<template>
    <div>
        <div class="container">
			<div class="d-flex mb-5 mt-5">
				<a href="/" class="my-auto mr-3">
					<img src="/Arrow-Icon.svg" alt="edit" title="Edit" class="icon-action"/>
				</a>
				<div class="title"> Editar Naver </div>
			</div>
			<formEdit :naver="naver"/>
        </div>
    </div>
</template>
<script>
import formEdit from '~/components/formEdit'
    export default {
        data(){
            return{

            }
        },
        async asyncData({params, query, res, $axios, req, app, error, store}) {
        try {
            let naver = {}
            await $axios.$get(`/navers/${query.id}`).then((res) =>{
                naver = res
            })
            return {
                naver: naver
            }
        }
        catch (e) {
            console.log(e)
        }
    },
    }
</script>