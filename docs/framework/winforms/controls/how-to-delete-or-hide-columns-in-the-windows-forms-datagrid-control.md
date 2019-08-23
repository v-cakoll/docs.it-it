---
title: 'Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms'
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
ms.openlocfilehash: 70229abddb831788f521f85747db1093c941ba8a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967381"
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="a8494-102">Procedura: Eliminare o nascondere colonne nel controllo DataGrid di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8494-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
> <span data-ttu-id="a8494-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="a8494-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="a8494-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="a8494-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="a8494-105">È possibile eliminare o nascondere a livello di codice le colonne <xref:System.Windows.Forms.DataGrid> nel controllo Windows Forms usando le proprietà e i metodi <xref:System.Windows.Forms.GridColumnStylesCollection> degli <xref:System.Windows.Forms.DataGridColumnStyle> oggetti e (che sono membri della <xref:System.Windows.Forms.DataGridTableStyle> classe).</span><span class="sxs-lookup"><span data-stu-id="a8494-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="a8494-106">Le colonne eliminate o nascoste sono ancora presenti nell'origine dati a cui è associata la griglia ed è comunque possibile accedervi a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="a8494-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="a8494-107">Non sono più visibili nell'elemento DataGrid.</span><span class="sxs-lookup"><span data-stu-id="a8494-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a8494-108">Se l'applicazione non accede ad alcune colonne di dati e non si desidera che vengano visualizzate nel DataGrid, è probabile che non sia necessario includerle nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="a8494-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="a8494-109">Per eliminare una colonna da DataGrid a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a8494-109">To delete a column from the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="a8494-110">Nell'area dichiarazioni del form dichiarare una nuova istanza della <xref:System.Windows.Forms.DataGridTableStyle> classe.</span><span class="sxs-lookup"><span data-stu-id="a8494-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="a8494-111">Impostare la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> proprietà sulla tabella nell'origine dati a cui si desidera applicare lo stile.</span><span class="sxs-lookup"><span data-stu-id="a8494-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="a8494-112">Nell'esempio seguente viene usata <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> la proprietà, che presuppone che sia già impostata.</span><span class="sxs-lookup"><span data-stu-id="a8494-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="a8494-113">Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella del DataGrid.</span><span class="sxs-lookup"><span data-stu-id="a8494-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="a8494-114">Chiamare il <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> metodo <xref:System.Windows.Forms.DataGrid>della raccolta di <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> , specificando l'indice di colonna della colonna da eliminare.</span><span class="sxs-lookup"><span data-stu-id="a8494-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="a8494-115">Per nascondere una colonna nella griglia a livello di codice</span><span class="sxs-lookup"><span data-stu-id="a8494-115">To hide a column in the DataGrid programmatically</span></span>  
  
1. <span data-ttu-id="a8494-116">Nell'area dichiarazioni del form dichiarare una nuova istanza della <xref:System.Windows.Forms.DataGridTableStyle> classe.</span><span class="sxs-lookup"><span data-stu-id="a8494-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2. <span data-ttu-id="a8494-117">Impostare la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà dell'oggetto <xref:System.Windows.Forms.DataGridTableStyle> sulla tabella nell'origine dati a cui si desidera applicare lo stile.</span><span class="sxs-lookup"><span data-stu-id="a8494-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="a8494-118">Nell'esempio di codice seguente viene <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> usata la proprietà, che presuppone è già impostata.</span><span class="sxs-lookup"><span data-stu-id="a8494-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3. <span data-ttu-id="a8494-119">Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella del DataGrid.</span><span class="sxs-lookup"><span data-stu-id="a8494-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4. <span data-ttu-id="a8494-120">Nascondere la colonna impostando la `Width` relativa proprietà su 0, specificando l'indice di colonna della colonna da nascondere.</span><span class="sxs-lookup"><span data-stu-id="a8494-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8494-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8494-121">See also</span></span>

- [<span data-ttu-id="a8494-122">Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8494-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](change-displayed-data-at-run-time-wf-datagrid-control.md)
- [<span data-ttu-id="a8494-123">Procedura: Aggiungere tabelle e colonne al controllo Windows Forms DataGrid</span><span class="sxs-lookup"><span data-stu-id="a8494-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
