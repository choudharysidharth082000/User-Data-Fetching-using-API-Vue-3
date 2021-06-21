<template>
<div>
    
        <div class="photocontainor">
            <div class="photocontainor_image">
                <img v-bind:src="`https://avatars.dicebear.com/v2/avataaars/${username}.svg?options[mood][]=happy`">
                 

            </div>
            <div class="photcontainor_dscription">
                <h6>{{data}}</h6>
                <p>{{email}}</p>
                <p>{{phone}}</p>
                <p>{{website}}</p>
                
                
                
                

            </div>
            <div class="photocontainor_functionality">
                <div class="functionality_like">
                    <p v-bind:onclick="likeselector" v-bind:class="{likes: likes}"><fa icon="heart" /></p>

                </div>
                <div class="functionality_edit">
                    <p><fa icon ="edit" /></p>

                </div>
                <div class="functionality_delete">
                    <p><fa icon= "trash" /></p>

                </div>

            </div>
            


        </div>
    </div>

    
</template>
<script>

export default {
    name : 'Header',

    props:{
        data: String,
        email: String,
        website: String,
        phone: String,
        username : String
    },
    data()
  {
    return{
        likes : false
    }

  },
    methods:
    {
        
        likeselector()
        {
            if(this.likes == true)
            {
                this.likes = false
            }
            else
            {
                this.likes = true
            }
        

        }
    },
   

    

    
   
}
</script>
<style scoped>
*
{
    margin: 0;
    padding: 0;
    font-family: Verdana, Geneva, Tahoma, sans-serif;
}

.photocontainor
{
    margin: 20px;
    
    
    width: 250px;
    height: 340px;
    display: flex;
    flex-direction: column;

}
.photocontainor_image 
{
    width: 250px;
    height: 150px;
    background-color: #efefef;
}
.photocontainor_image img
{
    object-fit: contain;
    height: 150px;
    width: 250px;
}
.photcontainor_dscription
{
    display: flex;
    padding-left: 10px;
    flex-direction: column;
    justify-content: center;
    align-items: to-left;
    color: rgba(0, 0, 0, 0.685);
    width: 250px;
    height: 150px;
    background-color: white;
}
.photcontainor_dscription h6
{
    font-size: 1rem;
    font-family: Arial, Helvetica, sans-serif;
    padding: 10px 10px 10px 0px;
    color: black;
}
.photcontainor_dscription p
{
    
    font-size: 0.75rem;
    color: rgba(0, 0, 0, 0.658);
    padding: 2px 2px 2px 0px;
}
.photocontainor_functionality
{
    height: 40px;
    width: 250px;
    background-color: #efefef;
    display: grid;
    grid-template-columns: 83.3px 83.3px 83.3px;

}
.functionality_like , .functionality_edit, .functionality_delete

{
    display: flex;
    justify-content: center;
    align-items: center;
    
    color: rgba(0, 0, 0, 0.842);
    font-size: 0.9rem;
    cursor: pointer;
}
.likes
{
    color: rgb(228, 13, 13);
    cursor: pointer;
}
.functionality_unlike 
{
    color: rgba(0, 0, 0, 0.356);
}


</style>