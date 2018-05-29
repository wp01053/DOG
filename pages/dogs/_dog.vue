<template>
<section class="section">
    <article class="hero">
        <div class="hero-body"></div>


    </article>
{{dogName}}

</section>

</template>
<script>
    export default{       
            asyncData({params}){
                return{
                    dogName: params.dog

                };
            }

        
    };


</script>
