<template>
    <div class="twoot-item">
        <div class="user-profile__twoot">
            <div class="twoot-item__user"> 
                @ {{ username }} <!-- Remember this is a propeed passed in from UserP-->
            </div>
            <div class="twoot-item__content">
                {{ twoot.content }}
            </div>
        </div>
    </div>

</template>

<script>
    export default{
        name: "TwootItem",
        props: {
            username: {
                type: String,
                required: true
            },
            twoot: {
                type: Object,
                required: true
            }
        }
    };

</script>

<style>
    .twoot-item{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        margin-top: 25px;
        padding-right: 80rem;
        cursor: pointer;
    }

    .user-profile__twoot{
        width: 325px;
        height: 4rem;
        background-color: #ffffff;
        border-radius: 8px;
        overflow: hidden;
        box-shadow: 0px 2px 4px rgba(0,0,0,0.2);
        padding: 1rem;
        padding-right: 40rem;
        transition: all 0.25s ease;
    }

    .user-profile__twoot:hover{
        transform: scale(1.1, 1.1);
    }

    .twoot-item__user{
        text-align: left;
        font-weight: bold;
    }

    .twoot-item__content{
        font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        font-weight: 300;
        text-align: left;
    }

</style>