---
title: 'Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms'
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
ms.openlocfilehash: bfb0296566fecc2029df16d91c9c04d7daa4b4b5
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046161"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="58865-102">Procedura: Aggiungere tabelle e colonne al controllo DataGrid di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="58865-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>

> [!NOTE]
> <span data-ttu-id="58865-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="58865-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="58865-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="58865-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

<span data-ttu-id="58865-105">È possibile visualizzare i dati nel controllo <xref:System.Windows.Forms.DataGrid> Windows Forms in tabelle e colonne creando oggetti **DataGridTableStyle** e aggiungendoli all'oggetto **GridTableStylesCollection** , a cui è possibile accedere tramite il <xref:System.Windows.Forms.DataGrid> controllo Proprietà **TableStyles** .</span><span class="sxs-lookup"><span data-stu-id="58865-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="58865-106">In ogni stile di tabella viene visualizzato il contenuto di qualsiasi tabella di dati specificata nella proprietà **MappingName** dell'oggetto **DataGridTableStyle** .</span><span class="sxs-lookup"><span data-stu-id="58865-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="58865-107">Per impostazione predefinita, uno stile di tabella senza stili di colonna specificato visualizzerà tutte le colonne all'interno della tabella di dati.</span><span class="sxs-lookup"><span data-stu-id="58865-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="58865-108">È possibile limitare le colonne presenti nella tabella aggiungendo oggetti **DataGridColumnStyle** all'oggetto **GridColumnStylesCollection** , a cui si accede tramite la proprietà **GridColumnStyles** di ogni **DataGridTableStyle** oggetto.</span><span class="sxs-lookup"><span data-stu-id="58865-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>

### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="58865-109">Per aggiungere una tabella e una colonna a una griglia a livello di codice</span><span class="sxs-lookup"><span data-stu-id="58865-109">To add a table and column to a DataGrid programmatically</span></span>

1. <span data-ttu-id="58865-110">Per visualizzare i dati nella tabella, è innanzitutto necessario associare il <xref:System.Windows.Forms.DataGrid> controllo a un set di dati.</span><span class="sxs-lookup"><span data-stu-id="58865-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="58865-111">Per altre informazioni, vedere [Procedura: Associare il controllo DataGrid Windows Forms a un'origine](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)dati.</span><span class="sxs-lookup"><span data-stu-id="58865-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>

    > [!CAUTION]
    > <span data-ttu-id="58865-112">Quando si specificano gli stili delle colonne a livello di codice, creare sempre oggetti DataGridColumnStyle e aggiungerli all'oggetto **GridColumnStylesCollection** prima di aggiungere oggetti **DataGridTableStyle** al  **Oggetto GridTableStylesCollection** .</span><span class="sxs-lookup"><span data-stu-id="58865-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="58865-113">Quando si aggiunge un oggetto **DataGridTableStyle** vuoto alla raccolta, gli oggetti DataGridColumnStyle vengono generati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="58865-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="58865-114">Di conseguenza, verrà generata un'eccezione se si tenta di aggiungere nuovi oggetti DataGridColumnStyle con valori di MappingName duplicati all'oggetto **GridColumnStylesCollection** .</span><span class="sxs-lookup"><span data-stu-id="58865-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>

2. <span data-ttu-id="58865-115">Dichiarare un nuovo stile di tabella e impostarne il nome del mapping.</span><span class="sxs-lookup"><span data-stu-id="58865-115">Declare a new table style and set its mapping name.</span></span>

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

3. <span data-ttu-id="58865-116">Dichiarare un nuovo stile di colonna e impostarne il nome del mapping e altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="58865-116">Declare a new column style and set its mapping name and other properties.</span></span>

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

4. <span data-ttu-id="58865-117">Chiamare il metodo **Add** dell'oggetto **GridColumnStylesCollection** per aggiungere la colonna allo stile della tabella</span><span class="sxs-lookup"><span data-stu-id="58865-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>

    ```vb
    ts1.GridColumnStyles.Add(myDataCol)
    ```

    ```csharp
    ts1.GridColumnStyles.Add(myDataCol);
    ```

    ```cpp
    ts1->GridColumnStyles->Add(myDataCol);
    ```

5. <span data-ttu-id="58865-118">Chiamare il metodo **Add** dell'oggetto **GridTableStylesCollection** per aggiungere lo stile della tabella alla griglia dei dati.</span><span class="sxs-lookup"><span data-stu-id="58865-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>

    ```vb
    DataGrid1.TableStyles.Add(ts1)
    ```

    ```csharp
    dataGrid1.TableStyles.Add(ts1);
    ```

    ```cpp
    dataGrid1->TableStyles->Add(ts1);
    ```

## <a name="see-also"></a><span data-ttu-id="58865-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58865-119">See also</span></span>

- [<span data-ttu-id="58865-120">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="58865-120">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="58865-121">Procedura: Eliminare o nascondere colonne nel controllo Windows Forms DataGrid</span><span class="sxs-lookup"><span data-stu-id="58865-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
