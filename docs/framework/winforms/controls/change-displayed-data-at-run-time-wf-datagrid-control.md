---
title: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGrid control [Windows Forms], dynamically changing at run time
- DataGrid control [Windows Forms], data binding
- cells [Windows Forms], changing DataGrid cell values
ms.assetid: 0c7a6d00-30de-416e-8223-0a81ddb4c1f8
ms.openlocfilehash: f91e2ea01ef4a52dd649efed70319017efb8368a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740599"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="23451-102">Procedura: modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="23451-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="23451-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="23451-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="23451-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="23451-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="23451-105">Dopo aver creato un Windows Forms <xref:System.Windows.Forms.DataGrid> utilizzando le funzionalità della fase di progettazione, è anche possibile modificare dinamicamente gli elementi dell'oggetto <xref:System.Data.DataSet> della griglia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="23451-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="23451-106">Possono essere incluse modifiche ai singoli valori della tabella o alla modifica dell'origine dati associata al controllo <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="23451-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="23451-107">Le modifiche ai singoli valori vengono eseguite tramite l'oggetto <xref:System.Data.DataSet> e non con il controllo <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="23451-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="23451-108">Per modificare i dati a livello di programmazione</span><span class="sxs-lookup"><span data-stu-id="23451-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="23451-109">Specificare la tabella desiderata dall'oggetto <xref:System.Data.DataSet> e la riga e il campo desiderati della tabella e impostare la cella su un valore uguale a quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="23451-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="23451-110">Per specificare la prima tabella del <xref:System.Data.DataSet> o la prima riga della tabella, utilizzare 0.</span><span class="sxs-lookup"><span data-stu-id="23451-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="23451-111">Nell'esempio seguente viene illustrato come modificare la seconda voce della prima riga della prima tabella di un set di dati facendo clic su `Button1`.</span><span class="sxs-lookup"><span data-stu-id="23451-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="23451-112">Il <xref:System.Data.DataSet> (`ds`) e le tabelle (`0` e `1`) sono stati creati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="23451-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
    ```vb  
    Protected Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       ds.tables(0).rows(0)(1) = "NewEntry"  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       ds.Tables[0].Rows[0][1]="NewEntry";  
    }  
    ```  
  
    ```cpp  
    private:   
       void button1_Click(System::Object^ sender, System::EventArgs^ e)  
       {  
          dataSet1->Tables[0]->Rows[0][1] = "NewEntry";  
       }  
    ```  
  
     <span data-ttu-id="23451-113">(Visual C#, Visual C++) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="23451-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="23451-114">In fase di esecuzione è possibile usare il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> per associare il controllo <xref:System.Windows.Forms.DataGrid> a un'origine dati diversa.</span><span class="sxs-lookup"><span data-stu-id="23451-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="23451-115">Ad esempio, è possibile disporre di diversi controlli dati ADO.NET, ciascuno connesso a un database diverso.</span><span class="sxs-lookup"><span data-stu-id="23451-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="23451-116">Per modificare l'origine dati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="23451-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="23451-117">Impostare il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> sul nome dell'origine dati e della tabella a cui si desidera eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="23451-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="23451-118">Nell'esempio seguente viene illustrato come modificare l'origine della data utilizzando il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> in un controllo dati ADO.NET (adoPubsAuthors) connesso alla tabella authors nel database pubs.</span><span class="sxs-lookup"><span data-stu-id="23451-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
    ```vb  
    Private Sub ResetSource()  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors")  
    End Sub  
    ```  
  
    ```csharp  
    private void ResetSource()  
    {  
       DataGrid1.SetDataBinding(adoPubsAuthors, "Authors");  
    }  
    ```  
  
    ```cpp  
    private:  
       void ResetSource()  
       {  
          dataGrid1->SetDataBinding(adoPubsAuthors, "Authors");  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23451-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23451-119">See also</span></span>

- [<span data-ttu-id="23451-120">Oggetti DataSet ADO.NET</span><span class="sxs-lookup"><span data-stu-id="23451-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="23451-121">Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="23451-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="23451-122">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="23451-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="23451-123">Procedura: Associare il controllo DataGrid Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="23451-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
