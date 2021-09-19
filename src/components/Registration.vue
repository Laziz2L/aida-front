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

            <button id="save-btn" class="btn registration__save-btn" @click="submit">
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

        submit() {
            this.age = parseInt(this.age);
            alert("name: " + this.name + "\nage: " + this.age + "\nsex: " + (this.male ? "male" : (this.female ? "female" : "")))
        },

        setMargins() {
            let screenHeight =
                window.innerHeight ||
                document.documentElement.clientHeight ||
                document.body.clientHeight;
            // console.log(screenHeight);
            let saveBtn = document.getElementById("save-btn");
            let saveBtnHeight = saveBtn.offsetHeight;
            // console.log(saveBtnHeight);

            let center = document.getElementById("vertical-center");
            let centerHeight = center.offsetHeight;
            // console.log(centerHeight);

            // // let centerHeight = 350;
            // console.log([centerHeight, saveBtnHeight, screenHeight]);
            if ( ((screenHeight - centerHeight) / 2) > (saveBtnHeight + 20) ) {
            // if (screenHeight > (centerHeight + saveBtnHeight + 60)) {
                center.style.marginTop =
                    (screenHeight - centerHeight) / 2 + "px";
                saveBtn.style.marginTop =
                    screenHeight -
                    (screenHeight - centerHeight) / 2 -
                    centerHeight -
                    (saveBtnHeight + 20) +
                    "px";
                // saveBtn.style.marginBottom
            } else {
                center.style.marginTop = "20px";
                saveBtn.style.marginTop = "20px";
            }
        },
    },
    mounted() {
        this.setMargins();

        window.addEventListener("resize", this.setMargins, true);
    },
};
</script>

<style>
</style>