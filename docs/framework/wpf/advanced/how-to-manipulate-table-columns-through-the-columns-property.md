---
title: 'Procedura: Modificare le colonne di una tabella tramite la proprietà Columns'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
ms.openlocfilehash: e7b2c1923f7262417f44cb5ac2ea057ef6c83690
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57358509"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a><span data-ttu-id="bc2bc-102">Procedura: Modificare le colonne di una tabella tramite la proprietà Columns</span><span class="sxs-lookup"><span data-stu-id="bc2bc-102">How to: Manipulate a Table's Columns through the Columns Property</span></span>
<span data-ttu-id="bc2bc-103">In questo esempio vengono illustrate alcune delle operazioni più comuni che possono essere eseguite su colonne di una tabella tramite il <xref:System.Windows.Documents.Table.Columns%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc2bc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-104">Example</span></span>  
 <span data-ttu-id="bc2bc-105">Nell'esempio seguente crea una nuova tabella e quindi Usa il <xref:System.Windows.Documents.TableColumnCollection.Add%2A> metodo per aggiungere colonne alla tabella <xref:System.Windows.Documents.Table.Columns%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="bc2bc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-106">Example</span></span>  
 <span data-ttu-id="bc2bc-107">L'esempio seguente inserisce una nuova <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="bc2bc-108">La nuova colonna viene inserita nella posizione di indice 0, rendendo la prima colonna della tabella.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc2bc-109">Il <xref:System.Windows.Documents.TableColumnCollection> raccolta Usa un'indicizzazione in base zero standard.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="bc2bc-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-110">Example</span></span>  
 <span data-ttu-id="bc2bc-111">Nell'esempio seguente accede ad alcune proprietà arbitrarie per le colonne nel <xref:System.Windows.Documents.TableColumnCollection> raccolta, che fa riferimento a colonne specifiche in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="bc2bc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-112">Example</span></span>  
 <span data-ttu-id="bc2bc-113">Nell'esempio seguente ottiene il numero delle colonne attualmente ospitati dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="bc2bc-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-114">Example</span></span>  
 <span data-ttu-id="bc2bc-115">L'esempio seguente rimuove una colonna specifica per riferimento.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="bc2bc-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-116">Example</span></span>  
 <span data-ttu-id="bc2bc-117">L'esempio seguente rimuove una colonna specifica in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="bc2bc-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="bc2bc-118">Example</span></span>  
 <span data-ttu-id="bc2bc-119">Nell'esempio seguente rimuove tutte le colonne dalla raccolta di colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="bc2bc-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="bc2bc-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bc2bc-120">See also</span></span>
- [<span data-ttu-id="bc2bc-121">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="bc2bc-121">Table Overview</span></span>](table-overview.md)
- [<span data-ttu-id="bc2bc-122">Definire un oggetto Table con XAML</span><span class="sxs-lookup"><span data-stu-id="bc2bc-122">Define a Table with XAML</span></span>](how-to-define-a-table-with-xaml.md)
- [<span data-ttu-id="bc2bc-123">Compilare oggetti Table a livello di codice</span><span class="sxs-lookup"><span data-stu-id="bc2bc-123">Build a Table Programmatically</span></span>](how-to-build-a-table-programmatically.md)
- [<span data-ttu-id="bc2bc-124">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="bc2bc-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [<span data-ttu-id="bc2bc-125">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="bc2bc-125">Manipulate a FlowDocument through the Blocks Property</span></span>](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [<span data-ttu-id="bc2bc-126">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="bc2bc-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
