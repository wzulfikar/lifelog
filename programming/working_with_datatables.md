# Working with Datatables

https://datatables.net/reference/api/row().data()

- get data of row
- create action button
- show modal with row data as content
- reuse datatables
- highlight search value


### Common Actions : Edit & Delete
- using bootstrap and fontawesome
- on click, do ajax operation

```js
// column def

// your code here...

// code to create action buttons
{
  title:'Action', 
  data: 'id', 
  render:function(data, type, row, meta){
    var 
    ctxName = 'row', // context name
    btnEdit = '<button data-toggle="tooltip" class="btn-xs btn-info" data-action="' + ctxName + ':edit" data-id="' + row.id + '" title="Edit" data-trigger="hover"><i class="fa fa-edit"></i></button>',
    btnDel  = '<button data-toggle="tooltip" class="btn-xs btn-danger" title="Delete" data-id="' + row.id + '" data-trigger="hover" data-action="' + ctxName + ':delete"><i class="fa fa-times"></i></button>',
    render  = btnEdit + '&nbsp' + btnDel;

    return render;
  }
},
```
