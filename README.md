# Example

Add.jsp
<?xml version="1.0" encoding="ISO-8859-1" ?>
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1" />
<title>SBM Details</title>
<link rel="stylesheet" type="text/css" href="css/style.css"/>
</head>
<body>
<form id="sbmForm" action="<%=request.getContextPath() %>/controller">
<input type="hidden" name="nextAction" value="sbmAdd"/>

<center><h2>Social Book Marking</h2></center>
<div style="border:2px solid;border-radius:25px;box-shadow: 10px 10px 5px #888888;">
 
    
	<table cellspacing="0" border="0" align="center" width="300">
	
	<tr><td colspan="2"><a href="<%=request.getContextPath()%>/controller?nextAction=sbmlistview"><strong><img src="images/view.png" width="42" height="42"></strong></a></td></tr>
	
	<% java.util.List<String> errors = (java.util.List<String>) request.getAttribute("errors"); 
	 if (errors != null) {
		 for (String error : errors) {
	%>
	<tr>
	  <td colspan="2"><%=error %></td>
	</tr>
	 <%} 
		 }%>
	
	<tr>
		<td style="font-weight:bold;"><label for="Title">SITE: </label> </td> 
		<td><input type="text" id="site" name="site" value="" size="25" /> </td> 
	</tr>
	<tr><td style="font-weight:bold;"><label for="Url">URL: </label> </td> 
	<td> <input type="text" id="url" name="url" /></td> </tr>
	<tr>
		<td style="font-weight:bold;"><label for="Username">USERNAME: </label> </td> 
		<td><input type="text" id="username" name="username" value="" size="20" /> </td> 
	</tr>
	<tr>
		<td style="font-weight:bold;"><label for="Password">PASSWORD: </label> </td> 
		<td><input type="password" id="password" name="password" value="" size="20" /> </td> 
	</tr>
	
	<tr><td style="font-weight:bold;"><label for="EMAIL">EMAILID:</label> </td> 
	<td> <input type="text" id="email" name="email" value="" /></td> </tr>
	<tr>
		<td style="font-weight:bold;"><label for="Phoneno">PHONENO: </label> </td> 
		<td><input type="text" id="phoneno" name="phoneno" value="" size="25" /> </td> 
	</tr>
	<tr><td style="font-weight:bold;"><label for="DISCRIPTION">DESCRIPTION: </label> </td> 
	<td><textarea cols="40" rows="4" id="description" name="description"></textarea> </td> </tr>
	
			
           <tr><td colspan="2"><input type="submit" value="SUBMIT"> <input type="reset" value="RESET" /> <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
     </table>
    </div>
	</form>

</body>
</html>



Update.jsp
<?xml version="1.0" encoding="ISO-8859-1" ?>
<%@page import="in.delhiguru.seo.dto.SocialBookMarking"%>
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1" />
<title>SBM Details</title>
<link rel="stylesheet" type="text/css" href="css/style.css"/>
</head>
<body>

<form id="sbmForm" action="<%=request.getContextPath() %>/controller">
<input type="hidden" name="nextAction" value="sbmUpdate"/>
<center><h2>Social Book Marking Update</h2></center>
<div style="border:2px solid;border-radius:25px;box-shadow: 10px 10px 5px #888888;">
 
    
	<table cellspacing="0" border="0" align="center" width="300">
	
	<tr><td colspan="2"><a href="<%=request.getContextPath()%>/controller?nextAction=sbmListView"><strong> <img src="images/view.png" width="42" height="42"> </strong></a></td></tr>
	<%
	SocialBookMarking sbm = (SocialBookMarking) request.getAttribute("entity");
	//System.out.println(sbm.getPassword());
	if (sbm != null) {
	%>
	<tr>
		<td style="font-weight:bold;"><label for="Title"> </label> </td> 
		<td><input type="hidden" id="id" name="id" value="<%=sbm.getId()%>" /> </td> 
	</tr>
	<tr>
		<td style="font-weight:bold;"><label for="Title">SITE: </label> </td> 
		<td><input type="text" id="site" name="site" value="<%=sbm.getSite()%>" /> </td> 
	</tr>
	<tr>
	    <td style="font-weight:bold;"><label for="Url">URL: </label> </td> 
	    <td> <input type="text" id="url" name="url" value="<%=sbm.getUrl() %>" /></td>
	 </tr>
	<tr>
		<td style="font-weight:bold;"><label for="Username">USERNAME: </label> </td> 
		
	    <td><input type="text" id="username" name="username" value="<%=sbm.getUsername() %>"  /> </td> 
	</tr>
	<tr>
		<td style="font-weight:bold;"><label for="Password">PASSWORD: </label> </td> 
		<td><input type="password" id="password" name="password" value="<%=sbm.getPassword() %>"> </td> 
	</tr>
	
	<tr><td style="font-weight:bold;"><label type="EMAIL">EMAILID:</label> </td> 
	<td> <input type="text" id="email" name="email" value="<%=sbm.getEmail() %>" /></td> </tr>
	<tr>
		<td style="font-weight:bold;"><label for="Phoneno">PHONENO: </label> </td> 
		<td><input type="text" id="phoneno" name="phoneno" value="<%=sbm.getPhone() %>" /> </td> 
	</tr>
	<tr><td style="font-weight:bold;">DESCRIPTION: </td> 
	<td><input type="text" id="description" name="description" value="<%=sbm.getDescription() %>" /> </td> 
	 </tr>
	
	<%
	}
	%>
			
           <tr><td colspan="2"><input type="submit" value="UPDATE"> <input type="reset" value="reset" /> <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
     </table>
    </div>
	</form>

</body>
</html>

Listview.jsp
<?xml version="1.0" encoding="ISO-8859-1" ?>
<%@page import="in.delhiguru.seo.dto.SocialBookMarking"%>
<%@page import="java.util.List"%>
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1" />
<title>SBM Details</title>
<link rel="stylesheet" type="text/css" href="css/style.css"/>
</head>
<body>

<center><h2>Social Book Marking ListView</h2></center>
 <div style="border:2px solid;border-radius:25px;box-shadow: 10px 10px 5px #888888;">
    
	<center><table cellspacing="0" border="1" align="centre" width="600">
	<tr><td colspan="11"><a href="<%=request.getContextPath()%>/controller?nextAction=sbmAddShow"><img src="images/add.png" width="42" height="42"></a> </td></tr>
	<tr>
	    <th>Sn</th>
		<th>Site </th>
		<th>Url</th>
		<th>UserName</th>
		<th>Password</th>
		<th>EmailId</th>
		<th>Phoneno</th>
		<th>Description</th>
		
		<th colspan="3"></th>
	</tr>
	
	<%
	List<SocialBookMarking> list = (List<SocialBookMarking>) request.getAttribute("list");
	
	if (list!= null) {
		int couner = 1;
		for(SocialBookMarking sbm : list) {
		
	%>
	
	<tr>
	<td><%=couner %> </td><td><%=sbm.getSite() %></td><td><%=sbm.getUrl() %></td><td><%=sbm.getUsername() %></td>
	<td><%=sbm.getPassword() %></td><td><%=sbm.getEmail() %></td><td><%=sbm.getPhone() %></td><td><%=sbm.getDescription() %></td>
	
	
	 <td>  
	    <a href="<%=request.getContextPath()%>/controller?nextAction=sbmUpdateShow&id=<%=sbm.getId() %>">
	    <img src="images/edit.png" width="42" height="42"></a> 
	   </td>
      <td> 
	    <a href="<%=request.getContextPath()%>/controller?nextAction=sbmView&id=<%=sbm.getId() %>">
	    <img src="images/view.png" width="42" height="42"></a></a> 
	</td>
	<td >
	    <!-- <a href="javascript:alert('Are you really want to delete this');">Delete</a> &nbsp;| &nbsp;-->
	    <!-- <a href="<%=request.getContextPath()%>/controller?nextAction=sbmDelete&id=<%=sbm.getId() %>">Delete</a> -->  
	    <a href="<%=request.getContextPath()%>/controller?nextAction=sbmDelete&id=<%=sbm.getId() %>">
	     <img src="images/delete.png" width="42" height="42"></a> 
	   </td>
	  
	 
	</tr>
	
	<%	
	couner++;
		}
	} 
	%>
	
	
	
     </table></center>
    </div>
