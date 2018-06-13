---
title: 'Procedura: condividere le proprietà di ridimensionamento tra griglie'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], sharing sizing data of columns
- sizing data in Grid controls [WPF]
- Grid control [WPF], sharing sizing data of rows
ms.assetid: a0535a6f-ff04-4b25-9912-7dd856e11044
ms.openlocfilehash: a85c0c36ef99e6501afddaca7f26acd2928da1ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33550865"
---
# <a name="how-to-share-sizing-properties-between-grids"></a>Procedura: condividere le proprietà di ridimensionamento tra griglie
In questo esempio viene illustrato come condividere i dati di ridimensionamento di colonne e righe tra <xref:System.Windows.Controls.Grid> elementi per mantenere coerente il ridimensionamento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono presentate due <xref:System.Windows.Controls.Grid> elementi come elementi figlio di un elemento padre <xref:System.Windows.Controls.DockPanel>. Il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> associata di <xref:System.Windows.Controls.Grid> è definito nell'elemento padre, <xref:System.Windows.Controls.DockPanel>.  
  
 L'esempio modifica il valore della proprietà usando due <xref:System.Windows.Controls.Button> elementi; ogni elemento rappresenta uno dei valori di proprietà booleana. Quando il <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A> il valore di proprietà è impostato su `true`, ogni membro di riga o colonna di un <xref:System.Windows.Controls.DefinitionBase.SharedSizeGroup%2A> condivide informazioni sul ridimensionamento, indipendentemente dal contenuto di una riga o colonna.  
  
 [!code-xaml[gridIssharedsizescopeProp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#1)]  
  
 ...  
  
 [!code-xaml[gridIssharedsizescopeProp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml#2)]  
  
 Nell'esempio di codice seguente gestisce i metodi che il pulsante <xref:System.Windows.Controls.Primitives.ButtonBase.Click> genera eventi. L'esempio scrive i risultati delle chiamate al metodo <xref:System.Windows.Controls.TextBlock> gli elementi correlati utilizzare metodi get per restituire i nuovi valori di proprietà come stringhe.  
  
 [!code-csharp[gridIssharedsizescopeProp#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridIssharedsizescopeProp/CSharp/Window1.xaml.cs#3)]
 [!code-vb[gridIssharedsizescopeProp#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridIssharedsizescopeProp/VisualBasic/Window1.xaml.vb#3)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Controls.Grid.IsSharedSizeScope%2A>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
