## Code Fragmentation
Till step_11 we have whole template code on home.jsp page. In actual application we need to split the whole code in different manageable
fragments. Through this we want to achieve code reusblity, extensability, and maintainability.

### Steps for code fragmentation on DAMS app

we have certain section on home.jsp page like Header, main and footer. Header it self has few sections like logo, navigation etc. 

- Create **common** folder in view folder.
- Create header.jsp, footer.jsp, menu.jsp pages.
- take header section from home.jsp page and paste it in header.jsp
- do the same for footer
- do not remove the main section
- use below code to include jsp fragments. 
- ``` <%@include file="resource location"%> ```
