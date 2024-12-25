<main>
<h1>Your information</h1>

<form action="/submit" method="POST">
    
        <div class="info-name">

          <label for="firstname">First Name:<span aria-hidden="true" style="color: red;">*</span></label>
          <input 
          type="text"
          id="firstname"
          name="firstname"
          required
          />
          
          <label for="lastname">Last Name:<span aria-hidden="true" style="color: red;">*</span></label>
          <input 
          type="text"
          id="lastname"
          name="lastname"
          required
          />
          
        </div>  

      <label for="emailaddress">Email Address:</label>
      <input
        type="email"
        id="emailaddress"
        name="emailaddress"
        required
      />
   
  
    <!-- <button type="submit">Submit</button> -->
  </form>
  

    <p>By donating, you agree to our <span>terms of services</span>  and <span>privacy policy</span>.</p>
</main>

<style>
    main {
        
        & form {
           /*  display: grid;
          grid-template-areas: initial; */
            
          & .info-name {
            display: flex;
            flex-direction: row;
            margin-left: 5rem;
            gap: 1rem;

            
          }
          
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