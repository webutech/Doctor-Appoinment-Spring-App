## Service and ServiceImpl

- Code for UserService
```
package com.yash.damsapp.service;
import com.yash.damsapp.domain.User;
/**
 * This Service will handle user related services
 * @author sharma.pankaj
 *
 */
public interface UserService {
	public void userRegistration(User user);
}

```
- Code for UserServiceImpl
```
package com.yash.damsapp.serviceimpl;

import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;

import com.yash.damsapp.dao.UserDAO;
import com.yash.damsapp.domain.User;
import com.yash.damsapp.service.UserService;

@Service
public class UserServiceImpl implements UserService {
	
	@Autowired
	private UserDAO userDAO;

	public void userRegistration(User user) {
		userDAO.insert(user);
	}

}
```
