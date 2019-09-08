---
title: Gestione di oggetti DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0b67fab5-1722-4d2b-bfc1-247a75f0f1ee
ms.openlocfilehash: 5e85fccddf6359791ea702667a36b44f611815dc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784499"
---
# <a name="managing-dataviews"></a><span data-ttu-id="fe725-102">Gestione di oggetti DataView</span><span class="sxs-lookup"><span data-stu-id="fe725-102">Managing DataViews</span></span>
<span data-ttu-id="fe725-103">È possibile usare un tipo <xref:System.Data.DataViewManager> per gestire le impostazioni di visualizzazione per tutte le tabelle di un tipo <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="fe725-103">You can use a <xref:System.Data.DataViewManager> to manage view settings for all the tables in a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="fe725-104">Se si dispone di un controllo che si desidera associare a più tabelle, ad esempio una griglia che Esplora le relazioni, un **DataViewManager** è ideale.</span><span class="sxs-lookup"><span data-stu-id="fe725-104">If you have a control that you want to bind to multiple tables, such as a grid that navigates relationships, a **DataViewManager** is ideal.</span></span>  
  
 <span data-ttu-id="fe725-105">**DataViewManager** contiene una raccolta di <xref:System.Data.DataViewSetting> oggetti utilizzati per impostare l'impostazione di visualizzazione delle tabelle in. <xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="fe725-105">The **DataViewManager** contains a collection of <xref:System.Data.DataViewSetting> objects that are used to set the view setting of the tables in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fe725-106">Contiene un <xref:System.Data.DataViewSetting> oggetto per ogni tabella in un **set di dati.** <xref:System.Data.DataViewSettingCollection></span><span class="sxs-lookup"><span data-stu-id="fe725-106">The <xref:System.Data.DataViewSettingCollection> contains one <xref:System.Data.DataViewSetting> object for each table in a **DataSet**.</span></span> <span data-ttu-id="fe725-107">È possibile impostare le proprietà **ApplyDefaultSort**, **Sort**, **RowFilter**e **RowStateFilter** predefinite della tabella a cui si fa riferimento usando la relativa **DataViewSetting**.</span><span class="sxs-lookup"><span data-stu-id="fe725-107">You can set the default **ApplyDefaultSort**, **Sort**, **RowFilter**, and **RowStateFilter** properties of the referenced table by using its **DataViewSetting**.</span></span> <span data-ttu-id="fe725-108">È possibile fare riferimento a **DataViewSetting** per una determinata tabella in base al nome o al riferimento ordinale oppure passando un riferimento a tale oggetto tabella specifico.</span><span class="sxs-lookup"><span data-stu-id="fe725-108">You can reference the **DataViewSetting** for a particular table by name or ordinal reference, or by passing a reference to that specific table object.</span></span> <span data-ttu-id="fe725-109">È possibile accedere alla raccolta di oggetti **DataViewSetting** in **DataViewManager** usando la proprietà **DataViewSettings** .</span><span class="sxs-lookup"><span data-stu-id="fe725-109">You can access the collection of **DataViewSetting** objects in a **DataViewManager** by using the **DataViewSettings** property.</span></span>  
  
 <span data-ttu-id="fe725-110">Nell'esempio di codice seguente viene compilato un **set** di dati con le tabelle di database SQL Server **Northwind** **Customers**, **Orders**e **Order Details**, vengono create le relazioni tra le tabelle, viene utilizzato un **DataViewManager** per impostare le impostazioni di **DataView** predefinite e associare un **DataGrid** a **DataViewManager**.</span><span class="sxs-lookup"><span data-stu-id="fe725-110">The following code example fills a **DataSet** with the SQL Server **Northwind** database tables **Customers**, **Orders**, and **Order Details**, creates the relationships between the tables, uses a **DataViewManager** to set default **DataView** settings, and binds a **DataGrid** to the **DataViewManager**.</span></span> <span data-ttu-id="fe725-111">Nell'esempio vengono impostate le impostazioni **DataView** predefinite per tutte le tabelle del **set di dati** in modo da eseguire l'ordinamento in base alla chiave primaria della tabella (**ApplyDefaultSort** = **true**), quindi viene modificato l'ordinamento della tabella **Customers** in Ordina per **CompanyName**.</span><span class="sxs-lookup"><span data-stu-id="fe725-111">The example sets the default **DataView** settings for all tables in the **DataSet** to sort by the primary key of the table (**ApplyDefaultSort** = **true**), and then modifies the sort order of the **Customers** table to sort by **CompanyName**.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection to Northwind.  
