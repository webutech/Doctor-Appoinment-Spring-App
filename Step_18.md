## Controller update

Initially we had created Controller now Here we need to create few more methods for handling user related activities. 

Code changes on Controller

```
package com.yash.damsapp.controller;

import org.apache.log4j.Logger;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Controller;
import org.springframework.web.bind.annotation.ModelAttribute;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RequestMethod;

import com.yash.damsapp.domain.User;
import com.yash.damsapp.service.UserService;

/**
 * This controller will perform all the user related controlling
 * @author sharma.pankaj
 *
 */

@Controller
@RequestMapping("/user")
public class UserController {
	
	private static final Logger logger =Logger.getLogger(UserController.class);
	
	@Autowired
	private UserService userService;
	
	@RequestMapping(value="/home.htm", method=RequestMethod.GET)
	public String showHomePage(){
		logger.info("user service : "+userService);
		return "home";
	}
	
	@RequestMapping(value="/userRegistration.htm", method=RequestMethod.GET)
	public String showUserRegistrationForm(){
		return "userRegistration";
	}

	@RequestMapping(value="/processUserRegistration.htm", method=RequestMethod.POST)
	public String processUserRegistration(@ModelAttribute("user") User user){
		userService.userRegistration(user);
		return "redirect:./home.htm";
	}
}

```
