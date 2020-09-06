<template>
  <div id="map" ref="newmap"></div>
</template>

<script>
export default {
    data () {
        return {
        }
    },
    mounted () {
        this.createMap()
        // eslint-disable-next-line
        google.maps.event.addDomListener(this.map, 'click', (event) =>{
            this.addClickMarker(event.latLng)
        })
        // eslint-disable-next-line
        this.infowindow = new google.maps.InfoWindow()
    }, 
    methods: {
        createMap () {
            // eslint-disable-next-line
            this.map = new google.maps.Map( 
                this.$refs.newmap, { zoom: 8, center: {lat: 30.615196,lng: -96.335957}})
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
        bindInfoWindow (marker, map, infowindow, description) {
            marker.addListener('click', function () {
                infowindow.setContent(description)
                infowindow.open(map, marker)
            })
        },
    }  
}
</script>

<style>
#map{
    height: 400px;
    width: 75%  ;
    float: right
  }
</style>