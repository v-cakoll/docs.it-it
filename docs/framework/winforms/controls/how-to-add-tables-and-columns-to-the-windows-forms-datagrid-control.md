---
title: 'Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: fc8161ea29da92f5dcc2e76f956f3fecd6140acc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527719"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="16e5a-102">Procedura: aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="16e5a-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="16e5a-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="16e5a-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="16e5a-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="16e5a-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="16e5a-105">È possibile visualizzare i dati in Windows Form <xref:System.Windows.Forms.DataGrid> controllo in tabelle e colonne creando **DataGridTableStyle** oggetti e aggiungendoli al **GridColumnStylesCollection** oggetto, ovvero si accede tramite il <xref:System.Windows.Forms.DataGrid> del controllo **TableStyles** proprietà.</span><span class="sxs-lookup"><span data-stu-id="16e5a-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="16e5a-106">Ogni stile tabella viene visualizzato il contenuto di qualsiasi tabella di dati specificata nella **DataGridTableStyle** dell'oggetto **MappingName** proprietà.</span><span class="sxs-lookup"><span data-stu-id="16e5a-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="16e5a-107">Per impostazione predefinita, uno stile di tabella con nessuno stile di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati.</span><span class="sxs-lookup"><span data-stu-id="16e5a-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="16e5a-108">È possibile limitare le colonne della tabella vengono visualizzati aggiungendo **DataGridColumnStyle** oggetti per il **GridColumnStylesCollection** oggetto, che è possibile accedere mediante il  **GridColumnStyles** proprietà di ogni **DataGridTableStyle** oggetto.</span><span class="sxs-lookup"><span data-stu-id="16e5a-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="16e5a-109">Per aggiungere una tabella e una colonna a una griglia dati a livello di codice</span><span class="sxs-lookup"><span data-stu-id="16e5a-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="16e5a-110">Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati.</span><span class="sxs-lookup"><span data-stu-id="16e5a-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="16e5a-111">Per ulteriori informazioni, vedere [procedura: associare il controllo DataGrid Windows Form a un'origine dati](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="16e5a-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="16e5a-112">Quando si specifica a livello di codice gli stili di colonna, creare sempre **DataGridColumnStyle** degli oggetti e aggiungerli al **GridColumnStylesCollection** oggetto prima di aggiungere  **DataGridTableStyle** oggetti per il **GridColumnStylesCollection** oggetto.</span><span class="sxs-lookup"><span data-stu-id="16e5a-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="16e5a-113">Quando si aggiunge un oggetto vuoto **DataGridTableStyle** oggetto alla raccolta, **DataGridColumnStyle** gli oggetti vengono generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="16e5a-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="16e5a-114">Di conseguenza, verrà generata un'eccezione se si tenta di aggiungere nuovi **DataGridColumnStyle** oggetti con duplicato **MappingName** i valori per il **GridColumnStylesCollection**oggetto.</span><span class="sxs-lookup"><span data-stu-id="16e5a-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2.  <span data-ttu-id="16e5a-115">Dichiarare un nuovo stile di tabella e impostarne il nome di mapping.</span><span class="sxs-lookup"><span data-stu-id="16e5a-115">Declare a new table style and set its mapping name.</span></span>  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  <span data-ttu-id="16e5a-116">Dichiarare un nuovo stile di colonna e impostare altre proprietà e il nome di associazione.</span><span class="sxs-lookup"><span data-stu-id="16e5a-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  <span data-ttu-id="16e5a-117">Chiamare il **Aggiungi** metodo il **GridColumnStylesCollection** oggetto per aggiungere la colonna allo stile di tabella</span><span class="sxs-lookup"><span data-stu-id="16e5a-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  <span data-ttu-id="16e5a-118">Chiamare il **Aggiungi** metodo il **GridColumnStylesCollection** oggetto da aggiungere lo stile di tabella alla griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="16e5a-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="16e5a-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16e5a-119">See Also</span></span>  
 [<span data-ttu-id="16e5a-120">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="16e5a-120">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="16e5a-121">Procedura: Eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="16e5a-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
