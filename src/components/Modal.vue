  <template>
    <div>
        <button @click="show = !show">Modal</button>
        <div class="prompt" v-if="show" @click="show = !show">
            <div id="modal-box" @click="show = !show">
                <div class="box">
                    <div id="center" :class="{ sale: isValid }">
                        <h1>{{ title }}</h1>
                        <p>{{ content }}</p>
                    </div>
                </div>
            </div>
        </div>
        <slot name="links"></slot>
    </div>
    <!-- <button @click="getUser(childData)"></button> -->
</template>
  
<script>
export default {
    name: 'Modal',
    data() {
        return {
            show: false,
            childData: "Im child",
        }
    },
    props: {
        title: String,
        content: String,
        theme: String,
        getUser: Function,
        show: Boolean
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
}

#center {
    width: 100%;
    padding: 45px;
    text-align: center;
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

.box {
    display: flex;
}

#modal-box {
    position: relative;
    background-color: blue;
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


</style>