## How to Create different pages and link them  

- Create userRegistration.jsp page in view folder. 
- Copy whole code from home.jsp page and paste on userRegistration.jsp page. 
- make changes in the Registration link as shown below
  ``` 
    <li class="nav-item">
         <a class="nav-link" href="./userRegistration.htm">Registration</a>
    </li>
  ```
  - Create one method in the UserController as shown below
    ```
      @RequestMapping(value="/userRegistration.htm", method=RequestMethod.GET)
	    public String showUserRegistrationForm(){
		    return "userRegistration";
	    }
    ```
  - modify the link for home as well by taking the reference of above mentioned steps.
