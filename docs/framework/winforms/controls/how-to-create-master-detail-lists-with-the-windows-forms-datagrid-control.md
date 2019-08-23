---
title: 'Procedura: Creare elenchi Master-Details con il controllo DataGrid Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: f0fd95cf0cd66e9a5105c0b8ff77d8c536a5822d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914757"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="6a48b-102">Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6a48b-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="6a48b-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="6a48b-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="6a48b-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6a48b-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="6a48b-105">Se contiene una serie di tabelle correlate, è possibile usare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato Master/Details. <xref:System.Data.DataSet></span><span class="sxs-lookup"><span data-stu-id="6a48b-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="6a48b-106">Una <xref:System.Windows.Forms.DataGrid> viene designata come griglia master e la seconda viene designata come griglia dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="6a48b-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="6a48b-107">Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlate vengono visualizzate nell'elenco dettagli.</span><span class="sxs-lookup"><span data-stu-id="6a48b-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="6a48b-108">Se, ad esempio, <xref:System.Data.DataSet> contiene una tabella Customers e una tabella Orders correlata, è necessario specificare la tabella Customers come griglia master e la tabella Orders come griglia dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="6a48b-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="6a48b-109">Quando un cliente viene selezionato dalla griglia master, tutti gli ordini associati a tale cliente nella tabella Orders vengono visualizzati nella griglia dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="6a48b-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="6a48b-110">Per impostare una relazione master/dettagli a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6a48b-110">To set a master/detail relationship programmatically</span></span>  
  
1. <span data-ttu-id="6a48b-111">Creare due nuovi <xref:System.Windows.Forms.DataGrid> controlli e impostarne le proprietà.</span><span class="sxs-lookup"><span data-stu-id="6a48b-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2. <span data-ttu-id="6a48b-112">Aggiungere tabelle al set di dati.</span><span class="sxs-lookup"><span data-stu-id="6a48b-112">Add tables to the dataset.</span></span>  
  
3. <span data-ttu-id="6a48b-113">Dichiarare una variabile di tipo <xref:System.Data.DataRelation> per rappresentare la relazione che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="6a48b-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4. <span data-ttu-id="6a48b-114">Creare un'istanza della relazione specificando un nome per la relazione e specificando la tabella, la colonna e l'elemento che collegheranno le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="6a48b-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5. <span data-ttu-id="6a48b-115">Aggiungere la relazione alla <xref:System.Data.DataSet> <xref:System.Data.DataSet.Relations%2A> raccolta dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6a48b-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6. <span data-ttu-id="6a48b-116">Utilizzare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo dell'oggetto <xref:System.Windows.Forms.DataGrid> per associare ogni griglia a <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="6a48b-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="6a48b-117">Nell'esempio seguente viene illustrato come impostare una relazione Master/Detail tra le tabelle Customers e Orders in un <xref:System.Data.DataSet> oggetto`ds`generato in precedenza ().</span><span class="sxs-lookup"><span data-stu-id="6a48b-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6a48b-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6a48b-118">See also</span></span>

- [<span data-ttu-id="6a48b-119">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="6a48b-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="6a48b-120">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="6a48b-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="6a48b-121">Procedura: Associare il controllo DataGrid Windows Forms a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="6a48b-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
