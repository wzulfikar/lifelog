# Working with Datatables

https://datatables.net/reference/api/row().data()

- get data of row
- create action button
- show modal with row data as content
- reuse datatables
- highlight search value


### Common Actions : Edit & Delete
- using bootstrap, fontawesome & jquery

```js
var 
ctxName  = 'row',
selector = {
  btnDel :'[data-action="' + ctxName + '.del"]',
  btnEdit:'[data-action="' + ctxName + '.edit"]'
};

// on click handler
$(document)
  // handle btn edit click event
  .on('click', selector.btnEdit, function(){
    var id = $(this).data('id');
    console.log('edit button clicked. id:', id);
  })
  // handle btn delete click event
  .on('click', selector.btnDel, function(){
    var id = $(this).data('id');
    console.log('delete button clicked. id:', id);
  });

// create your code to build datatable,
// and here is
// your column def for btn actions
// code to create action buttons
{
  title:'Action', 
  data: 'id', 
  render:function(data, type, row){
    var
    btnEdit = '<button class="btn-xs btn-info" title="Edit" data-toggle="tooltip" data-trigger="hover" data-id="' + row.id + '" ' selector.btnEdit + '><i class="fa fa-edit"></i></button>',
    btnDel  = '<button class="btn-xs btn-danger" title="Delete" data-toggle="tooltip" data-trigger="hover" data-id="' + row.id + '" ' + selector.btnDel + '><i class="fa fa-times"></i></button>',
    render  = btnEdit + '&nbsp' + btnDel;

    return render;
  }
},
```