</body>
</html>
View.jsp
<?xml version="1.0" encoding="ISO-8859-1" ?>
<%@page import="in.delhiguru.seo.dto.SocialBookMarking"%>
<%@ page language="java" contentType="text/html; charset=ISO-8859-1"
    pageEncoding="ISO-8859-1"%>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=ISO-8859-1" />
<title>SBM Details</title>
<link rel="stylesheet" type="text/css" href="css/style.css"/>
</head>
<body>
<center><h2>Social Book Marking View</h2></center>
<div style="border:2px solid;border-radius:25px;box-shadow: 10px 10px 5px #888888;">
 
    
	<table cellspacing="0" border="0" align="center" width="300">
	
	<tr><td colspan="2"><a href="<%=request.getContextPath()%>/controller?nextAction=sbmAddShow"><strong> <img src="images/add.png" width="42" height="42"> </strong></a></td></tr>
	<%
	SocialBookMarking sbm = (SocialBookMarking) request.getAttribute("entity");
	if (sbm != null) {
	%>
	<tr>
		<td style="font-weight:bold;"><label for="Title">SITE: </label> </td> 
		<td><%=sbm.getSite()%></td> 
	</tr>
	<tr>
	    <td style="font-weight:bold;"><label for="Url">URL: </label> </td> 
	    <td> <%=sbm.getUrl()%></td>
    </tr>
	<tr>
		<td style="font-weight:bold;"><label for="Username">USERNAME: </label> </td> 
		<td><%=sbm.getUsername()%> </td> 
	</tr>
	<tr>
		<td style="font-weight:bold;"><label for="Password">PASSWORD: </label> </td> 
		<td><%=sbm.getPassword()%> </td> 
	</tr>
	
	<tr>
	    <td style="font-weight:bold;"><label for="EMAIL">EMAILID:</label> </td> 
	    <td><%=sbm.getEmail()%> </td>  
	<tr>
		<td style="font-weight:bold;"><label for="Phoneno">PHONENO: </label> </td> 
		<td><%=sbm.getPhone()%> </td>  
	</tr>
	<tr>
	    <td style="font-weight:bold;"><label for="DISCRIPTION">DESCRIPTION: </label> </td> 
	    <td><%=sbm.getDescription() %> </td>
   </tr>
	
	<%
	 }
	
	%>
			
		   <tr><td colspan="2">&nbsp; <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
		   <tr><td colspan="2">&nbsp; <td></tr>
     </table>
    </div>

</body>
</html>


DAO-------
sco.java
public interface SocialBookMarkingDao {

	public void addSocialBookMarking(SocialBookMarking socialBookMarking) throws Exception;
	
	public void updateSocialBookMarking(SocialBookMarking socialBookMarking) throws Exception;
	
	public void deleteSocialBookMarking(int id) throws Exception;
	
	
	public SocialBookMarking  getSocialBookMarkingById(int id) throws Exception;
	
	public List<SocialBookMarking>  getSocialBookMarkingList() throws Exception;
	
	public List<SocialBookMarking>  getSocialBookMarkingList(int offset, int length) throws Exception;
}


Scoimpl.java
public class SocialBookMarkingDaoIml implements SocialBookMarkingDao
{

	private static List<SocialBookMarking> list = new ArrayList<SocialBookMarking>();
	
	public void addSocialBookMarking(SocialBookMarking socialBookMarking)
	{
			/*throws Exception {
		socialBookMarking.setId(list.size() + 1);
		list.add(socialBookMarking);*/
	Connection con = null;
	PreparedStatement ps = null; 
	try
	{
		con = DBConnection.getMySQLConnection();
		String insertQuery = "insert into seo.sbmtable(site,url,username,password,email,phoneno,description)values (?,?,?,?,?,?,?)";
		ps = con.prepareStatement(insertQuery);
		ps.setString(1, socialBookMarking.getSite());
		ps.setString(2, socialBookMarking.getUrl());
		ps.setString(3, socialBookMarking.getUsername());
		ps.setString(4, socialBookMarking.getPassword());
		ps.setString(5, socialBookMarking.getEmail());
		ps.setString(6, socialBookMarking.getPhone());
		ps.setString(7, socialBookMarking.getDescription());
		
		
		ps.executeUpdate();
		
		
	} catch(Exception e){
		e.printStackTrace();
	
		
	} finally
	{
		DBConnection.releaseStatement(ps);
		DBConnection.releaseConnection(con);
	}
		
	
		
	}

	public void updateSocialBookMarking(SocialBookMarking socialBookMarking)
			throws Exception
	{
		
		/*socialBookMarking.getId();
		list.add(socialBookMarking);*/
		
		//socialBookMarking.setId(list.size()-1 );
		//list.add(socialBookMarking);
		// TODO Auto-generated method stub
		
		Connection con = null;
		PreparedStatement ps = null; 
		try
		{
			con = DBConnection.getMySQLConnection();
			String insertQuery = "update seo.sbmtable set site=?,url=?,username=?,password=?,email=?,phoneno=?,description=? where id=?";
			ps = con.prepareStatement(insertQuery);
			ps.setString(1, socialBookMarking.getSite());
			ps.setString(2, socialBookMarking.getUrl());
			ps.setString(3, socialBookMarking.getUsername());
			ps.setString(4, socialBookMarking.getPassword());
			ps.setString(5, socialBookMarking.getEmail());
			ps.setString(6, socialBookMarking.getPhone());
			ps.setString(7, socialBookMarking.getDescription());
			ps.setInt(8, socialBookMarking.getId());
			
			
			ps.executeUpdate();
			
			
		} catch(Exception e)
		{
			e.printStackTrace();
		} finally 
		{
			DBConnection.releaseStatement(ps);
			DBConnection.releaseConnection(con);
		}
			
		
	}

	public void deleteSocialBookMarking(int id) throws Exception
	{
		
		/*if (list != null)
		{
			Iterator<SocialBookMarking> it = list.iterator();
			while(it.hasNext()) 
			{
				
				if (id == it.next().getId())
				{
					it.remove();
				}
			}
		}*/
		
		Connection con = null;
		PreparedStatement ps = null; 
		try
		{
			con = DBConnection.getMySQLConnection();
			String insertQuery = "delete from seo.sbmtable where id=?";
			ps = con.prepareStatement(insertQuery);
		
			ps.setInt(1, id);
			ps.executeUpdate();
			
			
		} catch(Exception e)
		{
			e.printStackTrace();
		} finally
		{
			DBConnection.releaseStatement(ps);
			DBConnection.releaseConnection(con);
		}
		
	}

