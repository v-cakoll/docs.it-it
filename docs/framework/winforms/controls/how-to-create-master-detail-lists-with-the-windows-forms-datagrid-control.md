---
title: 'Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Form'
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
ms.openlocfilehash: 8f247fb3e61abe46b3bb9c74a3b984310d2b99b3
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57715464"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="29df6-102">Procedura: Creare elenchi Master-Details con il controllo DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="29df6-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="29df6-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="29df6-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="29df6-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="29df6-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="29df6-105">Se il <xref:System.Data.DataSet> contiene una serie di tabelle correlate, è possibile utilizzare due <xref:System.Windows.Forms.DataGrid> controlli per visualizzare i dati in un formato master/dettaglio.</span><span class="sxs-lookup"><span data-stu-id="29df6-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="29df6-106">Uno <xref:System.Windows.Forms.DataGrid> designato come la griglia principale, e il secondo può essere tuttavia designato nella griglia dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="29df6-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="29df6-107">Quando si seleziona una voce nell'elenco master, tutte le voci figlio correlati vengono visualizzate nell'elenco di dettagli.</span><span class="sxs-lookup"><span data-stu-id="29df6-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="29df6-108">Ad esempio, se il <xref:System.Data.DataSet> contiene una tabella Customers e una tabella di ordini correlata, si specificherà la tabella Customers a griglia principale e la tabella Orders alla griglia dei dettagli.</span><span class="sxs-lookup"><span data-stu-id="29df6-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="29df6-109">Quando un cliente viene selezionato nella griglia principale, tutti gli ordini associati a tale cliente nella tabella Orders verrebbero visualizzati nella griglia dettagli.</span><span class="sxs-lookup"><span data-stu-id="29df6-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="29df6-110">Per impostare una relazione master/dettagli a livello di codice</span><span class="sxs-lookup"><span data-stu-id="29df6-110">To set a master/detail relationship programmatically</span></span>  
  
1.  <span data-ttu-id="29df6-111">Creare due nuovi <xref:System.Windows.Forms.DataGrid> consente di controllare e impostare le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="29df6-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2.  <span data-ttu-id="29df6-112">Aggiungere tabelle al set di dati.</span><span class="sxs-lookup"><span data-stu-id="29df6-112">Add tables to the dataset.</span></span>  
  
3.  <span data-ttu-id="29df6-113">Dichiarare una variabile di tipo <xref:System.Data.DataRelation> per rappresentare la relazione da creare.</span><span class="sxs-lookup"><span data-stu-id="29df6-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4.  <span data-ttu-id="29df6-114">Creare un'istanza della relazione specificando un nome per la relazione e la tabella, colonna e articoli che limiteranno le due tabelle.</span><span class="sxs-lookup"><span data-stu-id="29df6-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5.  <span data-ttu-id="29df6-115">Aggiungere la relazione con il <xref:System.Data.DataSet> dell'oggetto <xref:System.Data.DataSet.Relations%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="29df6-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6.  <span data-ttu-id="29df6-116">Usare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo del <xref:System.Windows.Forms.DataGrid> ognuna delle griglie per associare il <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="29df6-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="29df6-117">Nell'esempio seguente viene illustrato come impostare una relazione master/dettaglio tra le tabelle Customers e Orders in un oggetto generato in precedenza <xref:System.Data.DataSet> (`ds`).</span><span class="sxs-lookup"><span data-stu-id="29df6-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29df6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="29df6-118">See also</span></span>
- [<span data-ttu-id="29df6-119">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="29df6-119">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="29df6-120">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="29df6-120">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="29df6-121">Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="29df6-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
