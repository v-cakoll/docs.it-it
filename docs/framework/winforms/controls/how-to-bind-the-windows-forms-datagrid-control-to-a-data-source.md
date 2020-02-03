---
title: Associare il controllo DataGrid a un'origine dati
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
ms.openlocfilehash: 2634a6bd8ace36bcf7a49120162474a8c04b2b83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746694"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="6db23-102">Procedura: associare il controllo DataGrid Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="6db23-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
> <span data-ttu-id="6db23-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="6db23-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="6db23-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="6db23-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="6db23-105">Il controllo Windows Forms <xref:System.Windows.Forms.DataGrid> è progettato in modo specifico per visualizzare le informazioni provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="6db23-106">Il controllo viene associato in fase di esecuzione chiamando il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="6db23-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="6db23-107">Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le origini più tipiche sono i set di dati e le visualizzazioni dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="6db23-108">Per associare i dati al controllo DataGrid a livello di codice</span><span class="sxs-lookup"><span data-stu-id="6db23-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="6db23-109">Scrivere il codice per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="6db23-110">Se l'origine dati è un set di dati o una vista dati basata su una tabella del set di dati, aggiungere il codice al form per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="6db23-111">Il codice esatto utilizzato dipende dalla posizione in cui il set di dati recupera i dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="6db23-112">Se il set di dati viene popolato direttamente da un database, in genere si chiama il metodo `Fill` di un adattatore dati, come nell'esempio seguente, che popola un set di dati denominato `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="6db23-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="6db23-113">Se il set di dati viene compilato da un servizio Web XML, in genere si crea un'istanza del servizio nel codice e quindi si chiama uno dei metodi per restituire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="6db23-114">È quindi possibile unire il set di dati dal servizio Web XML nel set di dati locale.</span><span class="sxs-lookup"><span data-stu-id="6db23-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="6db23-115">Nell'esempio seguente viene illustrato come è possibile creare un'istanza di un servizio Web XML denominato `CategoriesService`, chiamare il relativo metodo `GetCategories` e unire il set di dati risultante in un set di dati locale denominato `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="6db23-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
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
  
2. <span data-ttu-id="6db23-116">Chiamare il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> del controllo <xref:System.Windows.Forms.DataGrid> passandogli l'origine dati e un membro dati.</span><span class="sxs-lookup"><span data-stu-id="6db23-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="6db23-117">Se non è necessario passare in modo esplicito un membro dati, passare una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="6db23-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="6db23-118">Se si associa la griglia per la prima volta, è possibile impostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> del controllo.</span><span class="sxs-lookup"><span data-stu-id="6db23-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="6db23-119">Tuttavia, non è possibile reimpostare queste proprietà dopo che sono state impostate.</span><span class="sxs-lookup"><span data-stu-id="6db23-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="6db23-120">È pertanto consigliabile utilizzare sempre il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="6db23-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="6db23-121">Nell'esempio seguente viene illustrato come è possibile eseguire l'associazione a livello di codice alla tabella Customers in un set di dati denominato `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="6db23-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="6db23-122">Se la tabella Customers è l'unica tabella del set di dati, è possibile associare la griglia in questo modo:</span><span class="sxs-lookup"><span data-stu-id="6db23-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="6db23-123">Opzionale Aggiungere gli stili di tabella e gli stili di colonna appropriati alla griglia.</span><span class="sxs-lookup"><span data-stu-id="6db23-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="6db23-124">Se non sono presenti stili di tabella, verrà visualizzata la tabella, ma con la formattazione minima e con tutte le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="6db23-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6db23-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6db23-125">See also</span></span>

- [<span data-ttu-id="6db23-126">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="6db23-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="6db23-127">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="6db23-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="6db23-128">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="6db23-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="6db23-129">Associazione ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="6db23-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