	public SocialBookMarking  getSocialBookMarkingById(int id) throws Exception
	{
		
		/*if (list != null) {
			for (SocialBookMarking sbm : list) {
				if (id == sbm.getId()) {
					return sbm;
				}
			}
		}*/
		
		Connection con = null;
		PreparedStatement ps = null; 
		ResultSet rs = null;
		SocialBookMarking sbm =  null;
		try
		{
			con = DBConnection.getMySQLConnection();
			String insertQuery = "select id,site,url,username,password,email,phoneno,description from sbmtable where id =?";
			ps = con.prepareStatement(insertQuery);
			ps.setInt(1, id);
			
			
			rs = ps.executeQuery();
			if(rs.next()) 
			{
				 sbm = new SocialBookMarking();
				sbm.setId(rs.getInt("id"));
				sbm.setSite(rs.getString("site"));
				sbm.setUrl(rs.getString("url"));
				sbm.setUsername(rs.getString("username"));
				sbm.setPassword(rs.getString("password"));
				sbm.setEmail(rs.getString("email"));
				sbm.setPhone(rs.getString("phoneno"));
				sbm.setDescription(rs.getString("description"));
				
				
			}
			
		} catch(Exception e)
		{
			e.printStackTrace();
		} finally 
		{
			DBConnection.releaseStatement(ps);
			DBConnection.releaseConnection(con);
		}
		return sbm;
		
	}

	public List<SocialBookMarking> getSocialBookMarkingList() throws Exception
	{
		Connection con = null;
		PreparedStatement ps = null; 
		ResultSet rs = null;
		List<SocialBookMarking> sbmList = new ArrayList<SocialBookMarking>();
		try
		{
			con = DBConnection.getMySQLConnection();
			String insertQuery = "select * from sbmtable";
			ps = con.prepareStatement(insertQuery);
			//ps.setString(1, socialBookMarking.getUsername());
			
			
			rs = ps.executeQuery();
			while(rs.next())
			{
				SocialBookMarking sbm = new SocialBookMarking();
				sbm.setId(rs.getInt("id"));
				sbm.setSite(rs.getString("site"));
				sbm.setUrl(rs.getString("url"));
				sbm.setUsername(rs.getString("username"));
				sbm.setPassword(rs.getString("password"));
				sbm.setEmail(rs.getString("email"));
				sbm.setPhone(rs.getString("phoneno"));
				sbm.setDescription(rs.getString("description"));
				
				
				
				sbmList.add(sbm);
			}
			
		} catch(Exception e)
		{
			e.printStackTrace();
		} finally 
		{
			DBConnection.releaseStatement(ps);
			DBConnection.releaseConnection(con);
		}
		return sbmList;

		
	}

	public List<SocialBookMarking>  getSocialBookMarkingList(int offset, int length)
			throws Exception
	{
		Connection con = null;
		PreparedStatement ps = null; 
		ResultSet rs = null;
		List<SocialBookMarking> sbmList = new ArrayList<SocialBookMarking>();
		try
		{
			con = DBConnection.getMySQLConnection();
			String insertQuery = "select * from sbmtable where id=?  limit  ?, ?";
			ps = con.prepareStatement(insertQuery);
			//ps.setString(1, socialBookMarking.getUsername());
			
			
			rs = ps.executeQuery();
			while(rs.next())
			{
				SocialBookMarking sbm = new SocialBookMarking();
				
				sbm.setId(rs.getInt("id"));
				sbm.setSite(rs.getString("site"));
				sbm.setUrl(rs.getString("url"));
				sbm.setUsername(rs.getString("username"));
				sbm.setPassword(rs.getString("password"));
				sbm.setEmail(rs.getString("email"));
				sbm.setPhone(rs.getString("phoneno"));
				sbm.setDescription(rs.getString("description"));
				
				
				sbmList.add(sbm);
			}
			
		} catch(Exception e)
		{
			e.printStackTrace();
		} finally 
		{
			DBConnection.releaseStatement(ps);
			DBConnection.releaseConnection(con);
		}
		return sbmList;
		
	}

}



DTO.java
public class SocialBookMarking implements Serializable {

	private static final long serialVersionUID = 8074235133771981413L;
	private int id;
	private String site;
	/**
	 * @return the site
	 */
	public String getSite() {
		return site;
	}

	/**
	 * @param site the site to set
	 */
	public void setSite(String site) {
		this.site = site;
	}

	private String url;
	private String username;
	private String password;
	private String email;
	private String phone;
	private String description;
	

	public String getUsername() {
		return username;
	}

	public void setUsername(String username) {
		this.username = username;
	}

	public String getPassword() {
		return password;
	}

	public void setPassword(String password) {
		this.password = password;
	}

	public String getEmail() {
		return email;
	}

	public void setEmail(String email) {
		this.email = email;
	}

	public String getPhone() {
		return phone;
	}

	public void setPhone(String phone) {
		this.phone = phone;
	}

	public String getDescription() {
		return description;
	}

	public void setDescription(String description) {
		this.description = description;
	}

	public int getId() {
		return id;
	}

	public void setId(int id) {
		this.id = id;
	}

	public String getUrl() {
		return url;
	}

	public void setUrl(String url) {
		this.url = url;
	}

}


