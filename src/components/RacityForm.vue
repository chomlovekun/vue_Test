<template>
    <div class="col-md-6 offset-md-3 col-sm-12 ">
        <div class="jumbotron">
{{receipt}}
            <form @submit.prevent="" class="form-horizontal">
                <fieldset class="highlight">

                    <!-- Form Name -->
                    <legend>Form Name</legend>
                    <!-- Text input-->
                    <div class="form-group row">
                        <label class="col-md-4 control-label" for="">title</label>
                        <div class="col-md-4">
                            <input id="" name="" type="text" placeholder="Yuor title" v-model="receipt.title" class="form-control">

                        </div>
                    </div>

                    <!-- Text input-->
                    <div class="form-group row">
                        <label class="col-md-4 control-label" for="Desc_id">Description</label>
                        <div class="col-md-4">
                            <input id="Desc_id" name="Desc_id" v-model="receipt.desc" type="text" placeholder="Your des" class="form-control input-md">

                        </div>
                    </div>

                    <!-- Text input-->
                    <div class="form-group row">
                        <label class="col-md-4 control-label" for="Image_id">Image</label>
                        <div class="col-md-4">
                            <input id="Image_id" name="Image_id" type="text" v-model="receipt.Img" placeholder="Your Image" class="form-control input-md">

                        </div>
                    </div>
                    <div data-v-68c7a4fb="" class="row">
                        <div data-v-68c7a4fb="" class="col">
                            <button  class="btn btn-primary float-right" @click="addIngredient"><i data-v-68c7a4fb="" class="fa fa-plus-circle"></i> more Ingredient
                            </button>
                        </div>
                    </div>
                    <!-- Button (Double) -->
                    <div class="form-group  row" >
                        <label class="col-md-4 control-label" for="Ingredientsid">Ingredients</label>
                        <div class="col-md-4" v-for="(Ingredient,index) in receipt.Ingredient" :key="index" >
                            <input v-model="receipt.Ingredient[index]"  id="Ingredientd" name="Ingredientd" type="text"  placeholder="Ingredient" class="form-control input-md">

                        </div>
                        <div class="col-md-8">
                            <button id="Ingredientsid" name="Ingredientsid" class="btn btn-danger">cancal</button>
                            <button id="saveid" @click="save" name="saveid"  class="btn btn-success">save</button>
                        </div>
                    </div>

                </fieldset>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    data () {
        return {
            receipt: {
                title: "",
                desc: "",
                Img: "",
                Ingredient: ['']
            }
        }
    },
    methods:{
        addIngredient (){
            this.receipt.Ingredient.push('');
        },
        save(){
            this.$emit('savereceipt', this.receipt)
        }
    }
}
</script>

<style scoped>
</style>