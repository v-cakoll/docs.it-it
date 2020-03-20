---
title: Modifica dei dati visualizzati in fase di esecuzione nel controllo DataGridChange Displayed Data at Run Time in DataGrid Control
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
ms.openlocfilehash: 6b788c10784082a0c74ee09f8cd85d540c670b84
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142381"
---
# <a name="how-to-change-displayed-data-at-run-time-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="73637-102">Procedura: modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="73637-102">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="73637-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="73637-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="73637-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="73637-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="73637-105">Dopo aver creato un <xref:System.Windows.Forms.DataGrid> Windows Form utilizzando le funzionalità della fase di <xref:System.Data.DataSet> progettazione, è anche possibile modificare dinamicamente gli elementi dell'oggetto della griglia in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73637-105">After you have created a Windows Forms <xref:System.Windows.Forms.DataGrid> using the design-time features, you may also wish to dynamically change elements of the <xref:System.Data.DataSet> object of the grid at run time.</span></span> <span data-ttu-id="73637-106">Ciò può includere modifiche ai singoli valori della tabella <xref:System.Windows.Forms.DataGrid> o la modifica dell'origine dati associata al controllo.</span><span class="sxs-lookup"><span data-stu-id="73637-106">This can include changes to either individual values of the table or changing which data source is bound to the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="73637-107">Le modifiche ai singoli <xref:System.Data.DataSet> valori vengono <xref:System.Windows.Forms.DataGrid> eseguite tramite l'oggetto, non il controllo.</span><span class="sxs-lookup"><span data-stu-id="73637-107">Changes to individual values are done through the <xref:System.Data.DataSet> object, not the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
### <a name="to-change-data-programmatically"></a><span data-ttu-id="73637-108">Per modificare i dati a livello di codiceTo change data programmatically</span><span class="sxs-lookup"><span data-stu-id="73637-108">To change data programmatically</span></span>  
  
1. <span data-ttu-id="73637-109">Specificare la tabella <xref:System.Data.DataSet> desiderata dall'oggetto e la riga e il campo desiderati dalla tabella e impostare la cella uguale al nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="73637-109">Specify the desired table from the <xref:System.Data.DataSet> object and the desired row and field from the table and set the cell equal to the new value.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="73637-110">Per specificare la <xref:System.Data.DataSet> prima tabella della o della prima riga della tabella, utilizzare 0.</span><span class="sxs-lookup"><span data-stu-id="73637-110">To specify the first table of the <xref:System.Data.DataSet> or the first row of the table, use 0.</span></span>  
  
     <span data-ttu-id="73637-111">Nell'esempio seguente viene illustrato come modificare la seconda voce della prima `Button1`riga della prima tabella di un dataset facendo clic su .</span><span class="sxs-lookup"><span data-stu-id="73637-111">The following example shows how to change the second entry of the first row of the first table of a dataset by clicking `Button1`.</span></span> <span data-ttu-id="73637-112">I <xref:System.Data.DataSet> `ds`campi (`0` ) `1`e le tabelle ( e ) sono stati creati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="73637-112">The <xref:System.Data.DataSet> (`ds`) and Tables (`0` and `1`) were previously created.</span></span>  
  
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
  
     <span data-ttu-id="73637-113">(Visual C, Visual C Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="73637-113">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click +=  
       gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     <span data-ttu-id="73637-114">In fase di esecuzione <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> è possibile <xref:System.Windows.Forms.DataGrid> utilizzare il metodo per associare il controllo a un'origine dati diversa.</span><span class="sxs-lookup"><span data-stu-id="73637-114">At run time you can use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to bind the <xref:System.Windows.Forms.DataGrid> control to a different data source.</span></span> <span data-ttu-id="73637-115">Ad esempio, è possibile disporre di diversi controlli dati ADO.NET, ognuno connesso a un database diverso.</span><span class="sxs-lookup"><span data-stu-id="73637-115">For example, you may have several ADO.NET data controls, each connected to a different database.</span></span>  
  
### <a name="to-change-the-datasource-programmatically"></a><span data-ttu-id="73637-116">Per modificare DataSource a livello di codiceTo change the DataSource programmatically</span><span class="sxs-lookup"><span data-stu-id="73637-116">To change the DataSource programmatically</span></span>  
  
1. <span data-ttu-id="73637-117">Impostare <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> il metodo sul nome dell'origine dati e della tabella a cui si desidera eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="73637-117">Set the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to the name of the data source and table you want to bind to.</span></span>  
  
     <span data-ttu-id="73637-118">Nell'esempio seguente viene illustrato come <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> modificare l'origine della data utilizzando il metodo per un controllo dati ADO.NET (adoPubsAuthors) connesso alla tabella Authors del database Pubs.</span><span class="sxs-lookup"><span data-stu-id="73637-118">The following example shows how to change the date source using the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method to an ADO.NET data control (adoPubsAuthors) that is connected to the Authors table in the Pubs database.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73637-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73637-119">See also</span></span>

- [<span data-ttu-id="73637-120">Oggetti DataSet ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73637-120">ADO.NET DataSets</span></span>](../../data/adonet/ado-net-datasets.md)
- [<span data-ttu-id="73637-121">Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="73637-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="73637-122">Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="73637-122">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="73637-123">Procedura: associare il controllo DataGrid Windows Form a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="73637-123">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
