<template>
    <div class="my-cards">
        <div class="content top">
            <h3>{{ type }}</h3>
            <p class="percentage"><i class="fa fa-arrow-up"></i>{{ percentage }}</p>
        </div>

        <div class="content footer">
            <i :class="['fa', icon]"></i>
            <p class="qtd">{{ qtd }}</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'CardsComponent',
    props: {
        type: String,
        percentage: String,
        icon: String,
        qtd: String
    }
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/_main';

    .my-cards {
        display: flex;
        flex-direction: column;
        width: 100%;
        background-color: $purple;
        padding: 15px;
        border-radius: 7px;
        color: #fff;

        .content {
            display: flex;
            justify-content: space-between;
        }

        .top {

            .percentage {
                color: $green;
            }
        }

        .footer {
            display: flex;

            .qtd {
                font-size: 20px;
                margin: 0;
            }
        }
    }
</style>