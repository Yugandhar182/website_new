<script>
	import { createEventDispatcher} from 'svelte';
	import 'bootstrap/dist/css/bootstrap.min.css';
	import { navigate } from "svelte-navigator";
  
  
	import Home from './Home.svelte';
  
	const dispatch = createEventDispatcher();
	import { Router, Link, Route } from "svelte-routing";
	import RecruitingAutomation from "./recruitingautomation.svelte";
	import RecruitingPricing from "./recruitingpricing.svelte";
  
  
  
	let showOverviewPopup = false;
	let showWhyRecruitlyPopup = false;
	let showTryFreeModal = false;
	let firstName = '';
	let email = '';
	let mobile = '';
	let companyName = '';
	let linkedIn = '';
	let address = '';
  
	let featureIndex = 0;
	const features = [
	  { text: 'ATS', color: 'blue' },
	  { text: 'CRM', color: 'green' },
	  { text: 'Marketing', color: 'purple' }
	];
   
  
	function openTryFreeModal() {
	  showTryFreeModal = true;
	}
  
   
	function openWhyRecruitlyPopup() {
	  showWhyRecruitlyPopup = true;
	}
  
	
	function closePopup() {
	  showTryFreeModal = false;
	  showWhyRecruitlyPopup = false;
	  showOverviewPopup = false;
	  
	}
	function openOverview() {
	 
	  showOverviewPopup = true;
	}
	setInterval(() => {
	  featureIndex = (featureIndex + 1) % features.length;
	}, 2000);
  
	function navigateToAutomation() {
	  location.href = "automation";
	}
  
	function navigateToPricing() {
	   location.href="pricing";
	}
   
  </script>
  
  <main>
  
	<div class="information">
	  <a on:click={openWhyRecruitlyPopup}  class="why-recruitly-anchor" style="color: blue; font-weight: 700;">Why Recruitly</a>
	  <span class="spacer"></span>
	 <li><a on:click={openTryFreeModal} style="color: blue; font-weight: 700;" class="why-recruitly-anchor" >Try Free</a></li>
	   
	  </div>
	  <div>
		<Router>
		  <nav>
			<Link to="/">Home</Link>
			<a on:click={navigateToAutomation}>Automation</a>
			<a on:click={navigateToPricing}>Pricing</a>
		  </nav>
	
		  <Route path="/" component={Home} />
		  <Route path="/recruiting_automation" component={RecruitingAutomation} />
		  <Route path="/recruiting_pricing" component={RecruitingPricing} />
		</Router>
	  </div>
  
	
	
	<div class="container">
	  <h1 class="display-4"style="color:blue;font-weight: 700;" > Recruitment</h1>
	   <h1 class="display-4"style="color:blue;font-weight: 700;"><span class="feature-text" style="color: {features[featureIndex].color}; font-weight: 700;">
		{features[featureIndex].text}
	  </span>
	  System</h1>
		
	  
	 <p class="card-text">Recruitly® is built to streamline agency recruitment processes and help businesses grow as a result.</p>
	</div>
	<div class="overview-button-container">
	  <button class="overview-button" on:click={openOverview}>Overview</button>
	</div>
	<section class="features-section">
	  <div class="container">
		<div class="row">
		  <div class="col-md-4">
			<div class="feature-card">
			  <i class="fa fa-search"></i>
			  <h3 style="color:red; font-weight: 700;">Powerful Search</h3>
			  <p>Efficiently search and filter through a large pool of candidates.</p>
			</div>
		  </div>
		  <div class="col-md-4">
			<div class="feature-card">
			  <i class="fa fa-envelope"></i>
			  <h3 style="color:blue;font-weight: 700;">Email Integration</h3>
			  <p>Seamlessly integrate with your email client for easy communication.</p>
			</div>
		  </div>
		  <div class="col-md-4">
			<div class="feature-card">
			  <i class="fa fa-users"></i>
			  <h3 style="color:purple;font-weight: 700;">Collaborative Hiring</h3>
			  <p>Collaborate with your team to make better hiring decisions.</p>
			</div>
		  </div>
		</div>
	  </div>
	</section>
  
	<section class="testimonials-section">
	  <div class="container">
		<div class="row">
		  <div class="col-md-6 offset-md-3">
			<h2 style="color:green;font-weight: 1000;">Faster, Smarter and Effective Recruitment CRM</h2>
			<div class="testimonial">
			  <p>Recruit faster and smarter with our customisable pipelines, built-in job posting and out-of-the-box integrations with the tools you already use and love.</p>
			 
			</div>
		  </div>
		</div>
	  </div>
	</section>
  
	
	<section class="testimonials-section">
	  <div class="container">
		<div class="row">
		  <div class="col-md-6 offset-md-3">
			<h2 style="color:darkred;font-weight: 700;">What Our Clients Say</h2>
			<div class="testimonial">
			  <p>"Recuitly.io has transformed our hiring process. We found the perfect candidates in no time."</p>
			  <p class="testimonial-author">John Doe, CEO at ABC Company</p>
			</div>
		  </div>
		</div>
	  </div>
	</section>
	
	<footer class="footer-section">
	  <div class="container">
		<div class="row">
		  <div class="col-md-6">
			<p style="font-weight: 700;">&copy; 2023 Recuitly.io. All rights reserved.</p>
		  </div>
		  
		</div>
	  </div>
	</footer>
  
	
	 </main>
  
	 {#if showWhyRecruitlyPopup}
	 
	 
	 <div class="popup" on:click={closePopup}>
	  
	   <div class="popup-content">
		 <button class="close-button" on:click={closePopup}>&times;</button>
		 <div class="popup-section">
		   <h3>Email Marketing</h3>
		   <p class="custom-paragraph">Engage talent at the right time, promote your business to the right audience.</p>
		 </div>
		 <div class="popup-section">
		   <h3>Applicant Tracking System</h3>
		   <p class="custom-paragraph">Candidate sharing, boolean searches, interview scheduling, automation and more.</p>
		 </div>
		 <div class="popup-section">
		   <h3>Website Integration</h3>
		   <p class="custom-paragraph">Turn your WordPress website into a fully featured job-board using our FREE plugins.</p>
		 </div>
		 <div class="popup-section">
		   <h3>Job Distribution</h3>
		   <p class="custom-paragraph">Get your job in front of millions of candidates, manage applicants in one place.</p>
		 </div>
		 <div class="popup-section">
		   <h3>Search & Import</h3>
		   <p class="custom-paragraph">Search and import candidates from CV-Library and TotalJobs with just a few clicks.</p>
		 </div>
		 <div class="popup-section">
		   <h3>Recruiting Automation</h3>
		   <p class="custom-paragraph">Boost your team's productivity by creating workflows that automate repetitive and common tasks.</p>
		 </div>
	   </div>
	 </div>
  
   {/if}
   
  
  {#if showOverviewPopup}
	<div class="popup" on:click={closePopup}>
	  <div class="popup-content">
		<button class="close-button" on:click={closePopup}>&times;</button>
		<div class="popup-video-section">
		  <iframe class="popup-video" src="https://www.youtube.com/embed/9L0fVJb7zSk" frameborder="0" allowfullscreen></iframe>
		</div>
	  </div>
	</div>
  {/if}
  
  
	  
  {#if showTryFreeModal}
  <div class="modal" tabindex="-1" role="dialog" style="display: block;">
	<div class="modal-dialog" role="document">
	  <div class="modal-content">
		<div class="modal-header">
		  <h5 class="modal-title" style="color: blue;">Start your 1-Week FREE trial.</h5>
		 
		  <button type="button" class="close" aria-label="Close" on:click={closePopup}>
			<span aria-hidden="true">&times;</span>
		  </button>
		 
		</div>
		<div class="modal-body">
		  <form>
			<div class="form-group">
			  <label for="firstName"></label>
			  <input type="text" class="form-control" id="firstName" bind:value={firstName} placeholder="Enter your first name">
			</div>
			<div class="form-group">
			  <label for="email"></label>
			  <input type="email" class="form-control" id="email" bind:value={email} placeholder="Enter your email">
			</div>
			<div class="form-group">
			  <label for="mobile"></label>
			  <input type="tel" class="form-control" id="mobile" bind:value={mobile} placeholder="Enter your mobile number">
			</div>
			<div class="form-group">
			  <label for="companyName"></label>
			  <input type="text" class="form-control" id="companyName" bind:value={companyName} placeholder="Enter your company name">
			</div>
			<div class="form-group">
			  <label for="linkedIn"></label>
			  <input type="text" class="form-control" id="linkedIn" bind:value={linkedIn} placeholder="Enter your LinkedIn profile URL">
			</div>
			<div class="form-group">
			  <label for="address"></label>
			  <textarea class="form-control" id="address" bind:value={address} placeholder="Enter your address"></textarea>
			</div>
		  </form>
		</div>
		<div class="modal-footer">
		  <button type="button" class="btn btn-primary" on:click={closePopup}>Submit</button>
		</div>
	  </div>
	</div>
  </div>
  {/if}
  
  <style>
	
	.spacer {
	margin: 0 10px;
  }
  
	.container {
	  text-align: center;
	  margin-top: 200px;
	}
	h1.display-4 {
	  font-size: 3.5rem;
	  margin-bottom: 0.5rem;
	  font-stretch: expanded;
	}
	.font-weight-bold {
	  font-weight: bold;
	}
  
	.header {
	  background-color: #f8f9fa;
	  padding: 20px;
	  text-align: center;
	}
  
	.information {
	  position: absolute;
	  top: 50px;
	  right: 270px;
	  display: flex;
	  flex-direction: row;
	  align-items: center;
	}
  
	.information p {
	  margin: 0;
	  margin-left: 10px;
	  cursor: pointer;
	}
  
	.popup {
	  position: fixed;
	  top: 0;
	  left: 0;
	  width: 100%;
	  height: 100%;
	  background-color: rgba(0, 0, 0, 0.5);
	  display: flex;
	  justify-content: center;
	  align-items: center;
	}
  
	.popup-content {
	  position: relative; /* Added position relative */
	  background-color: #fff;
	  padding: 20px;
	  text-align: center;
	  border-radius: 5px;
	  width: 80%; /* Increased the width */
	  height: 80%; /* Increased the height */
	  max-width: 800px;
	  display: flex;
	  flex-wrap: wrap;
	  justify-content: center;
	  align-items: center;
	  overflow-y: auto;
	}
  
	.popup-section {
	  width: calc(50% - 20px); 
	  height: 25%; 
	  padding: 10px;
	}
  
	.custom-paragraph {
	  text-align: center; 
	}
  
	.popup-content h3 {
	  text-align: center;
	  color: blue;
	}
  
	.popup-content p.custom-paragraph {
	  width: 100%; /* Set the width for the paragraphs */
	  text-align: center; /* Center the paragraph text */
	}
  
	body {
	  background-color: #e2f3fc;
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
	.overview-button {
	  margin-top: 10px;
	  padding: 10px 20px;
	  background-color: yellow;
	  color: black;
	  border: none;
	  border-radius: 5px;
	  font-size: 16px;
	  cursor: pointer;
	  display: flex;
	  align-items: center;
	  margin-left: 700px; /* Add margin from the left side */
	  margin-right: auto; /* Add margin from the right side */
	}
	.popup-video-section {
	  width: 100%;
	  text-align: center;
	}
  
	.popup-video {
	  width: 100%;
	  height: 400px;
	}
  
	.why-recruitly-anchor {
	  cursor: pointer;
	}
   
	.modal {
	  background-color: rgba(0, 0, 0, 0.5); /* Adjust the alpha value to control transparency */
	}
  
  
	
  </style>
  
