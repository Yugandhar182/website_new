<script>
   import 'bootstrap/dist/css/bootstrap.min.css';
   import { Link } from "svelte-routing";
   import { createEventDispatcher } from 'svelte';
   import Popup from './Popup.svelte';

    let isPopupOpen = false;
    const dispatch = createEventDispatcher();
    function openWhyRecruitlyPopup() {
     isPopupOpen = true;
    }

function closePopup() {
isPopupOpen = false;
}
dispatch('openWhyRecruitlyPopup', { closePopup });
  
  
  </script>
   {#if isPopupOpen}
   <Popup {closePopup} />
 {/if}
  
  <section class="Recruitly Pricing">
    <div class="links">
        <nav>
            <ul>
               <a on:click={openWhyRecruitlyPopup} class="why-recruitly-anchor" style="color:blue; font-weight: 700;">Why Recruitly</a>
              <span class="spacer"></span>
              <li><Link to="/automation" style="color:blue; font-weight: 700;">Automation</Link></li>
              <span class="spacer"></span>
              <li><Link to="/pricing" style="color: blue; font-weight: 700;">Pricing</Link></li>
             
              
         </ul>
          </nav>
          </div>
    <div class="pricing-component">
      <div class="hero-section">
        <h1 style="color:blue;">Recruitly Pricing</h1>
        <p>Recruitly is a pay-as-you-go service  excluding 1-Week FREE trial all payments should be made upfront before using the service.
        <p>If the Customer’s place of business is within the UK we will add UK VAT to our fees at the then current rate.</p>  
        <p>If your place of business is in the EU (excluding the UK) and we are not obliged to charge you VAT (due to current applicable law).
        <p> we will only exclude VAT from invoices if you provide us with a valid VAT registration number or other proof that you are using the Service for business purposes.</p>
      </div>
      <section class="features-section">
        <div class="container-fluid mt-4">
          <h1 style="color:crimson;">Affordable plans</h1>
         
          <div class="row">
            <div class="col p-3 bg-success text-white" style="color: blue; font-weight: 700;">
              <h1>Solo</h1>
              <p>For independent recruiters</p>
              <p>$35</p>
              <p>/user/month</p>
            </div>
              
            <div class="col p-3 bg-warning  text-white" style=" font-weight: 700;">
              <h1>Startup</h1>
              <p>For startup agencies</p>
              <p>$50</p>
              <p>/user/month</p>
            </div>
            <div class="col p-3  bg-success text-white" style=" font-weight: 700;">
              <h1>Professional
              </h1>
              <p>For established teams</p>
              <p>$75</p>
              <p>/user/month</p>
            </div>
            <div class="col p-3 bg-warning  text-white" style="font-weight: 700;">
              <h1>Enterprise
              </h1>
              <p>For large organisations</p>
              <p>$100</p>
              <p>/user/month</p>
            </div>
          </div>
        </div>
      </section>
        
      </div>
      
  </section>
  
  <style>


    .hero-section {
        text-align: center;
    margin-top: -1200px;
    margin-bottom: 10px;
  }
  .container{
    width: 160vh;
  }
   
  
    .features-section h1 {
      color: blue;
      font-weight: bold;
      font-size: 2rem;
      margin-top: 50px;
    }
  
   
    .close-button {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: purple;
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    .pricing-component {
        margin-top:5vh;
      width: 220vh;
      height:250vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color:white;
      padding: 20px;
      margin-left: 140vh;
      margin-right: -50vh;
    }

    

    .pricing-component p {
      font-size: 18px;
      margin-bottom: 10px;
    }

    .pricing-component ul {
      list-style-type: disc;
      margin-left: 20px;
    }

    .pricing-component li {
      font-size: 16px;
      margin-bottom: 5px;
    }

    .links {
    display: flex;
    justify-content: flex-end;
    position: absolute;
    top:8px;
    right: 10px;
  }
  
  .links ul {
    display: flex;
    list-style-type: none;
    padding: 0;
  }
  
  .links li {
    margin-right: 5px;
  }
  .spacer {
	margin: 0 10px;
  }
  .close-button {
	  position: absolute;
	  top: 0px;
	  right: 1px;
	  font-size: 24px;
	  color: #f00f22;
	  background: transparent;
	  border: none;
	  cursor: pointer;
	}
    .why-recruitly-anchor {
	  cursor: pointer;
	}
   
  
  </style>
  