Web..servlet---frontcontroller.java
public class FrontControllerServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
      
	private SocialBookMarkingDao socialBookMarkingDao;
	private SMODao sMODao;
	private ClassifiedDao classifiedDao;
	private CredentialDao credentialDao;
	private DirectoryDao directoryDao;
	private QuestionDao questionsDao;
	

	
    /**
     * @see HttpServlet#HttpServlet()
     */
    public FrontControllerServlet() {
        super();
        // TODO Auto-generated constructor stub
        socialBookMarkingDao = new SocialBookMarkingDaoIml();
        sMODao=new SMODaoIml();
        classifiedDao=new ClassifiedDaoIml();
        credentialDao=new CredentialDaoIml();
        directoryDao=new DirectoryDaoIml();
        questionsDao=new QuestionDaoIml();
      
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {

		processRequest(request, response);

	}
	/**
	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException
	{
		processRequest(request,response);
	}
	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void processRequest(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		String nextAction = request.getParameter("nextAction");
		try{
		if (nextAction.startsWith("sbm")) {
			processSbmRequest(request, response, nextAction);
			}else if(nextAction.startsWith("smo"))	{
				processSmoRequest(request,response,nextAction);
				
			}else if(nextAction.startsWith("class")){
				processClassifiedRequest(request,response,nextAction);
			}else if(nextAction.startsWith("cred")){
				processCredentialRequest(request,response,nextAction);
			}else if(nextAction.startsWith("dir")){
				processDirectoryRequest(request,response,nextAction);
			}else if(nextAction.startsWith("ques")){
				processQuestionRequest(request,response,nextAction);
			}
		
			} catch (Exception e) {
				e.printStackTrace();
			// TODO: handle exception
		}
}

	private void processSbmRequest(HttpServletRequest request,HttpServletResponse response, String nextAction)
			throws ServletException, IOException, Exception {
		if (nextAction != null && "sbmAddShow".equalsIgnoreCase(nextAction))
		{
			
			System.out.println("Hi this is smy jso");
			//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			request.getRequestDispatcher(Constant.JSP_SBM_ADD_FORM).forward(request, response);
			
		}else if (nextAction != null && "sbmAdd".equalsIgnoreCase(nextAction))
		  {
			    SocialBookMarking sbm = InputCollector.getSocialBookMarkingDTO(request);
				List<String>errors=SBMValidator.validate(sbm);
				if (errors != null && errors.size() > 0) {
					request.setAttribute("errors", errors);
					request.getRequestDispatcher(Constant.JSP_SBM_ADD_FORM).forward(request, response); // "/WEB-INF/views/smo_add.jsp"
				} else {
					socialBookMarkingDao.addSocialBookMarking(sbm);
				request.setAttribute("list", socialBookMarkingDao.getSocialBookMarkingList());
				request.getRequestDispatcher(Constant.JSP_SBM_LISTVIEW_FORM).forward(request, response);
				}
		 }else if (nextAction != null && "sbmUpdateShow".equalsIgnoreCase(nextAction))
		   {
			String sid = request.getParameter("id");
			int id = Integer.parseInt(sid);
			SocialBookMarking sbm = socialBookMarkingDao.getSocialBookMarkingById(id);
			request.setAttribute("entity", sbm);
			request.getRequestDispatcher(Constant.JSP_SBM_UPDATE_FORM).forward(request, response);
			
		   }else if (nextAction != null && "sbmUpdate".equalsIgnoreCase(nextAction))
		     {
				SocialBookMarking sbm = new SocialBookMarking();
				sbm.setId(Integer.parseInt(request.getParameter("id")));
				sbm.setSite(request.getParameter("site"));
				sbm.setUrl(request.getParameter("url"));
				sbm.setUsername(request.getParameter("username"));
				sbm.setPassword(request.getParameter("password"));
				
				sbm.setEmail(request.getParameter("email"));
				
				sbm.setPhone(request.getParameter("phoneno"));
				sbm.setDescription(request.getParameter("description"));
				socialBookMarkingDao.updateSocialBookMarking(sbm);
				System.out.println("Hi this is smy jso");
				
				//List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
				request.setAttribute("list", socialBookMarkingDao.getSocialBookMarkingList());
				
				//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
				request.getRequestDispatcher(Constant.JSP_SBM_LISTVIEW_FORM).forward(request, response);
				
		     } else if (nextAction != null && "sbmView".equalsIgnoreCase(nextAction))
		       {
			
		        	String sid = request.getParameter("id");
		        	int id = Integer.parseInt(sid);
		        	SocialBookMarking sbm = socialBookMarkingDao.getSocialBookMarkingById(id);
			        request.setAttribute("entity", sbm);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
		        	request.getRequestDispatcher(Constant.JSP_SBM_VIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "sbmListView".equalsIgnoreCase(nextAction)) 
		       {
		 	
			         List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
			         request.setAttribute("list", sbmList);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			        request.getRequestDispatcher(Constant.JSP_SBM_LISTVIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "sbmDelete".equalsIgnoreCase(nextAction))
			   {
				String sid = request.getParameter("id");
				int id = Integer.parseInt(sid);
				 socialBookMarkingDao.deleteSocialBookMarking(id);
				 List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
		         request.setAttribute("list", sbmList);
				request.getRequestDispatcher(Constant.JSP_SBM_LISTVIEW_FORM).forward(request, response);
			   } else
		       {
			      request.getRequestDispatcher("/WEB-INF/views/test.jsp").forward(request, response);
		       }
	}
	
	private void processSmoRequest(HttpServletRequest request,HttpServletResponse response, String nextAction)
			throws ServletException, IOException, Exception {
		if (nextAction != null && "smoAddShow".equalsIgnoreCase(nextAction))
		{
			
			System.out.println("Hi this is smy jso");
			//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			request.getRequestDispatcher(Constant.JSP_SMO_ADD_FORM).forward(request, response);
			
		}else if (nextAction != null && "smoAdd".equalsIgnoreCase(nextAction))
		  {
				SMO smo = InputCollector.getSmoDTO(request);
				List<String> errors = SmoValidator.validate(smo);
				if (errors != null && errors.size() > 0) {
					request.setAttribute("errors", errors);
					request.getRequestDispatcher(Constant.JSP_SMO_ADD_FORM).forward(request, response); // "/WEB-INF/views/smo_add.jsp"
				} else {
					sMODao.addSMO(smo);
					request.setAttribute("list", sMODao.getSMOList());
					request.getRequestDispatcher(Constant.JSP_SMO_LISTVIEW_FORM).forward(request, response);
				}
				
				
		 } else if (nextAction != null && "smoUpdateShow".equalsIgnoreCase(nextAction))
		   {
			String sid = request.getParameter("id");
			int id = Integer.parseInt(sid);
			SMO smo = sMODao.getSMOById(id);
			request.setAttribute("entity", smo);
			request.getRequestDispatcher(Constant.JSP_SMO_UPDATE_FORM).forward(request, response);
			
		   } else if (nextAction != null && "smoUpdate".equalsIgnoreCase(nextAction))
		     {
				SMO smo = new SMO();
				smo.setId(Integer.parseInt(request.getParameter("id")));
				smo.setSite(request.getParameter("site"));
				smo.setUrl(request.getParameter("url"));
				smo.setUsername(request.getParameter("username"));
				smo.setPassword(request.getParameter("password"));
				
				smo.setDescription(request.getParameter("description"));
				sMODao.updateSMO(smo);
				System.out.println("Hi this is smy jso");
				
				//List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
				request.setAttribute("list", sMODao.getSMOList());
				
				//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
				request.getRequestDispatcher(Constant.JSP_SMO_LISTVIEW_FORM).forward(request, response);
				
		     } else if (nextAction != null && "smoView".equalsIgnoreCase(nextAction))
		       {
			
		        	String sid = request.getParameter("id");
		        	int id = Integer.parseInt(sid);
		        	SMO smo = sMODao.getSMOById(id);
			        request.setAttribute("entity", smo);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
		        	request.getRequestDispatcher(Constant.JSP_SMO_VIEW_FORM).forward(request, response);
		
		       }else if (nextAction != null && "smoListView".equalsIgnoreCase(nextAction)) 
		       {
		 	
			         List<SMO> smoList = sMODao.getSMOList();
			         request.setAttribute("list", smoList);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			        request.getRequestDispatcher(Constant.JSP_SMO_LISTVIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "smoDelete".equalsIgnoreCase(nextAction))
			   {
				String sid = request.getParameter("id");
				int id = Integer.parseInt(sid);
				 sMODao.deleteSMO(id);
				 List<SMO> smoList = sMODao.getSMOList();
		         request.setAttribute("list", smoList);
				request.getRequestDispatcher(Constant.JSP_SMO_LISTVIEW_FORM).forward(request, response);
			   } else
		       {
			      request.getRequestDispatcher("/WEB-INF/views/test.jsp").forward(request, response);
		       }
	}

	private void processClassifiedRequest(HttpServletRequest request,HttpServletResponse response, String nextAction)
			throws ServletException, IOException, Exception {
		if (nextAction != null && "classAddShow".equalsIgnoreCase(nextAction))
		{
			
			System.out.println("Hi this is smy jso");
			//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			request.getRequestDispatcher(Constant.JSP_CLASSIFIED_ADD_FORM).forward(request, response);
			
		}else if (nextAction != null && "classAdd".equalsIgnoreCase(nextAction))
		  {
			
			Classified smo = InputCollector.getClassifiedDTO(request);
			List<String> errors = ClassifiedValidator.validate(smo);
			if (errors != null && errors.size() > 0) {
				request.setAttribute("errors", errors);
				request.getRequestDispatcher(Constant.JSP_CLASSIFIED_ADD_FORM).forward(request, response); // "/WEB-INF/views/smo_add.jsp"
			} else {
				classifiedDao.addClassified(smo);
				request.setAttribute("list", classifiedDao.getClassifiedList());
				request.getRequestDispatcher(Constant.JSP_CLASSIFIED_LISTVIEW_FORM).forward(request, response);
			}
			
				
		 }else if (nextAction != null && "classUpdateShow".equalsIgnoreCase(nextAction))
		   {
			String sid = request.getParameter("id");
			int id = Integer.parseInt(sid);
			Classified sbm = classifiedDao.getClassifiedById(id);
			request.setAttribute("entity", sbm);
			request.getRequestDispatcher(Constant.JSP_CLASSIFIED_UPDATE_FORM).forward(request, response);
			
		   }else if (nextAction != null && "classUpdate".equalsIgnoreCase(nextAction))
		     {
			   Classified sbm = new Classified();
				sbm.setId(Integer.parseInt(request.getParameter("id")));
				sbm.setSite(request.getParameter("site"));
				sbm.setUrl(request.getParameter("url"));
				sbm.setUsername(request.getParameter("username"));
				sbm.setPassword(request.getParameter("password"));
				sbm.setDescription(request.getParameter("description"));
				classifiedDao.updateClassified(sbm);
				
				//List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
				request.setAttribute("list", classifiedDao.getClassifiedList());
				
				//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
				request.getRequestDispatcher(Constant.JSP_CLASSIFIED_LISTVIEW_FORM).forward(request, response);
				
		     } else if (nextAction != null && "classView".equalsIgnoreCase(nextAction))
		       {
			
		        	String sid = request.getParameter("id");
		        	int id = Integer.parseInt(sid);
		        	Classified sbm = classifiedDao.getClassifiedById(id);
			        request.setAttribute("entity", sbm);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
		        	request.getRequestDispatcher(Constant.JSP_CLASSIFIED_VIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "classListView".equalsIgnoreCase(nextAction)) 
		       {
		 	
			         List<Classified> sbmList = classifiedDao.getClassifiedList();
			         request.setAttribute("list", sbmList);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			        request.getRequestDispatcher(Constant.JSP_CLASSIFIED_LISTVIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "classDelete".equalsIgnoreCase(nextAction))
			   {
				String sid = request.getParameter("id");
				int id = Integer.parseInt(sid);
				 classifiedDao.deleteClassified(id);
				 List<Classified> sbmList = classifiedDao.getClassifiedList();
		         request.setAttribute("list", sbmList);
				request.getRequestDispatcher(Constant.JSP_CLASSIFIED_LISTVIEW_FORM).forward(request, response);
			   } else
		       {
			      request.getRequestDispatcher("/WEB-INF/views/test.jsp").forward(request, response);
		       }
	}
	private void processCredentialRequest(HttpServletRequest request,HttpServletResponse response, String nextAction)
			throws ServletException, IOException, Exception {
		if (nextAction != null && "credAddShow".equalsIgnoreCase(nextAction))
		{
			
			System.out.println("Hi this is smy jso");
			//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			request.getRequestDispatcher(Constant.JSP_CREDENTIAL_ADD_FORM).forward(request, response);
			
		}else if (nextAction != null && "credAdd".equalsIgnoreCase(nextAction))
		  {
			
			Credential smo = InputCollector.getCredentialDTO(request);
			List<String> errors = CredentialValidator.validate(smo);
			if (errors != null && errors.size() > 0) {
				request.setAttribute("errors", errors);
				request.getRequestDispatcher(Constant.JSP_CREDENTIAL_ADD_FORM).forward(request, response); // "/WEB-INF/views/smo_add.jsp"
			} else {
				credentialDao.addCredential(smo);
				request.setAttribute("list", classifiedDao.getClassifiedList());
				request.getRequestDispatcher(Constant.JSP_CREDENTIAL_LISTVIEW_FORM).forward(request, response);
			}
				
		 }else if (nextAction != null && "credUpdateShow".equalsIgnoreCase(nextAction))
		   {
			String sid = request.getParameter("id");
			int id = Integer.parseInt(sid);
			Credential sbm = credentialDao.getCredentialById(id);
			request.setAttribute("entity", sbm);
			request.getRequestDispatcher(Constant.JSP_CREDENTIAL_UPDATE_FORM).forward(request, response);
			
		   }else if (nextAction != null && "credUpdate".equalsIgnoreCase(nextAction))
		     {
			    Credential sbm = new Credential();
				sbm.setId(Integer.parseInt(request.getParameter("id")));
				sbm.setSite(request.getParameter("site"));
				sbm.setUrl(request.getParameter("url"));
				sbm.setUsername(request.getParameter("username"));
				sbm.setPassword(request.getParameter("password"));
				
				sbm.setEmail(request.getParameter("email"));
				
				sbm.setPhone(request.getParameter("phoneno"));
				sbm.setDescription(request.getParameter("description"));
				
				sbm.setType(request.getParameter("type"));
				
				credentialDao.updateCredential(sbm);
				System.out.println("Hi this is smy jso");
				
				//List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
				request.setAttribute("list", credentialDao.getCredentialList());
				
				//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
				request.getRequestDispatcher(Constant.JSP_CREDENTIAL_LISTVIEW_FORM).forward(request, response);
				
		     } else if (nextAction != null && "credView".equalsIgnoreCase(nextAction))
		       {
			
		        	String sid = request.getParameter("id");
		        	int id = Integer.parseInt(sid);
		        	Credential sbm = credentialDao.getCredentialById(id);
			        request.setAttribute("entity", sbm);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
		        	request.getRequestDispatcher(Constant.JSP_CREDENTIAL_VIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "credListView".equalsIgnoreCase(nextAction)) 
		       {
		 	
			         List<Credential> sbmList = credentialDao.getCredentialList();
			         request.setAttribute("list", sbmList);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			        request.getRequestDispatcher(Constant.JSP_CREDENTIAL_LISTVIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "credDelete".equalsIgnoreCase(nextAction))
			   {
				String sid = request.getParameter("id");
				int id = Integer.parseInt(sid);
				credentialDao.deleteCredential(id);
				 List<Credential> sbmList = credentialDao.getCredentialList();
		         request.setAttribute("list", sbmList);
				request.getRequestDispatcher(Constant.JSP_CREDENTIAL_LISTVIEW_FORM).forward(request, response);
			   } else
		       {
			      request.getRequestDispatcher("/WEB-INF/views/test.jsp").forward(request, response);
		       }
	}
	private void processDirectoryRequest(HttpServletRequest request,HttpServletResponse response, String nextAction)
			throws ServletException, IOException, Exception {
		if (nextAction != null && "dirAddShow".equalsIgnoreCase(nextAction))
		{
			
			System.out.println("Hi this is smy jso");
			//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			request.getRequestDispatcher(Constant.JSP_DIRECTORY_ADD_FORM).forward(request, response);
			
		}else if (nextAction != null && "dirAdd".equalsIgnoreCase(nextAction))
		  {
			
			
			
			
			Directory smo = InputCollector.getDirectoryDTO(request);
			List<String> errors = DirectoryValidator.validate(smo);
			if (errors != null && errors.size() > 0) {
				request.setAttribute("errors", errors);
				request.getRequestDispatcher(Constant.JSP_DIRECTORY_ADD_FORM).forward(request, response); // "/WEB-INF/views/smo_add.jsp"
			} else {
				directoryDao.addDirectory(smo);
				request.setAttribute("list", directoryDao.getDirectoryList());
				request.getRequestDispatcher(Constant.JSP_DIRECTORY_LISTVIEW_FORM).forward(request, response);
			}
						
		  }else if (nextAction != null && "dirUpdateShow".equalsIgnoreCase(nextAction))
		   {
			String sid = request.getParameter("id");
			int id = Integer.parseInt(sid);
			Directory directory = directoryDao.getDirectoryById(id);
			request.setAttribute("entity", directory);
			request.getRequestDispatcher(Constant.JSP_DIRECTORY_UPDATE_FORM).forward(request, response);
			
		   }else if (nextAction != null && "dirUpdate".equalsIgnoreCase(nextAction))
		     {
			        Directory sbm = new Directory();
				    sbm.setId(Integer.parseInt(request.getParameter("id")));
				    sbm.setSite(request.getParameter("site"));
				    sbm.setTitle(request.getParameter("title"));
				    sbm.setUrl(request.getParameter("url"));
					sbm.setUsername(request.getParameter("username"));
					sbm.setEmail(request.getParameter("email"));
					sbm.setDescription(request.getParameter("description"));
					sbm.setCatogrey(request.getParameter("catogrey"));
					sbm.setBulkUpload(request.getParameter("bulkUpload"));
					sbm.setFileName(request.getParameter("fileName"));
					
				directoryDao.updateDirectory(sbm);
				System.out.println("Hi this is smy jso");
				
				//List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
				request.setAttribute("list", directoryDao.getDirectoryList());
				
				//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
				request.getRequestDispatcher(Constant.JSP_DIRECTORY_LISTVIEW_FORM).forward(request, response);
				
		    	
		      } else if (nextAction != null && "dirView".equalsIgnoreCase(nextAction))
		       {
			
		        	String sid = request.getParameter("id");
		        	int id = Integer.parseInt(sid);
		        	Directory sbm = directoryDao.getDirectoryById(id);
			        request.setAttribute("entity", sbm);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
		        	request.getRequestDispatcher(Constant.JSP_DIRECTORY_VIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "dirListView".equalsIgnoreCase(nextAction)) 
		       {
		 	
			         List<Directory> sbmList = directoryDao.getDirectoryList();
			         request.setAttribute("list", sbmList);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			        request.getRequestDispatcher(Constant.JSP_DIRECTORY_LISTVIEW_FORM).forward(request, response);
		
		       }else  if (nextAction != null && "dirDelete".equalsIgnoreCase(nextAction))
			   {
				String sid = request.getParameter("id");
				int id = Integer.parseInt(sid);
				directoryDao.deleteDirectory(id);
				 List<Directory> sbmList = directoryDao.getDirectoryList();
		         request.setAttribute("list", sbmList);
				request.getRequestDispatcher(Constant.JSP_DIRECTORY_LISTVIEW_FORM).forward(request, response);
			   } else
		       {
			     // request.getRequestDispatcher("/WEB-INF/views/test.jsp").forward(request, response);
			      request.getRequestDispatcher("invalidPage.jsp").forward(request, response);
		       }
	}
	
	private void processQuestionRequest(HttpServletRequest request,HttpServletResponse response, String nextAction)
			throws ServletException, IOException, Exception {
		if (nextAction != null && "quesAddShow".equalsIgnoreCase(nextAction))
		{
			
			System.out.println("Hi this is smy jso");
			//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			request.getRequestDispatcher("/WEB-INF/views/question_add.jsp").forward(request, response);
			
		}else if (nextAction != null && "quesAdd".equalsIgnoreCase(nextAction))
		  {
				Questions sbm = new Questions();
				sbm.setCategory(request.getParameter("category"));
				sbm.setQuestion(request.getParameter("question"));
				sbm.setAnswer(request.getParameter("answer"));
				sbm.setCreatedAt(request.getParameter("createdAt"));
				sbm.setCreatedBy(request.getParameter("createdBy"));
				questionsDao.addQuestion(sbm);
				System.out.println("Hi this is smy jso");
				request.setAttribute("list", questionsDao.getQuestionsList());
				request.getRequestDispatcher("/WEB-INF/views/question_viewlist.jsp").forward(request, response);
				
		 }else if (nextAction != null && "quesUpdateShow".equalsIgnoreCase(nextAction))
		   {
			String sid = request.getParameter("id");
			int id = Integer.parseInt(sid);
			Questions sbm = questionsDao.getQuestionsById(id);
			request.setAttribute("entity", sbm);
			request.getRequestDispatcher("/WEB-INF/views/question_update.jsp").forward(request, response);
			
		   }else if (nextAction != null && "quesUpdate".equalsIgnoreCase(nextAction))
		     {
			   Questions sbm = new Questions();
				sbm.setId(Integer.parseInt(request.getParameter("id")));
				sbm.setCategory(request.getParameter("category"));
				sbm.setQuestion(request.getParameter("question"));
				sbm.setAnswer(request.getParameter("answer"));
				sbm.setCreatedAt(request.getParameter("createdAt"));
				sbm.setCreatedBy(request.getParameter("createdBy"));
				questionsDao.updateQuestion(sbm);
				System.out.println("Hi this is smy jso");
				
				//List<SocialBookMarking> sbmList = socialBookMarkingDao.getSocialBookMarkingList();
				request.setAttribute("list", questionsDao.getQuestionsList());
				
				//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
				request.getRequestDispatcher("/WEB-INF/views/question_viewlist.jsp").forward(request, response);
				
		     } else if (nextAction != null && "quesView".equalsIgnoreCase(nextAction))
		       {
			
		        	String sid = request.getParameter("id");
		        	int id = Integer.parseInt(sid);
		        	Questions sbm = questionsDao.getQuestionsById(id);
			        request.setAttribute("entity", sbm);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
		        	request.getRequestDispatcher("/WEB-INF/views/question_view.jsp").forward(request, response);
		
		       }else  if (nextAction != null && "quesListView".equalsIgnoreCase(nextAction)) 
		       {
		 	
			         List<Questions> sbmList = questionsDao.getQuestionsList();
			         request.setAttribute("list", sbmList);
			
		        	//request.getRequestDispatcher("firstexample.jsp").forward(request, response);
			        request.getRequestDispatcher("/WEB-INF/views/question_viewlist.jsp").forward(request, response);
		
		       }else  if (nextAction != null && "quesDelete".equalsIgnoreCase(nextAction))
			   {
				String sid = request.getParameter("id");
				int id = Integer.parseInt(sid);
				questionsDao.deleteQuestion(id);
				 List<Questions> sbmList = questionsDao.getQuestionsList();
		         request.setAttribute("list", sbmList);
				request.getRequestDispatcher("/WEB-INF/views/question_viewlist.jsp").forward(request, response);
			   } else
		       {
			      request.getRequestDispatcher("/WEB-INF/views/test.jsp").forward(request, response);
		       }
	}
	

	
}



Utils.java
Constant.java
public class Constant {

	
	public static final String[] NEXT_ACTION_ARRAYS = {"sbmAddShow", "sbmAdd","sbmListView","sbmView","sbmUpdateShow",
		                                                "sbmUpdate","sbmDelete","classAddShow", "classAdd","classListView",
		                                                "classView","classUpdateShow","classUpdate","classDelete",
				                                        "credAddShow", "credAdd","credListView","credView","credUpdateShow",
				                                        "credUpdate","credDelete","dirAddShow", "dirAdd","dirListView","dirView",
				                                        "dirUpdateShow","dirUpdate","dirDelete","smoAddShow", "smoAdd",
				                                        "smoListView","smoView","smoUpdateShow","smoUpdate","smoDelete",
				                                        "quesAddShow","quesAdd","quesListView","quesView","quesUpdateShow",
		                                                "quesUpdate","quesDelete"
				                                       };
	
	
	public static final String[] NEXT_ACTION_AUTHEN_ARRAYS = {"dirAddShow","dirAdd","dirListView","dirView","dirUpdateShow","dirUpdate","dirDelete"};
	public static final String[] NEXT_ACTION_UNAUTHEN_ARRAYS = {"login","logout"};
	
	// jsp page name
	public static final String JSP_PREFIX = "/WEB-INF/views/";
	public static final String JSP_SMO_ADD_FORM = JSP_PREFIX + "smo_add.jsp";
	public static final String JSP_SMO_UPDATE_FORM = JSP_PREFIX + "smo_update.jsp";
	public static final String JSP_SMO_LISTVIEW_FORM = JSP_PREFIX + "smo_listview.jsp";
	public static final String JSP_SMO_VIEW_FORM = JSP_PREFIX + "smo_view.jsp";
	
	public static final String JSP_SBM_ADD_FORM = JSP_PREFIX + "socialbookmarking_add.jsp";
	public static final String JSP_SBM_UPDATE_FORM = JSP_PREFIX + "socialbookmarking_update.jsp";
	public static final String JSP_SBM_LISTVIEW_FORM = JSP_PREFIX + "socialbookmarking_listview.jsp";
	public static final String JSP_SBM_VIEW_FORM = JSP_PREFIX + "socialbookmarking_view.jsp";
	
	public static final String JSP_CREDENTIAL_ADD_FORM = JSP_PREFIX + "credential_add.jsp";
	public static final String JSP_CREDENTIAL_UPDATE_FORM = JSP_PREFIX + "credential_update.jsp";
	public static final String JSP_CREDENTIAL_LISTVIEW_FORM = JSP_PREFIX + "credential_listview.jsp";
	public static final String JSP_CREDENTIAL_VIEW_FORM = JSP_PREFIX + "credential_view.jsp";
	
	public static final String JSP_CLASSIFIED_ADD_FORM = JSP_PREFIX + "classified_add.jsp";
	public static final String JSP_CLASSIFIED_UPDATE_FORM = JSP_PREFIX + "classified_update.jsp";
	public static final String JSP_CLASSIFIED_LISTVIEW_FORM = JSP_PREFIX + "classified_listview.jsp";
	public static final String JSP_CLASSIFIED_VIEW_FORM = JSP_PREFIX + "classified_view.jsp";
	
	public static final String JSP_DIRECTORY_ADD_FORM = JSP_PREFIX + "directory_add.jsp";
	public static final String JSP_DIRECTORY_UPDATE_FORM = JSP_PREFIX + "directory_update.jsp";
	public static final String JSP_DIRECTORY_LISTVIEW_FORM = JSP_PREFIX + "directory_listview.jsp";
	public static final String JSP_DIRECTORY_VIEW_FORM = JSP_PREFIX + "directory_view.jsp";
	
	
	
	
	// ERROR MESSAGE
	
	//public static final String JSP_SMO_ADD_FORM = "smo_add.jsp";
}
Inputcollector.java
public class InputCollector {

	public static SMO getSmoDTO(HttpServletRequest request) {
		SMO smo = new SMO();
		try {
			smo.setSite(request.getParameter("site"));
			smo.setUrl(request.getParameter("url"));
			smo.setUsername(request.getParameter("username"));
			smo.setPassword(request.getParameter("password"));
			smo.setDescription(request.getParameter("description"));
			
		} catch (Exception e) {
			
		}
		
		return smo;
	}
	
	public static Credential getCredentialDTO(HttpServletRequest request) {
		Credential credential = new Credential();
		try {
			 
			  credential.setSite(request.getParameter("site"));
			  credential.setUrl(request.getParameter("url"));
			  credential.setUsername(request.getParameter("username"));
			  credential.setPassword(request.getParameter("password"));
			  credential.setEmail(request.getParameter("email"));
			  credential.setPhone(request.getParameter("phoneno"));
			  credential.setDescription(request.getParameter("description"));
			  credential.setType(request.getParameter("type"));
				
			
		} catch (Exception e) {
			
		}
		
		return credential;
	}
	
	public static SocialBookMarking getSocialBookMarkingDTO(HttpServletRequest request) {
		SocialBookMarking sbm = new SocialBookMarking();
		try {
			
			sbm.setUsername(request.getParameter("username"));
			sbm.setPassword(request.getParameter("password"));
			sbm.setUrl(request.getParameter("url"));
			sbm.setEmail(request.getParameter("email"));
			sbm.setSite(request.getParameter("site"));
			sbm.setPhone(request.getParameter("phoneno"));
			sbm.setDescription(request.getParameter("description"));
			
			
		} catch (Exception e) {
			
		}
		
		return sbm;
	}
	
	public static Classified getClassifiedDTO(HttpServletRequest request) {
		Classified clas = new Classified();
		try {
			
			clas.setSite(request.getParameter("site"));
			clas.setUrl(request.getParameter("url"));
			clas.setUsername(request.getParameter("username"));
			clas.setPassword(request.getParameter("password"));
			clas.setDescription(request.getParameter("description"));
			
		} catch (Exception e) {
			
		}
		
		return clas;
	}
	
	public static Directory getDirectoryDTO(HttpServletRequest request) {
		Directory dir = new Directory();
		try {
			 
			dir.setSite(request.getParameter("site"));
			dir.setTitle(request.getParameter("title"));
			dir.setUrl(request.getParameter("url"));
			dir.setUsername(request.getParameter("username"));
			dir.setEmail(request.getParameter("email"));
			dir.setDescription(request.getParameter("description"));
			dir.setCatogrey(request.getParameter("catogrey"));
			dir.setBulkUpload(request.getParameter("bulkUpload"));
			dir.setFileName(request.getParameter("fileName"));
				
			
		} catch (Exception e) {
			
		}
		
		return dir;
	}
}

DBConnection.java
public class DBConnection {
	    
	//private static Log logger = LogFactory.getLog(DBConnection.class);
	    
	
	/**
	 * This method release the database connection  
	 * @param aConnection
	 * @throws SQLException
	 */
	public static void releaseConnection(Connection aConnection) {
		if (aConnection != null)
			try {
				aConnection.close();
				aConnection = null;
			} catch (SQLException e) {
				//logger.error("releaseConnection():Error in closing connection"+e.getMessage());
			}
	}

	/**
	 * This method release the database Statement  
	 * @param aConnection
	 * @throws SQLException
	 */
	public static void releaseStatement(Statement aStatement) {
		if (aStatement != null)
			try {
				aStatement.close();
				aStatement = null;
			} catch (SQLException e) {
				//logger.error("releaseStatement():Error in closing statement"+e.getMessage());
			}
	}

	/**
	 * This method release the ResultSet  
	 * @param aConnection
	 * @throws SQLException
	 */
	public static void releaseResultSet(ResultSet aResultSet) {
		if (aResultSet != null)
			try {
				aResultSet.close();
				aResultSet = null;
			} catch (SQLException e) {
				//logger.error("releaseResultSet(): Error in closing resultset"+e.getMessage());
			}
	}
	
	/** 
	 * This method is used get {@link Connection} from MySQL database.
	 *  
	 */
	public static Connection getMySQLConnection() {
		
		// See your driver documentation for the proper format of this string :
		String url = "jdbc:mysql://localhost:3306/seo";
		 
		// Provided by your driver documentation. In this case, a MySql driver is used :
		String DRIVER_CLASS_NAME = "com.mysql.jdbc.Driver";
		String USER_NAME = "root";
		String PASSWORD = "root";
		
		Connection result = null;
		try {
			Class.forName(DRIVER_CLASS_NAME).newInstance();
		} catch (Exception ex) {
			log("Check classpath. Cannot load db driver: " + DRIVER_CLASS_NAME);
		}

		try {
			result = DriverManager.getConnection(url, USER_NAME, PASSWORD);
		} catch (SQLException e) {
			log("Driver loaded, but cannot connect to db: " + url);
		} finally {
			url = null;
			DRIVER_CLASS_NAME = null;
			USER_NAME = null;
			PASSWORD = null;
		}
		return result;
	}

	/** 
	 * This method is used get {@link Connection} 
	 * Uses DriverManager. 
	 */
	public static Connection getOracleConnection() {
		
		// See your driver documentation for the proper format of this string :
		//String DB_CONN_STRING = "jdbc:mysql://localhost:3306/healthacedb_prod";
		 //Class.forName ("oracle.jdbc.driver.OracleDriver");
         //Connection conn = DriverManager.getConnection("jdbc:oracle:thin:@//localhost:1521/orcl", "scott", "tiger");
	      // @//machineName:port/SID,   userid,  password

		 String url = "jdbc:oracle:thin:@192.168.3.39:1521:epny";
		// Provided by your driver documentation. In this case, a MySql driver is used :
		String DRIVER_CLASS_NAME = "oracle.jdbc.driver.OracleDriver";
		String USER_NAME = "mcrm_mstr";
		String PASSWORD = "mcrm_mstr";

		Connection result = null;
		try {
			Class.forName(DRIVER_CLASS_NAME).newInstance();
		} catch (Exception ex) {
			log("Check classpath. Cannot load db driver: " + DRIVER_CLASS_NAME);
		}

		try {
			result = DriverManager.getConnection(url, USER_NAME, PASSWORD);
		} catch (SQLException e) {
			log("Driver loaded, but cannot connect to db: " + url);
		} finally {
			url = null;
			DRIVER_CLASS_NAME = null;
			USER_NAME = null;
			PASSWORD = null;
		}
		return result;
	}
	
	

	private static void log(Object aObject){
	    System.out.println(aObject);
	}

	
	/*public static void main(String[] args) {
		try {
			//Connection conn = getOracleConnection();
			Connection conn = getMySQLConnection();
			if (conn != null) {
				System.out.println("Connecton got");
			} else {
				System.out.println("Connecton not found");
			}
			
		} catch (Exception e) {
			System.out.println("exception : " + e.getMessage());
		}
	}*/
	
	public static Connection dummyConnection () {
		Connection connection = null;
		try {
		    // Load the JDBC driver
		    String driverName = "oracle.jdbc.driver.OracleDriver";
		    Class.forName(driverName);

		    // Create a connection to the database jdbc:oracle:thin:@192.168.3.39:1521:epny
		    String serverName = "192.168.3.80";
		    String portNumber = "1521";
		    String sid = "SAAS_DUMMY";
		    //String url = "jdbc:oracle:thin:@" + serverName + ":" + portNumber + ":" + sid;
		    String url = "jdbc:oracle:thin:@192.168.3.39:1521:epny";
		    //String url = "jdbc:oracle:thin:@192.168.3.80:1521:SAAS_DUMMY";
		    String username = "mcrm_mstr";
		    String password = "mcrm_mstr";
		    System.out.println("befor connection");
		    connection = DriverManager.getConnection(url, username, password);
		    System.out.println("after connection");
		} catch (ClassNotFoundException e) {
		    System.out.println(e.getMessage());
		    e.printStackTrace();
		} catch (SQLException e) {
		    // Could not connect to the database
			System.out.println(e.getMessage());
			e.printStackTrace();
		} catch (Exception  e) {
			System.out.println(e.getMessage());
			e.printStackTrace();
		}
		return connection;

	}
	
	/**
	 * This method is used to get the connectin for the different data store.
	 * 
	 * @return {@link Connection}
	 */
	public static Connection getConnection() {
		Connection conn = null;
		try {
			conn = getOracleConnection();
		} catch (Exception e) {
			System.out.println(e.getMessage());
		}
		return conn;
	}
}


