---
layout: default
title: AIOTI Urban Society Portfolio
---

<head>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/bulma@0.8.2/css/bulma.min.css"
    />
    <link rel="stylesheet" href="{{ '/assets/css/main.css' | relative_url }}" />
    
    <script
      src="https://code.jquery.com/jquery-3.5.0.min.js"
      integrity="sha256-xNzN2a4ltkB44Mc/Jz3pT4iU1cmeR0FkXs4pru/JxaQ="
      crossorigin="anonymous">
    </script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/datatables/1.10.20/js/jquery.dataTables.min.js"
      integrity="sha256-L4cf7m/cgC51e7BFPxQcKZcXryzSju7VYBKJLOKPHvQ="
      crossorigin="anonymous">
      </script>
  </head>

Browse the solutions provided by AIOTI members in the table below.

If you need to return to the main page, just follow [**this link**](./index.html).


### Catalogue of IoT Solutions focused on Urban Society Goals

<table id="catalogue" class="display" style="width: 100%">
    <thead>
      <tr>
        <th>Name</th>
        <th>Description</th>
        <th>Challenges</th>
        <th style="max-width: 80px;">Provider</th>
      </tr>
    </thead>

    <tbody>
      <!--For loop that iterates over markdown frontmatter in _skus folder-->
      {% for solution in site.solutions %}
      <tr>
        <td><strong><a href="{{ solution.link }}">{{ solution.name }}</a></strong></td>
        <td>{{ solution.content | markdownify }}</td>
        <td>{{ solution.challenges | markdownify }}</td>
        <td style="max-width: 80px;"><a href="{{ solution.provider_url }}"><img src="{{ solution.provider_logo }}" alt="{{ solution.provider }}"/></a></td>
      </tr>
      {% endfor %}
    </tbody>
  <!-- 
    <tfoot>
      <tr>
        <th>Name</th>
        <th>Position</th>
        <th>Description</th>
      </tr>
    </tfoot> -->
  </table>


## Contribute to our Portfolio!

This page is an [open-source project available on GitHub](https://github.com/AIOTIEU/urbansociety). Feel free to contribute!

<script>
$(document).ready(function() {
    $('#catalogue').DataTable();
} );
</script>
