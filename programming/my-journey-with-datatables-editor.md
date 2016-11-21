# My Journey with Datatables Editor

- using laravel: `DatatablesController`, `EditorController`, `routes/web/editor.php`, `routes/web/datatable.php`
- common snippet:

  ```js
$('#manage-freights').DataTable( {
    dom: "Bfrtip",
    ajax: "/dt/freights",
    columns: [
        { data: "name" },
    ],
    select: true,
    buttons: [
        { extend: "create", editor: editor },
        { extend: "edit", editor: editor },
        { extend: "remove", editor: editor }
    ]
});
  ```