Web.validator
Sbmvalidator.java
public class SBMValidator {
	public static List<String> validate(SocialBookMarking sbm) {
		List<String> errors = new ArrayList<String>();
		try {
			if (ValidatorRule.isEmpty(sbm.getSite())) {
				errors.add("Site must not be blank.");
			}
			if(ValidatorRule.isEmpty(sbm.getUrl())){
				errors.add("Url must not blank");
			} if(ValidatorRule.isEmpty(sbm.getUsername())){
				errors.add("Username must not be blank");
			}else if(ValidatorRule.isEmpty(sbm.getPassword())){
				errors.add("Password must not blank");
			}else if(ValidatorRule.isEmpty(sbm.getEmail())){
				errors.add("Email must not blank");
			}else if(ValidatorRule.isEmpty(sbm.getPhone())){
				errors.add("Phone no must not blank");
			}
		} catch (Exception e) {
			// TODO: handle exception
		}
		
		return errors;
	}
}
validatorRule.java
public class ValidatorRule {

	
	public static boolean isEmpty(String input) {
		boolean isEmpty = false;
		
		if (input == null || "".equals(input.trim())) {
			isEmpty = true;
		}
		
		return isEmpty;
	}
}
Web.filter
UrlValidatorFilter.java
public class UrlValidatorFilter implements Filter {

