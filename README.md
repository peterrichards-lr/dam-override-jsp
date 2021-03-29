# dam-override-jsp
 
This module is a OSGi fragment which overrides the view_entries.jsp to introduce an Upload button. More information on OSGi fragments or other methods of customising JSP can be found at the following link.

[Introduction to Customizing JSPs](https://help.liferay.com/hc/en-us/articles/360028808292-Introduction-to-Customizing-JSPs)

The reason this overrides the *view_entries.jsp* is because we want the button to take into account the folder in which the action is taken.

In addition, a call to the Document Library permissions helper ([DLFolderPermission](https://github.com/liferay/liferay-portal/blob/11e6081f96abb6bf299369519434c1eafa0658e3/portal-impl/src/com/liferay/portlet/documentlibrary/service/permission/DLFolderPermission.java)) ensures that the button is only present when the user has the correct permissions, in this case ADD_DOCUMENT.

This module was developed against *Liferay 7.3*

**This approach has been taken because an API based approach was unavailable in the case of Document and Media. It is always best to verify whether the JSP can be overriden using Dynamic Includes or Portlet Filters.**