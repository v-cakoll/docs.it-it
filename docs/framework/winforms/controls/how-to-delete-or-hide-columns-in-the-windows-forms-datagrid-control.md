---
title: Eliminare o nascondere colonne nel controllo DataGrid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], deleting columns
- DataGrid control [Windows Forms], deleting columns
- data grids [Windows Forms], hiding columns
- columns [Windows Forms], hiding
- columns [Windows Forms], deleting in data grids
- DataGrid control [Windows Forms], hiding columns
ms.assetid: bcd0dd96-6687-4c48-b0e1-d5287b93ac91
ms.openlocfilehash: c730be934e9b978bdaf09bc7e668b4318077fba5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743291"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="12125-102">Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="12125-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="12125-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="12125-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="12125-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="12125-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="12125-105">È possibile eliminare o nascondere a livello di codice le colonne nel controllo Windows Forms <xref:System.Windows.Forms.DataGrid> usando le proprietà e i metodi degli oggetti <xref:System.Windows.Forms.GridColumnStylesCollection> e <xref:System.Windows.Forms.DataGridColumnStyle> (membri della classe <xref:System.Windows.Forms.DataGridTableStyle>).</span><span class="sxs-lookup"><span data-stu-id="12125-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="12125-106">Le colonne eliminate o nascoste sono ancora presenti nell'origine dati a cui è associata la griglia ed è comunque possibile accedervi a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="12125-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="12125-107">Non sono più visibili nell'elemento DataGrid.</span><span class="sxs-lookup"><span data-stu-id="12125-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12125-108">Se l'applicazione non accede ad alcune colonne di dati e non si desidera che vengano visualizzate nel DataGrid, è probabile che non sia necessario includerle nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="12125-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="12125-109">Per eliminare una colonna da DataGrid a livello di codice</span><span class="sxs-lookup"><span data-stu-id="12125-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="12125-110">Nell'area dichiarazioni del modulo dichiarare una nuova istanza della classe <xref:System.Windows.Forms.DataGridTableStyle>.</span><span class="sxs-lookup"><span data-stu-id="12125-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="12125-111">Impostare la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> sulla tabella nell'origine dati a cui si desidera applicare lo stile.</span><span class="sxs-lookup"><span data-stu-id="12125-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="12125-112">Nell'esempio seguente viene utilizzata la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, che presuppone che sia già impostata.</span><span class="sxs-lookup"><span data-stu-id="12125-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="12125-113">Aggiungere il nuovo oggetto <xref:System.Windows.Forms.DataGridTableStyle> alla raccolta di stili di tabella del DataGrid.</span><span class="sxs-lookup"><span data-stu-id="12125-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="12125-114">Chiamare il metodo <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> della raccolta di <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> del <xref:System.Windows.Forms.DataGrid>, specificando l'indice di colonna della colonna da eliminare.</span><span class="sxs-lookup"><span data-stu-id="12125-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub DeleteColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Delete the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles.RemoveAt(0)  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void deleteColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Delete the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles.RemoveAt(0);  
    }  
    ```  
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="12125-115">Per nascondere una colonna nella griglia a livello di codice</span><span class="sxs-lookup"><span data-stu-id="12125-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="12125-116">Nell'area dichiarazioni del modulo dichiarare una nuova istanza della classe <xref:System.Windows.Forms.DataGridTableStyle>.</span><span class="sxs-lookup"><span data-stu-id="12125-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="12125-117">Impostare la proprietà <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> della <xref:System.Windows.Forms.DataGridTableStyle> alla tabella nell'origine dati a cui si desidera applicare lo stile.</span><span class="sxs-lookup"><span data-stu-id="12125-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="12125-118">Nell'esempio di codice seguente viene usata la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType>, che presuppone che sia già impostata.</span><span class="sxs-lookup"><span data-stu-id="12125-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="12125-119">Aggiungere il nuovo oggetto <xref:System.Windows.Forms.DataGridTableStyle> alla raccolta di stili di tabella del DataGrid.</span><span class="sxs-lookup"><span data-stu-id="12125-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="12125-120">Nascondere la colonna impostando la relativa proprietà `Width` su 0, specificando l'indice della colonna da nascondere.</span><span class="sxs-lookup"><span data-stu-id="12125-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
    ```vb  
    ' Declare a new DataGridTableStyle in the  
    ' declarations area of your form.  
    Dim ts As DataGridTableStyle = New DataGridTableStyle()  
  
    Sub HideColumn()  
       ' Set the DataGridTableStyle.MappingName property  
       ' to the table in the data source to map to.  
       ts.MappingName = DataGrid1.DataMember  
  
       ' Add it to the datagrid's TableStyles collection  
       DataGrid1.TableStyles.Add(ts)  
  
       ' Hide the first column (index 0)  
       DataGrid1.TableStyles(0).GridColumnStyles(0).Width = 0  
    End Sub  
    ```  
  
    ```csharp  
    // Declare a new DataGridTableStyle in the  
    // declarations area of your form.  
    DataGridTableStyle ts = new DataGridTableStyle();  
  
    private void hideColumn()  
    {  
       // Set the DataGridTableStyle.MappingName property  
       // to the table in the data source to map to.  
       ts.MappingName = dataGrid1.DataMember;  
  
       // Add it to the datagrid's TableStyles collection  
       dataGrid1.TableStyles.Add(ts);  
  
       // Hide the first column (index 0)  
       dataGrid1.TableStyles[0].GridColumnStyles[0].Width = 0;  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="12125-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12125-121">See also</span></span>

- [<span data-ttu-id="12125-122">Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="12125-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="12125-123">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="12125-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
