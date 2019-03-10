---
title: 'Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form'
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
ms.openlocfilehash: 3ba23dd3966591777c7e354f79dd45ec4530955a
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714957"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="bfc7f-102">Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="bfc7f-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="bfc7f-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="bfc7f-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="bfc7f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="bfc7f-105">Dopo aver creato un controllo Windows Form <xref:System.Windows.Forms.DataGrid> usando le funzionalità in fase di progettazione, è anche possibile modificare dinamicamente gli elementi del <xref:System.Data.DataSet> oggetti della griglia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="bfc7f-106">Può includere le modifiche dei singoli valori di tabella o la modifica origine dati a cui è associata il <xref:System.Windows.Forms.DataGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="bfc7f-107">Vengono apportate modifiche ai singoli valori tramite il <xref:System.Data.DataSet> dell'oggetto, non il <xref:System.Windows.Forms.DataGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="bfc7f-108">Per modificare i dati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="bfc7f-108">To change data programmatically</span></span>  
  
1.  <span data-ttu-id="bfc7f-109">Specificare la tabella desiderata di <xref:System.Data.DataSet> oggetto e il valore desiderato di righe e campo dalla tabella e impostare la cella uguale a quello nuovo.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bfc7f-110">Per specificare la tabella prima di <xref:System.Data.DataSet> o la prima riga della tabella, usare 0.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="bfc7f-111">Nell'esempio seguente viene illustrato come modificare la seconda voce della prima riga della tabella prima di un set di dati, fare clic su `Button1`.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="bfc7f-112">Il <xref:System.Data.DataSet> (`ds`) e le tabelle (`0` e `1`) creati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="bfc7f-113">(Visual c#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-113">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="bfc7f-114">In fase di esecuzione è possibile usare la <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo a cui associare il <xref:System.Windows.Forms.DataGrid> controllo a un'origine dati diversa.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="bfc7f-115">Ad esempio, si possono invece avere diversi [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controlli dei dati, ciascuna connessa a un database diverso.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-115">For example, you may have several [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="bfc7f-116">Per modificare l'origine dati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="bfc7f-116">To change the DataSource programmatically</span></span>  
  
1.  <span data-ttu-id="bfc7f-117">Impostare il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> al nome dell'origine dati e della tabella che si desidera associare al metodo.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="bfc7f-118">Nell'esempio seguente viene illustrato come modificare l'origine dati utilizzando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo a un [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] controllo dati (adoPubsAuthors) che è connessa alla tabella Authors nel database Pubs.</span><span class="sxs-lookup"><span data-stu-id="bfc7f-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bfc7f-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfc7f-119">See also</span></span>
- [<span data-ttu-id="bfc7f-120">Oggetti DataSet ADO.NET</span><span class="sxs-lookup"><span data-stu-id="bfc7f-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="bfc7f-121">Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="bfc7f-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="bfc7f-122">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="bfc7f-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="bfc7f-123">Procedura: Associare il controllo DataGrid di Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="bfc7f-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
