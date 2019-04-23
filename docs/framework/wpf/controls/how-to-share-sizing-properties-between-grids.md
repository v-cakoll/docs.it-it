---
title: 'Procedura: Condividere le proprietà di ridimensionamento tra elementi Grid'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: d5ab2ac612d55c8cbc34ae6d7d9d63b9f8aa23e7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190340"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Procedura: Condividere le proprietà di ridimensionamento tra elementi Grid
In questo esempio mostra come condividere i dati di ridimensionamento di colonne e righe tra <xref:System.Windows.Controls.Grid> elementi per mantenere coerente il ridimensionamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono introdotti due <xref:System.Windows.Controls.Grid> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel>. Il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> proprietà collegata <xref:System.Windows.Controls.Grid> viene definito nell'elemento padre <xref:System.Windows.Controls.DockPanel>.  
  
 L'esempio modifica il valore della proprietà usando due <xref:System.Windows.Controls.Button> elementi; ogni elemento rappresenta uno dei valori della proprietà booleana. Quando la <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> valore della proprietà è impostato su `true`, ogni membro di riga o colonna di una <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> condivide le informazioni sul ridimensionamento, indipendentemente dal contenuto di una riga o colonna.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 L'esempio di codice seguente gestisce i metodi che il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> generati dagli eventi. L'esempio scrive i risultati di chiamate ai metodi <xref:System.Windows.Controls.TextBlock> gli elementi correlati Usa metodi get per restituire i nuovi valori di proprietà come stringhe.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](~/samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
