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
<br/>Follow [**this link**](./index.html) to return to the main page.

<div class= "container" >
  <table id="catalogue" class="display" style="width: 100%">
      <tbody>
        <td colspan="12" bgcolor=gray></td>  
        <!--For loop that iterates over markdown frontmatter in _skus folder-->
        {% for solution in site.solutions %}
        <tr>
			    <td colspan="3"><b>Name</b></td>
          <td colspan="3"><b>Provider</b></td>
          <td colspan="3"><b>Domains</b></td>
          <td colspan="3"><b>Status</b></td>
        </tr>
        <tr>
          <td colspan="3">
            <strong>
              <a href="{{ solution.link }}">{{ solution.name }}</a>
            </strong>
          </td>
          <td colspan="3">
            <a href="{{ solution.provider_url }}">
              <strong>{{ solution.provider}}</strong>
              <br><br>
					  	<img src="{{ solution.provider_logo }}" alt="{{ solution.provider }}" width=100/>
            </a>
          </td>
          <td colspan="3">{{ solution.challenges }}</td>
					<td colspan="3">
            {{ solution.status }}
            <br><br>
						<strong>Location:</strong>
            <br>{{ solution.location }}
          </td>
        </tr>
				<tr>
					<td colspan="9">
						<strong>Description:</strong>
            {{ solution.content | markdownify }}
					</td>
          <td colspan="3">
						<strong>Partners involved:</strong>
            <br>
            {{ solution.partners }}
					</td>
				</tr>
				<tr>
					<td colspan="9">
						<strong>More details:</strong>
            <br>
            {{ solution.details }}
					</td>
					<td colspan="3">
						<strong>Next Steps:</strong>
            <br>
            {{ solution.next_steps}}
					</td>
        </tr>
        <tr>
          <td colspan="12" bgcolor=grey></td>
        </tr>
        {% endfor %}
      </tbody>
    </table>
  </div>

## Contribute to our Portfolio!

This page is an [open-source project available on GitHub](https://github.com/AIOTIEU/urbansociety).
<br>Feel free to contribute!

<script>
$(document).ready(function() {
    $('#catalogue').DataTable();
} );
</script>
