# roundcube bootstrap skin (RBS)
========================

A roundcube mobile-first skin, based on twitter bootstrap 3

This skin is intended to combine the power of roundcube, an open source webmail client, and twitter boostrap, a mobile-first css framework.

At the moment this skin is under heavy development and should not be used in production AT ALL!

However, I'm looking for contributors and fellow bootstrap and roundcube fans who are looking for a bootstrap skin but didn't find one yet.

Contact me, if you want to participate in this project!

======================
## Advantages
Bootstrap is a highly developed and very mature css and javascript framework that can be applied for a lot of different scenarios. 
Roundcube is one of these scenarios.

Roundcube on the other hand is a very flexible web mail client for almost any imap servers. Roundcube offers a markup language that enables one to design its own skins or to extend roundcube skins.

With this said, it is relatively easy to develop and install new skins for roundcube. There's no need to install new software or program modules besides the skin. The skin comes with all componenets that are necessary to run rbs out of the box.
Roundcube also comes with jquery which means, that you don't even have to install another JavaScript library. Therefore you don't have any issues with conflicting libraries.

## The not so fun part
Roundcubes Markup Language for skins is well documented an easy to use. However, there are some not so fun parts that come with this "magic". 
Skin_ML does not allow the developer to specify css-classes of attributes for the included html elements. For example, when you're including the login form (labels, textfields and button), you specify this in your html-template:
`<roundcube:object name="loginform" form="form" size="40" submit=true />`
This will, once rendered by roundcube, result in the login form. It's all fun and games until here. The html code generated looks like this:
`<table>  
  <tbody>  
    <tr>  
      <td class="title">  
        <label for="rcmloginuser">Benutzername</label>  
      </td>  
      <td class="input"><input name="_user" id="rcmloginuser" required="required" size="40" autocapitalize="off"    autocomplete="off" type="text">  
      </td>  
    </tr>  
    <tr>  
      <td class="title">  
        <label for="rcmloginpwd">Passwort</label>  
      </td>  
      <td class="input">  
        <input name="_pass" id="rcmloginpwd" required="required" size="40" autocapitalize="off" autocomplete="off" type="password">  
      </td>  
    </tr>  
  </tbody>  
</table>`  

This HTML code is perfectly fine and works for every self-designed css where you can easily style the classes by yourself. However, Using a framework with predefined classes makes it more difficult to wrap this html into valid bootstrap css.

Being short, this results in some JavaScript overhead to extract the html from the table and wrap place it where the table was. But that's still nothing we can't fix, right ;)




