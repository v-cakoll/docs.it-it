---
title: "Procedura: modificare una tabella &#39; s colonne tramite la proprietà di colonne"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], manipulating table columns
- properties [WPF], Columns [WPF], manipulating table columns
- tables [WPF], manipulating columns
- Columns property [WPF]
ms.assetid: 3f8884f4-7e1f-456b-be06-fbd3cf469bf3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d0f15339b829335798d7ee21dcc90b81cb536cf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a><span data-ttu-id="984ce-102">Procedura: modificare una tabella &#39; s colonne tramite la proprietà di colonne</span><span class="sxs-lookup"><span data-stu-id="984ce-102">How to: Manipulate a Table&#39;s Columns through the Columns Property</span></span>
<span data-ttu-id="984ce-103">In questo esempio vengono illustrate alcune delle operazioni più comuni che possono essere eseguite su colonne di una tabella tramite il <xref:System.Windows.Documents.Table.Columns%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="984ce-103">This example demonstrates some of the more common operations that can be performed on a table's columns through the <xref:System.Windows.Documents.Table.Columns%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="984ce-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-104">Example</span></span>  
 <span data-ttu-id="984ce-105">Nell'esempio seguente viene creata una nuova tabella e quindi utilizza il <xref:System.Windows.Documents.TableColumnCollection.Add%2A> metodo per aggiungere colonne alla tabella <xref:System.Windows.Documents.Table.Columns%2A> insieme.</span><span class="sxs-lookup"><span data-stu-id="984ce-105">The following example creates a new table and then uses the <xref:System.Windows.Documents.TableColumnCollection.Add%2A> method to add columns to the table's <xref:System.Windows.Documents.Table.Columns%2A> collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a><span data-ttu-id="984ce-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-106">Example</span></span>  
 <span data-ttu-id="984ce-107">Nell'esempio seguente viene inserita una nuova <xref:System.Windows.Documents.TableColumn>.</span><span class="sxs-lookup"><span data-stu-id="984ce-107">The following example inserts a new <xref:System.Windows.Documents.TableColumn>.</span></span>  <span data-ttu-id="984ce-108">La nuova colonna viene inserita in corrispondenza della posizione di indice 0, in modo che la prima colonna nella tabella.</span><span class="sxs-lookup"><span data-stu-id="984ce-108">The new column is inserted at index position 0, making it the new first column in the table.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="984ce-109">Il <xref:System.Windows.Documents.TableColumnCollection> insieme utilizza l'indicizzazione in base zero standard.</span><span class="sxs-lookup"><span data-stu-id="984ce-109">The <xref:System.Windows.Documents.TableColumnCollection> collection uses standard zero-based indexing.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a><span data-ttu-id="984ce-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-110">Example</span></span>  
 <span data-ttu-id="984ce-111">Nell'esempio seguente consente di accedere alcune proprietà arbitrarie sulle colonne di <xref:System.Windows.Documents.TableColumnCollection> raccolta, che fa riferimento a colonne specifiche in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="984ce-111">The following example accesses some arbitrary properties on columns in the <xref:System.Windows.Documents.TableColumnCollection> collection, referring to particular columns by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a><span data-ttu-id="984ce-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-112">Example</span></span>  
 <span data-ttu-id="984ce-113">Nell'esempio seguente ottiene il numero di colonne ospitate dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="984ce-113">The following example gets the number of columns currently hosted by the table.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a><span data-ttu-id="984ce-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-114">Example</span></span>  
 <span data-ttu-id="984ce-115">Nell'esempio seguente viene rimossa una colonna per riferimento.</span><span class="sxs-lookup"><span data-stu-id="984ce-115">The following example removes a particular column by reference.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a><span data-ttu-id="984ce-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-116">Example</span></span>  
 <span data-ttu-id="984ce-117">Nell'esempio seguente viene rimossa una colonna in base all'indice.</span><span class="sxs-lookup"><span data-stu-id="984ce-117">The following example removes a particular column by index.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a><span data-ttu-id="984ce-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="984ce-118">Example</span></span>  
 <span data-ttu-id="984ce-119">Nell'esempio seguente rimuove tutte le colonne dalla raccolta di colonne della tabella.</span><span class="sxs-lookup"><span data-stu-id="984ce-119">The following example removes all columns from the table's columns collection.</span></span>  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a><span data-ttu-id="984ce-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="984ce-120">See Also</span></span>  
 [<span data-ttu-id="984ce-121">Cenni preliminari sull'elemento Table</span><span class="sxs-lookup"><span data-stu-id="984ce-121">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [<span data-ttu-id="984ce-122">Definire un oggetto Table con XAML</span><span class="sxs-lookup"><span data-stu-id="984ce-122">Define a Table with XAML</span></span>](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [<span data-ttu-id="984ce-123">Compilare oggetti Table a livello di codice</span><span class="sxs-lookup"><span data-stu-id="984ce-123">Build a Table Programmatically</span></span>](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)  
 [<span data-ttu-id="984ce-124">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="984ce-124">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [<span data-ttu-id="984ce-125">Modificare un oggetto FlowDocument tramite la proprietà Blocks</span><span class="sxs-lookup"><span data-stu-id="984ce-125">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="984ce-126">Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups</span><span class="sxs-lookup"><span data-stu-id="984ce-126">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
