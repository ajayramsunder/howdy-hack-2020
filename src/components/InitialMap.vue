<template>
  <div id="map" ref="newmap"></div>
</template>

<script>
export default {
    mounted () {
        this.createMap()
        // eslint-disable-next-line
        google.maps.event.addDomListener(this.map, 'click', (event) =>{
            this.addClickMarker(event.latLng)
        })
    }, 
    methods: {
        createMap () {
            // eslint-disable-next-line
            this.map = new google.maps.Map( 
                this.$refs.newmap, { zoom: 8, center: {lat: 29.749907,lng: -95.358421}})
        },
        addClickMarker (latlng) {
            // if (this.mapType === 'markerPolyline') {
            // eslint-disable-next-line
            this.new_marker = new google.maps.Marker({position: latlng, map: this.map})
            this.places.push(this.new_marker.getPosition())
            this.markers.push(this.new_marker)
            this.currentPlace = null
            // }
    },

    }  
}
</script>

<style>
#map{
    height: 400px;
    width: 100%;
  }
</style>