' Create a Connection, DataAdapters, and a DataSet.  
Dim custDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers", connection)  
Dim orderDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, CustomerID FROM Orders", connection)  
Dim ordDetDA As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection)  
  
Dim custDS As DataSet = New DataSet()  
  
' Open the Connection.  
connection.Open()  
  
    ' Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey  
  
    custDA.Fill(custDS, "Customers")  
    orderDA.Fill(custDS, "Orders")  
    ordDetDA.Fill(custDS, "OrderDetails")  
  
    ' Close the Connection.  
    connection.Close()  
  
    ' Create relationships.  
    custDS.Relations.Add("CustomerOrders", _  
          custDS.Tables("Customers").Columns("CustomerID"), _  
          custDS.Tables("Orders").Columns("CustomerID"))  
  
    custDS.Relations.Add("OrderDetails", _  
          custDS.Tables("Orders").Columns("OrderID"), _  
          custDS.Tables("OrderDetails").Columns("OrderID"))  
  
' Create default DataView settings.  
Dim viewManager As DataViewManager = New DataViewManager(custDS)  
  
Dim viewSetting As DataViewSetting  
For Each viewSetting In viewManager.DataViewSettings  
  viewSetting.ApplyDefaultSort = True  
Next  
  
viewManager.DataViewSettings("Customers").Sort = "CompanyName"  
  
' Bind to a DataGrid.  
Dim grid As System.Windows.Forms.DataGrid = New System.Windows.Forms.DataGrid()  
grid.SetDataBinding(viewManager, "Customers")  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection to Northwind.  
// Create a Connection, DataAdapters, and a DataSet.  
SqlDataAdapter custDA = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers", connection);  
SqlDataAdapter orderDA = new SqlDataAdapter(  
  "SELECT OrderID, CustomerID FROM Orders", connection);  
SqlDataAdapter ordDetDA = new SqlDataAdapter(  
  "SELECT OrderID, ProductID, Quantity FROM [Order Details]", connection);  
  
DataSet custDS = new DataSet();  
  
// Open the Connection.  
connection.Open();  
  
    // Fill the DataSet with schema information and data.  
    custDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    orderDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
    ordDetDA.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
  
    custDA.Fill(custDS, "Customers");  
    orderDA.Fill(custDS, "Orders");  
    ordDetDA.Fill(custDS, "OrderDetails");  
  
    // Close the Connection.  
    connection.Close();  
  
    // Create relationships.  
    custDS.Relations.Add("CustomerOrders",  
          custDS.Tables["Customers"].Columns["CustomerID"],  
          custDS.Tables["Orders"].Columns["CustomerID"]);  
  
    custDS.Relations.Add("OrderDetails",  
          custDS.Tables["Orders"].Columns["OrderID"],  
          custDS.Tables["OrderDetails"].Columns["OrderID"]);  
  
// Create default DataView settings.  
DataViewManager viewManager = new DataViewManager(custDS);  
  
foreach (DataViewSetting viewSetting in viewManager.DataViewSettings)  
  viewSetting.ApplyDefaultSort = true;  
  
viewManager.DataViewSettings["Customers"].Sort = "CompanyName";  
  
// Bind to a DataGrid.  
System.Windows.Forms.DataGrid grid = new System.Windows.Forms.DataGrid();  
grid.SetDataBinding(viewManager, "Customers");  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe725-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe725-112">See also</span></span>

- <xref:System.Data.DataSet>
- <xref:System.Data.DataViewManager>
- <xref:System.Data.DataViewSetting>
- <xref:System.Data.DataViewSettingCollection>
- [<span data-ttu-id="fe725-113">DataView</span><span class="sxs-lookup"><span data-stu-id="fe725-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="fe725-114">Panoramica di ADO.NET</span><span class="sxs-lookup"><span data-stu-id="fe725-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
