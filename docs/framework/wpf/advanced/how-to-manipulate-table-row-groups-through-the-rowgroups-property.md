---
title: 'Procedura: Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- row groups [WPF], manipulating through RowGroups property
- RowGroups property [WPF], manipulating row groups
- documents [WPF], manipulating row groups through RowGroups property
- properties [WPF], RowGroups [WPF], manipulating row groups
ms.assetid: ea61440f-08ae-44ed-b314-5716aaaae3ed
ms.openlocfilehash: 195920af64888bd3671b45befc0fe4cde463ae7b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913552"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="30bf0-102">Procedura: Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="30bf0-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="30bf0-103">Questo esempio illustra alcune delle operazioni più comuni che è possibile eseguire sui gruppi di righe di una tabella tramite la <xref:System.Windows.Documents.Table.RowGroups%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="30bf0-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30bf0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-104">Example</span></span>  
 <span data-ttu-id="30bf0-105">Nell'esempio seguente viene creata una nuova tabella, quindi viene <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> utilizzato il metodo per aggiungere colonne alla <xref:System.Windows.Documents.Table.RowGroups%2A> raccolta della tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-106">Example</span></span>  
 <span data-ttu-id="30bf0-107">Nell'esempio seguente viene inserito un <xref:System.Windows.Documents.TableRowGroup>nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="30bf0-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="30bf0-108">La nuova colonna viene inserita in corrispondenza della posizione di indice 0, rendendola il nuovo gruppo di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30bf0-109">La <xref:System.Windows.Documents.TableRowGroupCollection> raccolta usa l'indicizzazione in base zero standard.</span><span class="sxs-lookup"><span data-stu-id="30bf0-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-110">Example</span></span>  
 <span data-ttu-id="30bf0-111">Nell'esempio seguente vengono aggiunte più righe a un <xref:System.Windows.Documents.TableRowGroup> particolare (specificato dall'indice) nella tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-112">Example</span></span>  
 <span data-ttu-id="30bf0-113">Nell'esempio seguente vengono accessibili alcune proprietà arbitrarie sulle righe nel primo gruppo di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-114">Example</span></span>  
 <span data-ttu-id="30bf0-115">Nell'esempio seguente vengono aggiunte più celle a un <xref:System.Windows.Documents.TableRow> particolare (specificato dall'indice) nella tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-116">Example</span></span>  
 <span data-ttu-id="30bf0-117">Nell'esempio seguente vengono accessibili alcune proprietà e metodi arbitrari nelle celle della prima riga del primo gruppo di righe.</span><span class="sxs-lookup"><span data-stu-id="30bf0-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-118">Example</span></span>  
 <span data-ttu-id="30bf0-119">Nell'esempio seguente viene restituito il numero <xref:System.Windows.Documents.TableRowGroup> di elementi ospitati dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-120">Example</span></span>  
 <span data-ttu-id="30bf0-121">Nell'esempio seguente viene rimosso un particolare gruppo di righe in base al riferimento.</span><span class="sxs-lookup"><span data-stu-id="30bf0-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-122">Example</span></span>  
 <span data-ttu-id="30bf0-123">Nell'esempio seguente viene rimosso un particolare gruppo di righe in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="30bf0-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="30bf0-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="30bf0-124">Example</span></span>  
 <span data-ttu-id="30bf0-125">Nell'esempio seguente vengono rimossi tutti i gruppi di righe dalla raccolta di gruppi di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="30bf0-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="30bf0-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30bf0-126">See also</span></span>

- [<span data-ttu-id="30bf0-127">Procedura: Modificare gli elementi di contenuto del flusso tramite la proprietà Inlines</span><span class="sxs-lookup"><span data-stu-id="30bf0-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="30bf0-128">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="30bf0-128">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="30bf0-129">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="30bf0-129">Manipulate a Table's Columns through the Columns Property</span></span>](how-to-manipulate-table-columns-through-the-columns-property.md)
