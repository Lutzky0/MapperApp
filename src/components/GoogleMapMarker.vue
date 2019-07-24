<script>
import { POINT_MARKER_ICON_CONFIG } from "@/constants/mapSettings";


// Source: https://codesandbox.io/s/1o45zvxk0q?from-embed

export default {
  props: {
    google: {
      type: Object,
      required: true
    },
    map: {
      type: Object,
      required: true
    },
    marker: {
      type: Object,
      required: true
    }
  },

  mounted() {
    const { Marker } = this.google.maps;

    new Marker({
      position: this.marker.position,
      marker: this.marker,
      map: this.map,
      icon: POINT_MARKER_ICON_CONFIG
    });
  },

  render() {}
};
</script>
