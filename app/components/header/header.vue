<template>
    <div class="header">
        <p class="title">{{ title }}</p><p class="time"> {{ time }}</p>
    </div>
</template>

<script>
    export default {
      data () {
        return {
          title:'Tianpf\'s Vue Station',
          time:'0'
        }
      },
      methods:{
        format (num) {
          return num > 9 ? num : '0' + num
        }
      },

      created () {
        setInterval(() => {
          const date = new Date()
          const y = date.getFullYear()
          const m = date.getMonth() + 1
          const d = date.getDate()
          const h = date.getHours()
          const mm = date.getMinutes()
          const s = date.getSeconds()

          this.time = `${y}年${this.format(m)}月${this.format(d)}日 ${this.format(h)}:${this.format(mm)}:${this.format(s)}`

        })
      }

    }
</script>

<style>
    .header{
        width:100%;
        height:6rem;
        margin-bottom:1rem;
    }

    .header p{
        display:inline-block;
        box-sizing:border-box;
        vertical-align: top;
    }
    .header .title{
        background:url(../../img/logo.png) 2rem 0.4rem no-repeat;
        background-size:5rem 5rem;
        width:60%;
        height:6rem;
        padding-left:8rem;
        line-height:6rem;
        font-size:3rem;
        color:#fff;
    }
    .header .time{
        background:#333;
        opacity:0.6;
        width:40%;
        height:6rem;
        padding-right:2rem;
        line-height:6rem;
        font-size:2rem;
        text-align:right;
        color:yellow;
    }

</style>