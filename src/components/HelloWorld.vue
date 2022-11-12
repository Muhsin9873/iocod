<template>
  <div class="container">
    <div class="top-container">
      <div class="input-wrapper">
        <input type="text" placeholder="Transaction from" class="input-field">
        <input type="text" placeholder="Date from" class="input-field">
        <input type="text" placeholder="Transaction Status" class="input-field">
        <input type="text" placeholder="Transaction To" class="input-field">
        <input type="text" placeholder="Date To" class="input-field">
        <input type="text" placeholder="Type" class="input-field">
      </div>

    </div>
    <div class="bottom-container">
       <div class="search-container">
          <div>
            <input type="text" placeholder="Search" class="input-field">
          </div>
          <div class="create-button-wrapper">
            <button class="create-button">Create Customer</button>
          </div>
       </div>
       <div class="table-container">
         <table>
           <tr>
             <th>S/N</th>
             <th>Transfer from</th>
             <th>Transfer To</th>
             <th>Requested amount</th>
             <th>Completed amount</th>
             <th>Date & Time</th>
             <th>Action</th>
           </tr>
           <tr v-for="data in tableData" :key="data.sl">
              <td>{{data.sl}}</td>
              <td>{{data.from}}</td>
              <td>{{data.to}}</td>
              <td>{{data.refund_amount}}</td>
              <td>{{data.compl_amount}}</td>
              <td>{{data.date}}</td>
              <td> <i class="fa fa-eye"></i></td>

           </tr>
         </table>
       </div>
    </div>
    <div class="res-bottom" v-for="data in tableData" :key="data.sl">
       <div class="inner-wrapper">
         <div class="transfer-data">
           <div class="transfer-data-text">
             Transfer from <br> {{data.from}}
           </div>
           <div class="transfer-data-text">
            Transfer to <br> {{data.to}}
           </div>
         </div>
         <div class="transfer-data">
           <div class="transfer-data-text">
             Requested amount<br> {{data.refund_amount}}
           </div>
           <div class="transfer-data-text">
            Completed amount <br> {{data.compl_amount}}
           </div>
         </div>
         <div class="transfer-data">
           <div>
             Date & time<br> {{data.date}}
           </div>
         </div>
       </div>
       <div class="action-icon">
        <i class="fa fa-eye"></i>
       </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data(){
    return{
      tableData:[
        {
        sl:1,
        from:'doodle',
        to:'merchant',
        refund_amount:2.99,
        compl_amount:2.99,
        date:'10-19-2022 04:56 PM'
      },
      {
        sl:2,
        from:'doodle',
        to:'merchant',
        refund_amount:2.99,
        compl_amount:2.99,
        date:'10-19-2022 04:56 PM'
      },
      {
        sl:3,
        from:'Tiago',
        to:'merchant',
        refund_amount:2.99,
        compl_amount:2.99,
        date:'10-19-2022 04:56 PM'
      },
      {
        sl:4,
        from:'doodle',
        to:'merchant',
        refund_amount:2.99,
        compl_amount:2.99,
        date:'10-19-2022 04:56 PM'
      },
      {
        sl:5,
        from:'Tiago',
        to:'merchant',
        refund_amount:2.99,
        compl_amount:2.99,
        date:'10-19-2022 04:56 PM'
      },
      {
        sl:6,
        from:'doodle',
        to:'merchant',
        refund_amount:2.99,
        compl_amount:2.99,
        date:'10-19-2022 04:56 PM'
      }
    ]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container{
  background-color: rgb(245, 242, 242);
  /* width: 100%; */
  height: 100%;
  padding: 20px;
}
.top-container{
  background-color: rgba(207, 218, 227, 0.386);
  border-radius: 20px;
}
.input-field{
  width: 400px;
  height: 25px;
  border-radius: 5px;
  padding: 8px;
  margin-right: 25px;
  margin-bottom: 20px;

}
input{
  border: 1px solid gray;
}
.input-wrapper{
  border-radius: 5px;
  width: 80%;
  padding: 20px;
  background-color:white

}
.search-container{
  display: flex;
  justify-content: space-between;
  padding: 20px;
}
.create-button{
  background-color:rgba(0, 0, 255, 0.849);
  color: white;
  width: 180px;
  height: 35px;
  border-radius: 5px;
  
}
.bottom-container{
  margin-top: 30px;
  border-radius: 20px;
  background-color: #fff;

}
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}
td, th {
  text-align: left;
  padding: 8px;
  height: 50px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.164);
}

.res-bottom{
  border: 1px solid rgba(207, 218, 227, 0.386);;
  border-radius: 15px;
  background-color: rgba(207, 218, 227, 0.386);
  width: 500px;
  margin-top: 30px;
  /* padding: 20px; */
}
.transfer-data{
  display: flex;
  /* justify-content: space-between; */
  margin-bottom: 20px;
  
}
.inner-wrapper{
  margin-top: 10px;
  /* margin-bottom: 30px; */
  padding: 20px;
  border-radius: 15px;
  background-color: white;
}
.action-icon{
  display: flex;
  justify-content: center;
}

/** For responsive ness */
@media only screen and (max-width: 765px) {
  .bottom-container{
    display: none;
    
  }
}
@media only screen and (min-width: 765px) {
  .res-bottom{
    display: none;
    
  }
}

@media only screen and (max-width: 426px){
 .input-field{
  width: 250px;
 }
 .res-bottom{
  width: 380px;
 }
 .transfer-data-text{
  width: 180px;
 }
}
@media only screen and (max-width: 570px){
 .input-field{
  width: 250px;
 }
}

</style>
