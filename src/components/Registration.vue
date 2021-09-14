<template>
    <div class="container">
        <div class="registration">
            <img src="../assets/avatar.png" class="avatar" />
            <form class="registration-form">
                <input
                    type="text"
                    class="registration-form__input"
                    placeholder="Введите имя"
                />
                <input
                    type="text"
                    class="registration-form__input"
                    placeholder="Сколько вам лет?"
                />
                <div class="registration-form__sex-choose">
                    <button type="button" class="btn registration-form__sex-btn ">
                        Мужчина
                    </button>
                    <button type="button" class="btn registration-form__sex-btn">
                        Женщина
                    </button>
                </div>
            </form>

            <br>
            <br>
            <br>
            <br>

            <button class="btn registration__save-btn">Сохранить</button>
        </div>
    </div>
</template>

<script>
export default {};
</script>

<style>
</style>