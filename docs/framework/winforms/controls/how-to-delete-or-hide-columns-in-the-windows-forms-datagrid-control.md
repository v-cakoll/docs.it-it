---
title: 'Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d89f14d034c1050d364282c04424b1326bcff9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control"></a><span data-ttu-id="57c02-102">Procedura: eliminare o nascondere colonne nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="57c02-102">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="57c02-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="57c02-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="57c02-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="57c02-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="57c02-105">Puoi eliminare o nascondere le colonne in Windows Form a livello di programmazione <xref:System.Windows.Forms.DataGrid> controllo utilizzando le proprietà e metodi del <xref:System.Windows.Forms.GridColumnStylesCollection> e <xref:System.Windows.Forms.DataGridColumnStyle> oggetti (che sono membri del <xref:System.Windows.Forms.DataGridTableStyle> classe).</span><span class="sxs-lookup"><span data-stu-id="57c02-105">You can programmatically delete or hide columns in the Windows Forms <xref:System.Windows.Forms.DataGrid> control by using the properties and methods of the <xref:System.Windows.Forms.GridColumnStylesCollection> and <xref:System.Windows.Forms.DataGridColumnStyle> objects (which are members of the <xref:System.Windows.Forms.DataGridTableStyle> class).</span></span>  
  
 <span data-ttu-id="57c02-106">Le colonne eliminate o nascoste ancora presenti nell'origine dei dati, la griglia è associata a e può comunque accedere a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="57c02-106">The deleted or hidden columns still exist in the data source the grid is bound to, and can still be accessed programmatically.</span></span> <span data-ttu-id="57c02-107">Non sono semplicemente più visibile nel controllo datagrid.</span><span class="sxs-lookup"><span data-stu-id="57c02-107">They are just no longer visible in the datagrid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57c02-108">Se l'applicazione non accedere ad alcune colonne di dati e non si desidera visualizzarli nel controllo datagrid, quindi è probabile che non necessario includerli in primo luogo nell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="57c02-108">If your application does not access certain columns of data, and you do not want them displayed in the datagrid, then it is probably not necessary to include them in the data source in the first place.</span></span>  
  
### <a name="to-delete-a-column-from-the-datagrid-programmatically"></a><span data-ttu-id="57c02-109">Per eliminare una colonna da DataGrid a livello di codice</span><span class="sxs-lookup"><span data-stu-id="57c02-109">To delete a column from the DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="57c02-110">Nella sezione delle dichiarazioni del form, dichiarare una nuova istanza di <xref:System.Windows.Forms.DataGridTableStyle> classe.</span><span class="sxs-lookup"><span data-stu-id="57c02-110">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2.  <span data-ttu-id="57c02-111">Impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> proprietà alla tabella nell'origine dati che si desidera applicare lo stile.</span><span class="sxs-lookup"><span data-stu-id="57c02-111">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A?displayProperty=nameWithType> property to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="57c02-112">L'esempio seguente usa il <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> proprietà, si presuppone che è già impostato.</span><span class="sxs-lookup"><span data-stu-id="57c02-112">The following example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3.  <span data-ttu-id="57c02-113">Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella della griglia.</span><span class="sxs-lookup"><span data-stu-id="57c02-113">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4.  <span data-ttu-id="57c02-114">Chiamare il <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> metodo il <xref:System.Windows.Forms.DataGrid>del <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> insieme, specificando l'indice della colonna da eliminare.</span><span class="sxs-lookup"><span data-stu-id="57c02-114">Call the <xref:System.Windows.Forms.GridColumnStylesCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DataGrid>'s <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> collection, specifying the column index of the column to delete.</span></span>  
  
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
  
### <a name="to-hide-a-column-in-the-datagrid-programmatically"></a><span data-ttu-id="57c02-115">Per nascondere una colonna nel controllo DataGrid a livello di codice</span><span class="sxs-lookup"><span data-stu-id="57c02-115">To hide a column in the DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="57c02-116">Nella sezione delle dichiarazioni del form, dichiarare una nuova istanza di <xref:System.Windows.Forms.DataGridTableStyle> classe.</span><span class="sxs-lookup"><span data-stu-id="57c02-116">In the declarations area of your form, declare a new instance of the <xref:System.Windows.Forms.DataGridTableStyle> class.</span></span>  
  
2.  <span data-ttu-id="57c02-117">Impostare il <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> proprietà del <xref:System.Windows.Forms.DataGridTableStyle> alla tabella nell'origine dati che si desidera applicare lo stile.</span><span class="sxs-lookup"><span data-stu-id="57c02-117">Set the <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property of the <xref:System.Windows.Forms.DataGridTableStyle> to the table in your data source that you want to apply the style to.</span></span> <span data-ttu-id="57c02-118">Nell'esempio di codice viene illustrato come utilizzare il <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> proprietà, si presuppone che è già impostato.</span><span class="sxs-lookup"><span data-stu-id="57c02-118">The following code example uses the <xref:System.Windows.Forms.DataGrid.DataMember%2A?displayProperty=nameWithType> property, which it assumes is already set.</span></span>  
  
3.  <span data-ttu-id="57c02-119">Aggiungere il nuovo <xref:System.Windows.Forms.DataGridTableStyle> oggetto alla raccolta di stili di tabella della griglia.</span><span class="sxs-lookup"><span data-stu-id="57c02-119">Add the new <xref:System.Windows.Forms.DataGridTableStyle> object to the datagrid's table styles collection.</span></span>  
  
4.  <span data-ttu-id="57c02-120">Nascondere la colonna impostando il relativo `Width` proprietà su 0, che specifica l'indice di colonna della colonna da nascondere.</span><span class="sxs-lookup"><span data-stu-id="57c02-120">Hide the column by setting its `Width` property to 0, specifying the column index of the column to hide.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57c02-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57c02-121">See Also</span></span>  
 [<span data-ttu-id="57c02-122">Procedura: Modificare i dati visualizzati in fase di esecuzione nel controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="57c02-122">How to: Change Displayed Data at Run Time in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/change-displayed-data-at-run-time-wf-datagrid-control.md)  
 [<span data-ttu-id="57c02-123">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="57c02-123">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