    /**
     * Default constructor. 
     */
    public UrlValidatorFilter() {
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see Filter#destroy()
	 */
	public void destroy() {
		// TODO Auto-generated method stub
	}

	/**
	 * @see Filter#doFilter(ServletRequest, ServletResponse, FilterChain)
	 */
	public void doFilter(ServletRequest request, ServletResponse response, FilterChain chain) throws IOException, ServletException {
		// TODO Auto-generated method stub
		// place your code here

		// pass the request along the filter chain
		
		HttpServletRequest req = (HttpServletRequest) request;
        HttpServletResponse resp = (HttpServletResponse) response;
        HttpSession session = req.getSession();
        String sesionValue = null;
        if(session != null) {
        	sesionValue = (String)session.getAttribute("name");
		}
		String nextAction = request.getParameter("nextAction");
		if (isFound(Constant.NEXT_ACTION_AUTHEN_ARRAYS, nextAction)) {
			if (sesionValue == null) {
				request.setAttribute("msg", "You are not logged-in so not authorized to view this page.");
				request.getRequestDispatcher("login.jsp").forward(request, response);
			} 
		} else if (isFound(Constant. NEXT_ACTION_UNAUTHEN_ARRAYS, nextAction)) {
			System.out.println("login action");
			//request.getRequestDispatcher("login.jsp").forward(request, response);
		} else {
			request.setAttribute("msg", "nextAction paramete is  not valid (URL is not valid.)");
			request.getRequestDispatcher("login.jsp").forward(request, response);
		}
		chain.doFilter(request, response);
		
	}
	private boolean isFound(String[] strArray, String key) {
		boolean isFound = false;
		try {
			for (String s : strArray) {
				if (s.equals(key)) {
					isFound = true;
					break;
				}
			}
		} catch (Exception e) {
			System.out.println("Excpetion found : " + e.getMessage());
		}
		
		return isFound;
	}
	/**
	 * @see Filter#init(FilterConfig)
	 */
	public void init(FilterConfig fConfig) throws ServletException {
		// TODO Auto-generated method stub
	}

}

Seo.service
Socialservice.java
public interface SocialBookMarkingService {

