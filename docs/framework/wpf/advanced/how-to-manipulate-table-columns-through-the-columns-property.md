---
title: 'Procedura: modificare una tabella&#39;colonne s tramite la proprietà di colonne'
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
ms.openlocfilehash: 916764c621738ddc651580f1232e1f579a17e6f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-manipulate-a-table39s-columns-through-the-columns-property"></a>Procedura: modificare una tabella&#39;colonne s tramite la proprietà di colonne
In questo esempio vengono illustrate alcune delle operazioni più comuni che possono essere eseguite su colonne di una tabella tramite il <xref:System.Windows.Documents.Table.Columns%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una nuova tabella e quindi utilizza il <xref:System.Windows.Documents.TableColumnCollection.Add%2A> metodo per aggiungere colonne alla tabella <xref:System.Windows.Documents.Table.Columns%2A> insieme.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene inserita una nuova <xref:System.Windows.Documents.TableColumn>.  La nuova colonna viene inserita in corrispondenza della posizione di indice 0, in modo che la prima colonna nella tabella.  
  
> [!NOTE]
>  Il <xref:System.Windows.Documents.TableColumnCollection> insieme utilizza l'indicizzazione in base zero standard.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente consente di accedere alcune proprietà arbitrarie sulle colonne di <xref:System.Windows.Documents.TableColumnCollection> raccolta, che fa riferimento a colonne specifiche in base all'indice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente ottiene il numero di colonne ospitate dalla tabella.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene rimossa una colonna per riferimento.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene rimossa una colonna in base all'indice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente rimuove tutte le colonne dalla raccolta di colonne della tabella.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sull'elemento Table](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [Definire un oggetto Table con XAML](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [Compilare oggetti Table a livello di codice](../../../../docs/framework/wpf/advanced/how-to-build-a-table-programmatically.md)  
 [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [Modificare un oggetto FlowDocument tramite la proprietà Blocks](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
