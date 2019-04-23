---
title: "Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati"
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
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332573"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="8b164-102">Procedura: Associare il controllo DataGrid di Windows Forms a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="8b164-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="8b164-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="8b164-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="8b164-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="8b164-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="8b164-105">I moduli di Windows <xref:System.Windows.Forms.DataGrid> controllo è appositamente progettato per visualizzare le informazioni da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="8b164-106">Si associa il controllo in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8b164-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="8b164-107">Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le cause più comuni sono i set di dati e le visualizzazioni dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="8b164-108">Per associare a livello di codice il controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="8b164-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="8b164-109">Scrivere codice per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="8b164-110">Se l'origine dati è un set di dati o una vista di dati basato su una tabella di set di dati, aggiungere codice al form per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="8b164-111">Il codice esatto che è usare dipende in cui il set di dati stia ottenendo i dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="8b164-112">In genere se il set di dati viene popolato direttamente da un database, si chiama il `Fill` metodo di un adattatore di dati, come nell'esempio seguente, che consente di popolare un set di dati denominato `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="8b164-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="8b164-113">Se il set di dati viene riempito da un servizio Web XML, si crea in genere un'istanza del servizio nel codice e quindi chiamarla uno dei relativi metodi per restituire un set di dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="8b164-114">Quindi unire il set di dati dal servizio Web XML in set di dati locale.</span><span class="sxs-lookup"><span data-stu-id="8b164-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="8b164-115">Nell'esempio seguente viene illustrato come è possibile creare un'istanza di un servizio Web XML chiamato `CategoriesService`, chiamare relativi `GetCategories` metodo e merge denominato set di dati risultante in un set di dati locale `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="8b164-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
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
  
2. <span data-ttu-id="8b164-116">Chiamare il <xref:System.Windows.Forms.DataGrid> del controllo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> passandogli l'origine dati e un membro dati.</span><span class="sxs-lookup"><span data-stu-id="8b164-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="8b164-117">Se non è necessario passare in modo esplicito un membro dati, passare una stringa vuota.</span><span class="sxs-lookup"><span data-stu-id="8b164-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b164-118">Se si esegue il binding della griglia per la prima volta, è possibile impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="8b164-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="8b164-119">Tuttavia, è possibile reimpostare le proprietà dopo che sono stati impostati.</span><span class="sxs-lookup"><span data-stu-id="8b164-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="8b164-120">Pertanto, è consigliabile usare sempre la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="8b164-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="8b164-121">Nell'esempio seguente viene illustrato come è possibile associare a livello di codice alla tabella Customers in un set di dati denominato `DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="8b164-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="8b164-122">Se la tabella Customers è l'unica tabella nel set di dati, è in alternativa è stato possibile associare la griglia in questo modo:</span><span class="sxs-lookup"><span data-stu-id="8b164-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="8b164-123">(Facoltativo) Aggiungere gli stili tabella appropriata e gli stili di colonna nella griglia.</span><span class="sxs-lookup"><span data-stu-id="8b164-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="8b164-124">Se non sono presenti stili di tabella, verrà visualizzato nella tabella, ma con una formattazione minima e con tutte le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="8b164-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b164-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8b164-125">See also</span></span>

- [<span data-ttu-id="8b164-126">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="8b164-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="8b164-127">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="8b164-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="8b164-128">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="8b164-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="8b164-129">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="8b164-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
