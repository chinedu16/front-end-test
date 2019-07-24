.<template>
  <button> {{msg}} </button>
</template>

<script>
export default {
name: 'button',
  props: {
    msg: String
  }
}
</script>

<style lang="scss">
button {
  height: 40px;
  background: lightseagreen;
  color: white;
  transition: 0.2s ease-in-out;
  border-radius: 50px;
  width: 162px;
  font-weight: bolder;
  padding: 10px 0px 10px;
  cursor: pointer;
  animation: jittery 4s infinite;
  &:hover {
    animation: heartbeat 0.2s infinite;
  }
}

@keyframes jittery {
  5%,
  50% {
    transform: scale(1);
  }
  10% {
    transform: scale(0.9);
  }
  15% {
    transform: scale(1.15);
  }
  20% {
    transform: scale(1.15) rotate(-5deg);
  }
  25% {
    transform: scale(1.15) rotate(5deg);
  }
  30% {
    transform: scale(1.15) rotate(-3deg);
  }
  35% {
    transform: scale(1.15) rotate(2deg);
  }
  40% {
    transform: scale(1.15) rotate(0);
  }
}

@keyframes heartbeat {
  50% {
    transform: scale(1.1);
  }
}
</style>
