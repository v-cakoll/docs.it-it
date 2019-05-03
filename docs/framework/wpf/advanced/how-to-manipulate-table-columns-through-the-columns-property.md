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
ms.openlocfilehash: d379d1a98bff614ff9e16cdd340bb69644988743
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051468"
---
# <a name="how-to-manipulate-a-tables-columns-through-the-columns-property"></a>Procedura: Modificare le colonne di una tabella tramite la proprietà Columns
In questo esempio vengono illustrate alcune delle operazioni più comuni che possono essere eseguite su colonne di una tabella tramite il <xref:System.Windows.Documents.Table.Columns%2A> proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente crea una nuova tabella e quindi Usa il <xref:System.Windows.Documents.TableColumnCollection.Add%2A> metodo per aggiungere colonne alla tabella <xref:System.Windows.Documents.Table.Columns%2A> raccolta.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Add](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_add)]
 [!code-vb[TableSnippets2#_Table_Columns_Add](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_add)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente inserisce una nuova <xref:System.Windows.Documents.TableColumn>.  La nuova colonna viene inserita nella posizione di indice 0, rendendo la prima colonna della tabella.  
  
> [!NOTE]
>  Il <xref:System.Windows.Documents.TableColumnCollection> raccolta Usa un'indicizzazione in base zero standard.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_insert)]
 [!code-vb[TableSnippets2#_Table_Columns_Insert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_insert)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente accede ad alcune proprietà arbitrarie per le colonne nel <xref:System.Windows.Documents.TableColumnCollection> raccolta, che fa riferimento a colonne specifiche in base all'indice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_manip)]
 [!code-vb[TableSnippets2#_Table_Columns_Manip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_manip)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente ottiene il numero delle colonne attualmente ospitati dalla tabella.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Count](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_count)]
 [!code-vb[TableSnippets2#_Table_Columns_Count](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_count)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente rimuove una colonna specifica per riferimento.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delref)]
 [!code-vb[TableSnippets2#_Table_Columns_DelRef](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delref)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente rimuove una colonna specifica in base all'indice.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_delindex)]
 [!code-vb[TableSnippets2#_Table_Columns_DelIndex](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_delindex)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente rimuove tutte le colonne dalla raccolta di colonne della tabella.  
  
 [!code-csharp[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml.cs#_table_columns_clear)]
 [!code-vb[TableSnippets2#_Table_Columns_Clear](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets2/visualbasic/window1.xaml.vb#_table_columns_clear)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'elemento Table](table-overview.md)
- [Definire un oggetto Table con XAML](how-to-define-a-table-with-xaml.md)
- [Compilare oggetti Table a livello di codice](how-to-build-a-table-programmatically.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
- [Modificare un oggetto FlowDocument tramite la proprietà Blocks](how-to-manipulate-a-flowdocument-through-the-blocks-property.md)
- [Modificare i gruppi di righe di una tabella tramite la proprietà RowGroups](how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
