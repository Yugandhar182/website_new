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
               <a on:click={openWhyRecruitlyPopup} class="why-recruitly-anchor" style="color: red; font-weight: 700;">Why Recruitly</a>
              <span class="spacer"></span>
              <li><Link to="/automation" style="color: red; font-weight: 700;">Automation</Link></li>
             
              <li><Link to="/pricing" style="color: red; font-weight: 700;">Pricing</Link></li>
             
              <li><a href="/" style="color: red; font-weight: 700;">Home</a></li> 
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
      <h1 class="display-4" style="color:green;font-weight:400;">Affordable plans for you</h1>
      <section class="features-section">
        <table>
            
        <div class="container">
          <div class="col">
            <div class="col-md-4">
              <div class="feature-card">
                <i class="fa fa-search"></i>
                <h3 style="color:purple; font-weight:600;">solo</h3>
                <p>For independent recruiters</p>
                <h3 >$35</h3>
                <p>/user/month</p>
              </div>
            </div>
            <div class="col-md-4">
              <div class="feature-card">
                <i class="fa fa-envelope"></i>
                <h3 style="color:purple; font-weight:600;">Startup</h3>
                <p>For startup agencies</p>
                <h3 >$50</h3>
                <p>/user/month</p>
              </div>
            </div>
            <div class="col-md-4">
              <div class="feature-card">
                <i class="fa fa-users"></i>
                <h3 style="color:purple; font-weight:600;">Professional</h3>
                <p>For established teams</p>
                <h3 >$75</h3>
                <p>/user/month</p>
              </div>
            </div>
           <div class="col-md-4">
              <div class="feature-card">
                <i class="fa fa-users"></i>
                <h3 style="color:purple; font-weight:600;">Enterprise</h3>
                <p>For large organisations</p>
                <h3 >$100</h3>
                <p>/user/month</p>
              </div>
            </div>
          </div>
        </div>
      </table>
      </section>
        
      </div>
      
  </section>
  
  <style>

h1.display-4 {
    text-align: center;
	  font-size: 3.5rem;
	  margin-bottom: 0.5rem;
	  font-stretch: expanded;
	}
      .hero-section {
       
        text-align: center;
    margin-top: -700px;
    margin-bottom: 10px;
  }
   
  
    .recruiting-pricing-section h1 {
      color: blue;
      font-weight: bold;
      font-size: 5rem;
    }
  
   
    .close-button {
      margin-top: 20px;
      padding: 10px 20px;
    
      color: white;
      border: none;
      border-radius: 5px;
      font-size: 16px;
      cursor: pointer;
    }
    body {
      margin: 0;
      padding: 0;
     
    }

    .pricing-component {
        width: 220vh;
      height:250vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #f0f0f0;
      padding: 50px;
      margin-left: 140vh;
      margin-right: -50vh;
    }
    .why-recruitly-anchor {
	  cursor: pointer;
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
    justify-content: center;
    margin-right: -2000px;
  }

  .links ul {
    display: flex;
    list-style-type: none;
    padding: 0;
  }

  .links li {
    margin-right: 20px;
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
  
  </style>
  
