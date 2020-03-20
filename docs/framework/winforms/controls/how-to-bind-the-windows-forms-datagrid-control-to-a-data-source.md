---
title: Associare un controllo DataGrid a un'origine datiBind DataGrid Control to a Data Source
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 42514c6a0ab9cf912a32b13675a069976632ece5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182251"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="1207f-102">Procedura: associare il controllo DataGrid Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="1207f-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="1207f-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="1207f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="1207f-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="1207f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="1207f-105">Il controllo <xref:System.Windows.Forms.DataGrid> Windows Form è progettato in modo specifico per visualizzare informazioni da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="1207f-106">Associare il controllo in fase <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> di esecuzione chiamando il metodo .</span><span class="sxs-lookup"><span data-stu-id="1207f-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="1207f-107">Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le origini più tipiche sono i set di dati e le visualizzazioni dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="1207f-108">Per associare dati al controllo DataGrid a livello di codiceTo data-bind the DataGrid control programmatically</span><span class="sxs-lookup"><span data-stu-id="1207f-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="1207f-109">Scrivere il codice per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="1207f-110">Se l'origine dati è un set di dati o una visualizzazione dati basata su una tabella del set di dati, aggiungere codice al form per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="1207f-111">Il codice esatto utilizzato dipende da dove il dataset sta ottenendo i dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="1207f-112">Se il dataset viene popolato direttamente da `Fill` un database, in genere si chiama il metodo di `DsCategories1`un adattatore dati, come nell'esempio seguente, che popola un set di dati denominato :</span><span class="sxs-lookup"><span data-stu-id="1207f-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="1207f-113">Se il set di dati viene compilato da un servizio Web XML, in genere si crea un'istanza del servizio nel codice e quindi si chiama uno dei relativi metodi per restituire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="1207f-114">È quindi possibile unire il set di dati dal servizio Web XML al dataset locale.</span><span class="sxs-lookup"><span data-stu-id="1207f-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="1207f-115">Nell'esempio riportato di seguito viene illustrato come `CategoriesService`creare `GetCategories` un'istanza di un servizio Web `DsCategories1`XML denominato , chiamare il relativo metodo e unire il dataset risultante in un dataset locale denominato :</span><span class="sxs-lookup"><span data-stu-id="1207f-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="1207f-116">Chiamare <xref:System.Windows.Forms.DataGrid> il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del controllo, passandogli l'origine dati e un membro dati.</span><span class="sxs-lookup"><span data-stu-id="1207f-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="1207f-117">Se non è necessario passare in modo esplicito un membro dati, passare una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="1207f-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1207f-118">Se si associa la griglia per la prima volta, <xref:System.Windows.Forms.DataGrid.DataSource%2A> <xref:System.Windows.Forms.DataGrid.DataMember%2A> è possibile impostare le proprietà e del controllo.</span><span class="sxs-lookup"><span data-stu-id="1207f-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="1207f-119">Tuttavia, non è possibile reimpostare queste proprietà una volta impostate.</span><span class="sxs-lookup"><span data-stu-id="1207f-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="1207f-120">Pertanto, si consiglia di <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> utilizzare sempre il metodo .</span><span class="sxs-lookup"><span data-stu-id="1207f-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="1207f-121">Nell'esempio seguente viene illustrato come eseguire l'associazione `DsCustomers1`a livello di codice alla tabella Customers in un set di dati denominato :</span><span class="sxs-lookup"><span data-stu-id="1207f-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="1207f-122">Se la tabella Customers è l'unica tabella del set di dati, in alternativa è possibile associare la griglia in questo modo:If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span><span class="sxs-lookup"><span data-stu-id="1207f-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="1207f-123">(Facoltativo) Aggiungere gli stili di tabella e gli stili di colonna appropriati alla griglia.</span><span class="sxs-lookup"><span data-stu-id="1207f-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="1207f-124">Se non sono presenti stili di tabella, verrà visualizzata la tabella, ma con una formattazione minima e con tutte le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="1207f-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1207f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1207f-125">See also</span></span>

- [<span data-ttu-id="1207f-126">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="1207f-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="1207f-127">Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="1207f-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="1207f-128">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="1207f-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="1207f-129">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="1207f-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
