# My Journey with Datatables Editor

* using laravel: `DatatablesController`, `EditorController`, `routes/web/editor.php`, `routes/web/datatable.php`
* common snippet:

  ```js
  // csrf token if u're using laravel
  $.ajaxSetup({ headers: { 'X-CSRF-TOKEN' : 'CSRF_TOKEN_HERE' } });
  var editor; // use a global for the submit and return data rendering in the examples
  $(document).ready(function() {
  editor = new $.fn.dataTable.Editor( {
    ajax: "/editor/freights",
    table: "#manage-freights",
    fields: [ 
        {
            label: "Nama",
            name: "name",
        }, 
    ] 
  });
  $('#manage-users').DataTable( {
    dom: "Bfrtip",
    ajax: "/dt/users",
    columns: [
        { data: "name" },
        { data: "email" },
    ],
    select: true,
    buttons: [
        { extend: "create", editor: editor },
        { extend: "edit", editor: editor },
        { extend: "remove", editor: editor }
    ]
  });
  });
  ```

### Common Errors:

* undefined row id: [https://datatables.net/manual/tech-notes/14](https://datatables.net/manual/tech-notes/14)
* undefined style: check your thead



