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
dtCtx = {
  name : 'user',
  action : {
    del  :function(){
      return this.name + '.del';
    },
    edit :function(){
      return this.name + '.edit';
    }
  },
  // code to create action buttons
  columnDef: {
    title:'Action', 
    data: 'id', 
    render:function(data, type, row){
      var
      btnEdit = '<button class="btn-xs btn-info" title="Edit" data-toggle="tooltip" data-trigger="hover" data-id="' + row.id + '" data-action="' + this.name.action.edit + '"><i class="fa fa-edit"></i></button>',
      btnDel  = '<button class="btn-xs btn-danger" title="Delete" data-toggle="tooltip" data-trigger="hover" data-id="' + row.id + '" data-action="' + this.name.action.del + '><i class="fa fa-times"></i></button>',
      render  = btnEdit + '&nbsp' + btnDel;

      return render;
    }
  },
};

// on click handler
$(document)
  // handle btn edit click event
  .on('click', selector.btnEdit, function(){
    $(document).trigger(action.edit);
    var id = $(this).data('id');
    console.log('edit button clicked. id:', id);
  })
  // handle btn delete click event
  .on('click', selector.btnDel, function(){
    $(document).trigger(action.del);
    var id = $(this).data('id');
    console.log('delete button clicked. id:', id);
  });
```