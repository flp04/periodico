<template>
  <section>
    <div class="topo row">
      <div class="row">
        <div class="col-sm-4">
          <!-- <img :src="icone_clima" style="width: 30px;"> -->
          {{ temperatura_atual }} São Paulo
        </div>
        <div class="col-sm-4">
          {{ data_atual }}
        </div>
        <div class="col-sm-4">
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      temperatura_atual: '',
      icone_clima: '',
      data_atual: ''
    }
  },
  mounted() {
    let hoje = new Date()
    // this.dia_da_semana = hoje.getDay()
    switch (hoje.getDay()) {
      case 1 :
        this.data_atual = 'Segunda, '
        break
      case 2 :
        this.data_atual = 'Terça, '
        break
      case 3 :
        this.data_atual = 'Quarta, '
        break
      case 4 :
        this.data_atual = 'Quinta, '
        break
      case 5 :
        this.data_atual = 'Sexta, '
        break
      case 6 :
        this.data_atual = 'Sábado, '
        break
      case 7 :
        this.data_atual = 'Domingo, '
        break
    }
    this.data_atual += hoje.getDate() + ' de '
    switch (hoje.getMonth()) {
      case 1 :
      this.data_atual += 'janeiro de ' + hoje.getFullYear()
      break
      case 2 :
      this.data_atual += 'fevereiro de ' + hoje.getFullYear()
      break
      case 3 :
      this.data_atual += 'março de ' + hoje.getFullYear()
      break
      case 4 :
      this.data_atual += 'abril de ' + hoje.getFullYear()
      break
      case 5 :
      this.data_atual += 'maio de ' + hoje.getFullYear()
      break
      case 6 :
      this.data_atual += 'junho de ' + hoje.getFullYear()
      break
    }
    console.log(hoje)
    // this.data_atual = hoje.split(' ')[0]
    // async getClima (latlong) {
      this.carregando = true
    // console.log(this.dias)
      let API_KEY = "ce36eceef4d7486091d95932230303"

      // Definir o local de interesse e o número de dias de previsão
    // let location = this.cidade
      // let location = xyz
    
      let days = 2
    
      // Fazer a requisição HTTP para a API da weatherapi
    // let url = `https://api.weatherapi.com/v1/forecast.json?key=${API_KEY}&q=${location}&days=${days}&lang=pt`
      let url = `https://api.weatherapi.com/v1/forecast.json?key=${API_KEY}&q=Sao Paulo&days=${days}&lang=pt`
      
      try {
        fetch(url)
        .then(response => response.json())
        .then(data => {
          this.temperatura_atual = data.current.temp_c + '°'
          this.icone_clima = data.current.condition.icon
          // this.clima = {
          //   localidade: {
          //     cidade: data.location.name.replace('ao', 'ão'),
          //     estado: data.location.region.replace('ao', 'ão'),
          //     pais: data.location.country.replace('ao', 'ão')
          //   },
          //   clima_hoje: {
          //     temperatura_celsius: data.current.temp_c + '°',
          //     condicao: data.current.condition.text,
          //     condicao_img: 'https:' + data.current.condition.icon,
          //     temperatura_maxima_celcius: data.forecast.forecastday[0].day.maxtemp_c + '°',
          //     temperatura_minima_celcius: data.forecast.forecastday[0].day.mintemp_c + '°',
          //   },
          //   clima_amanha: {
          //     temperatura_maxima_celcius: data.forecast.forecastday[1].day.maxtemp_c + '°',
          //     temperatura_minima_celcius: data.forecast.forecastday[1].day.mintemp_c + '°',
          //     condicao: data.forecast.forecastday[1].day.condition.text,
          //     condicao_img: 'https:' + data.forecast.forecastday[1].day.condition.icon
          //   },
          //   astros: {
          //     lua: data.forecast.forecastday[0].astro.moon_phase
          //   }
          // }
          console.log(data)
          // this.carregando = false
        })
    //   // let response = await axios.get(url)
    //   // let response = axios.get(url)
    //   // console.log(response.data)
    //   // temperatura_atual = response.data.current.temp_c
    //   // previsao_amanha = { maxima : response.data.forecast.forecastday[0].day.maxtemp_c , minima : response.data.forecast.forecastday[0].day.mintemp_c }
    //   // temperatura_maxima = response.data.forecast.forecastday[0].day.maxtemp_c
    //   // temperatura_minima = response.data.forecast.forecastday[0].day.mintemp_c
    //   // local = response.data.location.name
    } catch (error) {
      console.log(error)
    }
  }
}
</script>
<style scoped>
  .topo {
    background-color: black;
    color: white;
    padding: 3px 10px 3px 10px;
  }
</style>