<script>
export default {
  name: 'App',
  data() {
    return {
      form: {
        bColor: '',
        tColor: '',
        sText: true,
        range: 0,
        textarea: '',
        tSize: '',
        bOpacity: false,
        box: 'box',
        contenedor: 'contenedor',
        tStyles: [
          { value: '', label: 'Default' },
          { value: 'Roboto', label: 'Roboto' },
          { value: 'Courier New', label: 'Courier New' },
          { value: 'Georgia', label: 'Georgia' },
          { value: 'Trebuchet MS', label: 'Trebuchet MS' },
          { value: 'Arial', label: 'Arial' },
          { value: 'Times New Roman', label: 'Times New Roman' },
          { value: 'Verdana', label: 'Verdana' },
          { value: 'Helvetica', label: 'Helvetica' }
        ]
      }
    }
  }
}
</script>

<template>
  <div :class="{'contenedor': form.contenedor}">
    <div class="container p-0 m-0">
      <div class="row">
        <div class="col-5 form-box p-5">
          <form>
            <div class="form-group mb-3">
              <label class="form-label" for="bColor">Color de fondo</label>
              <input type="text" class="form-control" v-model="form.bColor" id="bColor" />
            </div>
            <div class="form-group mb-3">
              <label class="form-label" for="input2">Color de texto</label>
              <input type="text" class="form-control" v-model="form.tColor" id="tColor" />
            </div>
            <div class="form-check mb-3">
              <input class="form-check-input" type="checkbox" id="sText" value="sText"
                v-model="form.sText">
              <label class="form-check-label" for="sText">Mostrar Texto</label>
            </div>
            <div class="form-group mb-3">
              <label for="customRange1" class="form-label">Borde</label>
              <input type="range" class="form-range" id="customRange1" v-model="form.range">
            </div>
            <div class="form-group mb-3">
              <label class="form-label" for="textarea">Contenido Textual</label>
              <textarea class="form-control" v-model="form.textarea" id="textarea" rows="5"></textarea>
            </div>

            <div class="form-group mb-3">
              <label class="form-label" for="select">Tipografía</label>
              <select class="form-control" v-model="form.select" id="select">
                <option v-for="option in form.tStyles" :value="option.value" :key="option.value"> {{ option.label }}</option>
              </select>
            </div>
            <div class="form-group mb-3">
              <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" id="bOpacity" value="bOpacity"
                v-model="form.bOpacity">
              <label class="form-check-label" for="bOpacity">Opaco</label>
              </div>
            </div>
            <div class="form-group">
              <label class="form-label" for="select">Tamaño de letra</label>
              <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio1" value="15px"
                  v-model="form.tSize" />
                <label class="form-check-label" for="inlineRadio1">Pequeño</label>
              </div>
              <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio2" value="25px"
                  v-model="form.tSize" />
                <label class="form-check-label" for="inlineRadio2">Mediano</label>
              </div>
              <div class="form-check form-check-inline">
                <input class="form-check-input" type="radio" name="inlineRadioOptions" id="inlineRadio3" value="40px"
                  v-model="form.tSize" />
                <label class="form-check-label" for="inlineRadio3">Grande</label>
              </div>
            </div>
          </form>
        </div>
        <div class="col-7 d-flex justify-content-center align-items-center bg-light">
          <div :class="{'boxOpacity': form.bOpacity, 'box': form.box}" :style="{background: form.bColor, borderRadius:  form.range + '%', color: form.tColor, fontFamily: form.select, fontSize: form.tSize}"><span v-show="form.sText">{{ form.textarea }}</span></div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.contenedor {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100vw;
}

.form-box {
  background-color: blueviolet;
}

label {
  font-weight: bold;
  display: block;
  font-size: 15px;
  color: white;
}


.boxOpacity {
  opacity: .5;
}

.box {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 500px;
  height: 500px;
  font-weight: bold;
  text-wrap: break-word;
  text-align: center;
  padding: 40px;
}

</style>
