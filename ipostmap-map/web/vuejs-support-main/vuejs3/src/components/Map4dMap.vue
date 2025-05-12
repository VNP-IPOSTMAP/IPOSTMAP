<template>
  <div style="width: 100%; height: 100%; display: block;" :id=id ref="mapDom">
    <!-- <div style="display: none;">{{version}} {{accessKey}} {{mapId}} {{id}}</div> -->
  </div>
</template>

<script>

export default {
  name: 'Map4dMap',
  props: {
    version: String,
    accessKey: String,
    mapId: String,
    id: String,
    options: Object
  },
  data() {
    return {
      scriptElement: null,
      mapRef: null,
      mapCallback: null,
    }
  },
  methods: {
    createCallback() {
      this.mapCallback = `callback_${this.id}`
      window[this.mapCallback] = () => {
        let mapDom = this.$refs[`mapDom`]
        if (mapDom) {
          this.mapRef = new window.map4d.Map(mapDom, this.options)
          this.$emit('onMapReady', this.mapRef, this.id)
        } else {
          console.error(`Map4dMap: map element is NOT found`)
        }
      }
    },
    loadMapScript() {
      this.mapCallback = `callback_${this.id}`
      let url = `https://api.map4d.vn/sdk/map/js?version=${this.version}&key=${this.accessKey}&callback=${this.mapCallback}`
      if (this.mapId) {
        url += `&mapId=${this.mapId}`
      }
      let element = this.addLibrary(url, this.id)
      if (element) {
        this.scriptElement = element
      } else {
        //Invoke callback if map4d is existed
        window.map4d && window[this.mapCallback] && window[this.mapCallback]()
      }
    },
    addLibrary(url, id) {
      let scriptId = `script_${id}`
      let exist = document.getElementById(scriptId)
      if (exist) {
        return null
      }
      const script = document.createElement('script')
      script.src = url;
      script.defer = true;
      script.id = scriptId
      document.body.appendChild(script)
      return script
    },
    destroy() {
      delete window[this.mapCallback]
      if (this.scriptElement != null) {
        this.scriptElement.remove()
      }
      this.mapRef && this.mapRef.destroy()
      this.scriptElement = null
      this.mapRef = null
    }
  },
  beforeUpdate(){},
  mounted() {
    this.createCallback()
    this.loadMapScript()
  },
  beforeUnmount(){
    this.destroy()
  }
}
</script>