	public void addSocialBookMarking(SocialBookMarking socialBookMarking) throws Exception;
	
	public void updateSocialBookMarking(SocialBookMarking socialBookMarking) throws Exception;
	
	public void deleteSocialBookMarking(int id) throws Exception;
	
	
	public SocialBookMarking  getSocialBookMarkingById(int id) throws Exception;
	
	public List<SocialBookMarking>  getSocialBookMarkingList() throws Exception;
	
	public List<SocialBookMarking>  getSocialBookMarkingList(int offset, int length) throws Exception;
}


Socialseviceimpl.java
public class SocialBookMarkingServiceImpl implements SocialBookMarkingService{

	private SocialBookMarkingDao socialBookMarkingDao = null;
	
	private SocialBookMarkingServiceImpl() {
		socialBookMarkingDao = new SocialBookMarkingDaoIml();
	}
	
	public void addSocialBookMarking(SocialBookMarking socialBookMarking)
			throws Exception {
		socialBookMarkingDao.addSocialBookMarking(socialBookMarking);
		
	}

	public void updateSocialBookMarking(SocialBookMarking socialBookMarking)
			throws Exception {
		// TODO Auto-generated method stub
		
	}

	public void deleteSocialBookMarking(int id) throws Exception {
		// TODO Auto-generated method stub
		
	}

	public SocialBookMarking getSocialBookMarkingById(int id) throws Exception {
		// TODO Auto-generated method stub
		return null;
	}

	public List<SocialBookMarking> getSocialBookMarkingList() throws Exception {
		// TODO Auto-generated method stub
		return null;
	}

	public List<SocialBookMarking> getSocialBookMarkingList(int offset,
			int length) throws Exception {
		// TODO Auto-generated method stub
		return null;
	}

}


 
