# AdminLTE Integration for Java Freemarker (FTL)


- get all assets from bower 

layout structure :

- head.ftl
- main-header.ftl
- left-sidebar.ftl
- right-sidebar.ftl
- main.ftl
- footer.ftl

#### Main View
`main.ftl`

#### Passing Content From Child View to Main
>In `main.ftl`, there are pre-defined `<@yield to="head"/>` and `<@yield to="script"/>`. 

To pass content from child view to parent's `<head>`, use :

```
<@content for="head">
<#-- the `<@yield to="head"/>` in main.ftl will be replaced with whatever here -->
</@content>
```

To pass content from child view to parent's end of body, use :

```
<@content for="script">
<#-- the `<@yield to="script"/>` in main.ftl will be replaced with whatever here -->
</@content>
```