<template>
    <div class="container">
        <div class="registration">
            <div id="vertical-center" class="registration-center">
                <img src="../assets/avatar.png" class="avatar" />
                <form class="registration-form">
                    <input
                        v-model="name"
                        type="text"
                        class="registration-form__input"
                        placeholder="Введите имя"
                    />
                    <input
                        v-model="age"
                        type="text"
                        class="registration-form__input"
                        placeholder="Сколько вам лет?"
                    />
                    <div class="registration-form__sex-choose">
                        <button
                            @click="setMale()"
                            type="button"
                            class="btn registration-form__sex-btn"
                            v-bind:class="{ active: male }"
                        >
                            Мужчина
                        </button>
                        <button
                            @click="setFemale()"
                            type="button"
                            class="btn registration-form__sex-btn"
                            v-bind:class="{ active: female }"
                        >
                            Женщина
                        </button>
                    </div>
                </form>
            </div>

            <button id="save-btn" class="btn registration__save-btn">
                Сохранить
            </button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: "",
            age: "",
            male: false,
            female: false,
        };
    },
    methods: {
        setMale() {
            if (this.female) this.female = false;
            this.male = !this.male;
        },
        setFemale() {
            if (this.male) this.male = false;
            this.female = !this.female;
        },
    },
    mounted() {
        let screenHeight =
            window.innerHeight ||
            document.documentElement.clientHeight ||
            document.body.clientHeight;
        let saveBtn = document.getElementById("save-btn");
        let saveBtnHeight = saveBtn.offsetHeight;
        let center = document.getElementById("vertical-center");
        // let centerHeight = center.offsetHeight;
        let centerHeight = 350;
        console.log([centerHeight, saveBtnHeight, screenHeight]);
        if (screenHeight > centerHeight + saveBtnHeight + 20) {
            center.style.marginTop = (screenHeight - centerHeight) / 2 + "px";
            saveBtn.style.marginTop =
                screenHeight -
                (screenHeight - centerHeight) / 2 -
                centerHeight -
                (saveBtnHeight + 20) +
                "px";
        }
    },
};
</script>

<style>
</style>