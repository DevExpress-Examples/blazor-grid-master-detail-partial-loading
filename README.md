# Grid for Blazor - Master-Detail with partial loading

The DevExpress Blazor Grid component allows you to create hierarchical layouts of any complexity and depth. This example uses a nested component to visualize master-detail relationship between two data tables. It also shows how to integrate a Loading Panel into a detail area if it takes time for a nested component to render and load data, for example, if it retrieves records from a database.

![Blazor Grid - Loading Panel Integration](blazor-grid-master-detail-loading.gif)

Do the following to organize such master-detail relationship:

1. Add a master grid to your application, specify the grid's data source and columns. In this example, the **Index.razor** file implements the master grid.
2. Add a [DetailRowTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGrid.DetailRowTemplate) to the grid's markup to create a detail view.
3. Create a separate component that implements a detail view (**DetailContent.razor**). The **GetItemsByDateAsync** method imitates a time-consuming operation that retrieves data.
4. Place a Loading Panel to the detail view markup. The following snippet displays the Loading Panel until data is loaded:
    ```Razor
    @if(Records == null) {
        <DxLoadingPanel Visible="true" />
    } else {
        @* Detail view implementation
    }
    ```
5. Add the detail view to the **DetailRowTemplate**. Bind this view to a detail data source that uses the template's context object as a filter criteria.

## Files to Review

- [Index.razor](./CS/GridPartialLoading/Pages/Index.razor)
- [DetailContent.razor](./CS/GridPartialLoading/Pages/DetailContent.razor)

## Documentation

- [DetailRowTemplate](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxGrid.DetailRowTemplate)
- [DxLoadingPanel](https://docs.devexpress.com/Blazor/DevExpress.Blazor.DxLoadingPanel)

## More Examples

- [Grid for Blazor - How to add a nested Grid to create a master-detail layout](https://github.com/DevExpress-Examples/blazor-dxgrid-master-detail-grid)
- [Grid for Blazor - Save and load layout information](https://github.com/DevExpress-Examples/blazor-DxGrid-save-restore-layout)
