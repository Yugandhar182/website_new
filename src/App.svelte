
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
  <section class="recruiting-automation-section">
    <div class="links">
    <nav>
        <ul>
           <a on:click={openWhyRecruitlyPopup} class="why-recruitly-anchor" style="color: blue; font-weight: 700;">Why Recruitly</a>
          <span class="spacer"></span>
          <li><Link to="/automation" style="color:blue; font-weight: 700;">Automation</Link></li>
         
          <li><Link to="/pricing" style="color:blue; font-weight: 700;">Pricing</Link></li>
       
        </ul>
      </nav>
      </div>
    <div class="automation-component">
        
      <div class="hero-section">
        <h2 style="color: darkmagenta;">Recruiting Automation</h2>
        <p style="color:black; font-weight: 700;">Recruiting automation allows you to focus on the work that matters!</p>
        <p1 style="color:black; font-weight: 600;">Automation can be key to recruiting efficiency, but only if done right.</p1>
        <p2 style="color:black; font-weight: 600;">It takes time and effort to create the right workflow that is optimal for your business.</p2>
       

      </div>
      <h style="color:blue; ">Why Automate</h>
        <section class="testimonials-section">
          <table>
          <div class="container">
            <div class="col">
              <div class="col-md-4">
                <div class="feature-card">
                  <i class="fa fa-search"></i>
                  <h3 style="color:purple; font-weight:600;">Save time</h3>
                  <h6>Increase efficiency by creating workflows that automate repetitive and common tasks, save hours each week.</h6>
                </div>
              </div>
              <div class="col-md-4">
                <div class="feature-card">
                  <i class="fa fa-envelope"></i>
                  <h3 style="color:purple; font-weight:11600;">Proactive Interaction</h3>
                  <h6>Using Automation + Email Sequences you can engage with your passive contacts and candidates..</h6>
                </div>
              </div>
              <div class="col-md-4">
                <div class="feature-card">
                  <i class="fa fa-users"></i>
                  <h3 style="color:purple; font-weight:600;">Contain Costs</h3>
                  <h6>Automating redundant recruiting activities reduces the need for extensive labour.</h6>
                </div>
              </div>
              <div class="col-md-4">
                <div class="feature-card">
                  <i class="fa fa-users"></i>
                  <h3 style="color:purple; font-weight:600;">Improve Consistency and Accuracy</h3>
                  <h6>The possibility of errors with manual processing is a major drawback, especially when there are huge volumes involved.</h6>
                </div>
              </div>
              <div class="col-md-4">
                <div class="feature-card">
                  <i class="fa fa-users"></i>
                  <h3 style="color:purple; font-weight:600;">Happy Recruiters</h3>
                  <h6>Executing recurring activities on a daily basis gets mundane and monotonous for employees.</h6>
                </div>
              </div>
              
            
          </div>
        </table>
        </section>
         
      </div>
      
  </section>
 
  
  <style>
   
   .hero-section {
    text-align: center;
    margin-top: -1000px;
    margin-bottom: 10px;
  }
  .recruiting-automation-section h{
     
     font-weight: bold;
     font-size: 2rem;
   }
    .recruiting-automation-section h2 {
        margin-top: 1px;
    margin-bottom: 1px;
      font-weight: bold;
      font-size: 3rem;
    }
    .recruiting-automation-section p {
     
      font-weight: bold;
      font-size: 1.5rem;
    }
  
    .recruiting-automation-section h3 {

      font-weight: bold;
      font-size: 1.7rem;
    }
    .recruiting-automation-section h6 {

    font-weight: bold;
    font-size: 1rem;
   }
 
   .spacer {
	margin: 0 10px;
  }

  
   
    
    body {
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    .automation-component {
      width: 220vh;
      height:250vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background-color: #f0f0f0;
      padding: 20px;
      margin-left: 140vh;
      margin-right: -50vh;
    }

    .why-recruitly-anchor {
	  cursor: pointer;
	}

   

    .automation-component ul {
      list-style-type: disc;
      margin-left: 20px;
    }

    .automation-component li {
      font-size: 10px;
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
  </style>
  
