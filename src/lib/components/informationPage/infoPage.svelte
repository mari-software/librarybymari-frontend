<main>
<h1>Your information</h1>

<form action="/submit" method="POST">
    
  
      <label for="firstname">First Name:<span aria-hidden="true" style="color: red;">*</span></label>
      <input 
        type="text"
        id="firstname"
        name="firstname"
        required
        autocomplete="given-name"
      />
  
      <label for="lastname">Last Name:<span aria-hidden="true" style="color: red;">*</span></label>
      <input 
        type="text"
        id="lastname"
        name="lastname"
        required
        autocomplete="family-name"
      />
  
      <label for="emailaddress">Email Address:</label>
      <input
        type="email"
        id="emailaddress"
        name="emailaddress"
        autocomplete="email"
      />
   
  
    <!-- <button type="submit">Submit</button> -->
  </form>
  

    <p>By donating, you agree to our <span>terms of services</span>  and <span>privacy policy</span>.</p>
</main>

<style>
    main {
        
        & form {
            display: grid;
          grid-template-areas: initial;
           /*  flex-basis: 100%;
					order: calc(2 - 1); */

                & input {
                    width: 20rem;
                    height: 1.2rem;
                }
        }

        & p{
            & span {
             color: blue;
            }
        }
    }
</style>