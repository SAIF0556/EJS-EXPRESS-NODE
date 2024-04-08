When quickly creating Node applications, a fast way to template your application is sometimes necessary.

sets EJS as the view engine for the Express application using:  `app.set('view engine', 'ejs');`

create a new partials subdirectory:  mkdir views/partials

Use <%- include('RELATIVE/PATH/TO/FILE') %> to embed an EJS partial in another file.  <%- include('../partials/head'); %>

Passing data to views and partials: res.render('pages/index', {
    mascots: mascots,
    tagline: tagline
  });


  Looping over data in EJS: 
  <ul>
      <% mascots.forEach(function(mascot) { %>
        <li>
          <strong><%= mascot.name %></strong>
          representing <%= mascot.organization %>,
          born <%= mascot.birth_year %>
        </li>
      <% }); %>
    </ul>

  Passing data to the partials:

<header>
  <%- include('../partials/header', {variant: 'compact'}); %>
</header>
    

