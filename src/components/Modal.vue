  <template>
    <div>
        <button @click="show = !show">Modal</button>
        <div class="prompt" v-if="show" @click="show = !show">
            <div id="modal-box" :class="{ sale: isValid }" @click.prevent="show = !show">
                <h1>{{ title }}</h1>
                <p>{{ content }}</p>
                <div @click="show = !show" id="closeDiv">
                    <slot name="links" v-if="show"></slot>
                </div>
            </div>
        </div>
    </div>
</template>
  
<script>
export default {
    name: 'Modal',
    data() {
        return {
            show: false,
        }
    },
    props: {
        title: String,
        content: String,
        theme: String,
    },
    created() {
        if (this.theme == 'sale') {
            this.isValid = true
        }
    },
}
</script>

<style>
* {
    margin: 0px;
    padding: 0px;
}

#center {
    
}

#center h1 {
    color: rgb(48, 184, 184);
}

.sale {
    background-color: orangered !important;
    color: white;
}

.sale h1 {
    color: white !important;
}

#modal-box {
    position: relative;
    padding: 45px 45px 5px 45px;
    text-align: center;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-content: center;
    display:block;
}

.prompt {
    background-color: rgba(0, 0, 0, .3);
    position: absolute;
    top: 0;
    left: 0;
    height: 100vh;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
}

#closeDiv {
    margin: 25px auto 0px auto;
}
</style>