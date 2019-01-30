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
ms.openlocfilehash: 6c1e3318afeb8147e96dc3abc5417f2c29509d13
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55274898"
---
# <a name="how-to-manipulate-a-tables-row-groups-through-the-rowgroups-property"></a><span data-ttu-id="9b026-102">Procedura: Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="9b026-102">How to: Manipulate a Table's Row Groups through the RowGroups Property</span></span>
<span data-ttu-id="9b026-103">In questo esempio vengono illustrate alcune delle operazioni più comuni che possono essere eseguite su gruppi di righe di una tabella tramite il <xref:System.Windows.Documents.Table.RowGroups%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="9b026-103">This example demonstrates some of the more common operations that can be performed on a table's row groups through the <xref:System.Windows.Documents.Table.RowGroups%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b026-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-104">Example</span></span>  
 <span data-ttu-id="9b026-105">Nell'esempio seguente crea una nuova tabella e quindi Usa il <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> metodo per aggiungere colonne alla tabella <xref:System.Windows.Documents.Table.RowGroups%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="9b026-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableRowGroupCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.RowGroups%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_add)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_add)]  
  
## <a name="example"></a><span data-ttu-id="9b026-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-106">Example</span></span>  
 <span data-ttu-id="9b026-107">L'esempio seguente inserisce una nuova <xref:System.Windows.Documents.TableRowGroup>.</span><span class="sxs-lookup"><span data-stu-id="9b026-107">The following example inserts a new <xref:System.Windows.Documents.TableRowGroup>.</span></span>  <span data-ttu-id="9b026-108">La nuova colonna viene inserita nella posizione di indice 0, rendendo la prima riga nuovo gruppo nella tabella.</span><span class="sxs-lookup"><span data-stu-id="9b026-108">The new column is inserted at index position 0, making it the new first row group in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b026-109">Il <xref:System.Windows.Documents.TableRowGroupCollection> raccolta Usa un'indicizzazione in base zero standard.</span><span class="sxs-lookup"><span data-stu-id="9b026-109">The <xref:System.Windows.Documents.TableRowGroupCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_insert)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_insert)]  
  
## <a name="example"></a><span data-ttu-id="9b026-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-110">Example</span></span>  
 <span data-ttu-id="9b026-111">L'esempio seguente aggiunge più righe a un determinato <xref:System.Windows.Documents.TableRowGroup> (specificato in base all'indice) nella tabella.</span><span class="sxs-lookup"><span data-stu-id="9b026-111">The following example adds several rows to a particular <xref:System.Windows.Documents.TableRowGroup> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addrows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addrows)]  
  
## <a name="example"></a><span data-ttu-id="9b026-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-112">Example</span></span>  
 <span data-ttu-id="9b026-113">Nell'esempio seguente accede ad alcune proprietà arbitrarie nelle righe nel primo gruppo di righe nella tabella.</span><span class="sxs-lookup"><span data-stu-id="9b026-113">The following example accesses some arbitrary properties on rows in the first row group in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_maniprows)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipRows](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_maniprows)]  
  
## <a name="example"></a><span data-ttu-id="9b026-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-114">Example</span></span>  
 <span data-ttu-id="9b026-115">L'esempio seguente aggiunge diverse celle di un particolare <xref:System.Windows.Documents.TableRow> (specificato in base all'indice) nella tabella.</span><span class="sxs-lookup"><span data-stu-id="9b026-115">The following example adds several cells to a particular <xref:System.Windows.Documents.TableRow> (specified by index) in the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_addcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_AddCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_addcells)]  
  
## <a name="example"></a><span data-ttu-id="9b026-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-116">Example</span></span>  
 <span data-ttu-id="9b026-117">Nell'esempio seguente accedere alcuni metodi e proprietà arbitrari per le celle nella prima riga nel primo gruppo di righe.</span><span class="sxs-lookup"><span data-stu-id="9b026-117">The following example access some arbitrary methods and properties on cells in the first row in the first row group.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_manipcells)]
 [!code-vb[TableSnippets2#_Table_RowGroups_ManipCells](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_manipcells)]  
  
## <a name="example"></a><span data-ttu-id="9b026-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-118">Example</span></span>  
 <span data-ttu-id="9b026-119">L'esempio seguente restituisce il numero di <xref:System.Windows.Documents.TableRowGroup> elementi ospitati dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="9b026-119">The following example returns the number of <xref:System.Windows.Documents.TableRowGroup> elements hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_count)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_count)]  
  
## <a name="example"></a><span data-ttu-id="9b026-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-120">Example</span></span>  
 <span data-ttu-id="9b026-121">L'esempio seguente rimuove un gruppo di righe specifico per riferimento.</span><span class="sxs-lookup"><span data-stu-id="9b026-121">The following example removes a particular row group by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delref)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delref)]  
  
## <a name="example"></a><span data-ttu-id="9b026-122">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-122">Example</span></span>  
 <span data-ttu-id="9b026-123">L'esempio seguente rimuove un gruppo di righe specifico in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="9b026-123">The following example removes a particular row group by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_delindex)]
 [!code-vb[TableSnippets2#_Table_RowGroups_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_delindex)]  
  
## <a name="example"></a><span data-ttu-id="9b026-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b026-124">Example</span></span>  
 <span data-ttu-id="9b026-125">Nell'esempio seguente rimuove tutti i gruppi di righe dalla raccolta di gruppi di righe della tabella.</span><span class="sxs-lookup"><span data-stu-id="9b026-125">The following example removes all row groups from the table's row groups collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_rowgroups_clear)]
 [!code-vb[TableSnippets2#_Table_RowGroups_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_rowgroups_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="9b026-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9b026-126">See also</span></span>
- [<span data-ttu-id="9b026-127">Procedura: Modificare elementi di contenuto dinamico tramite la proprietà Inlines</span><span class="sxs-lookup"><span data-stu-id="9b026-127">How-to: Manipulate Flow Content Elements through the Inlines Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="9b026-128">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="9b026-128">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="9b026-129">Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="9b026-129">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)
