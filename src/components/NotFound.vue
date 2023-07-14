<template>
    <div id="notfound" class="container">
        <div class="row rowhijo">
            <img class="imagen" src="@/assets/404-error-not-found-page-lost.png" alt="404">
        </div>
    </div> 


</template>

<script>
    export default{
        name: 'notfound',
        data: function(){
            return{

            }
        },
        methods:{

        }
    }

</script>


<style scoped>
    #notfound{
     
        height: 600px;
    }

    .rowhijo{
        display: flex;
        flex-direction: row;
        justify-content: center;
    }
    .imagen{
        width: 67%;
       
    }


</style>