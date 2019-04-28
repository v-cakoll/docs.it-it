---
title: 'Procedura: Modificare la proprietà TextWrapping a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], changing TextWrapping property programmatically
- TextWrapping property [WPF], changing programmatically
ms.assetid: 30d25554-4c82-4df9-a8d6-35683a4a13bb
ms.openlocfilehash: 21ca31d24121492fe6927cd533d5b3c0785b5a28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776662"
---
# <a name="how-to-change-the-textwrapping-property-programmatically"></a>Procedura: Modificare la proprietà TextWrapping a livello di codice
## <a name="example"></a>Esempio  
 Esempio di codice seguente viene illustrato come modificare il valore della <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> proprietà a livello di codice.  
  
 Tre <xref:System.Windows.Controls.Button> elementi vengono posizionati all'interno di un <xref:System.Windows.Controls.StackPanel> elemento [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]. Ciascuna <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento per un <xref:System.Windows.Controls.Button> corrisponde a un gestore eventi nel codice. I gestori eventi usano lo stesso nome di <xref:System.Windows.Controls.TextBlock.TextWrapping%2A> valore verranno applicate a `txt2` quando fa clic sul pulsante. Inoltre, il testo nel `txt1` (una <xref:System.Windows.Controls.TextBlock> non visualizzati nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]) viene aggiornato per riflettere la modifica della proprietà.  
  
 [!code-xaml[TextWrapProperty#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml#1)]  
  
 [!code-csharp[TextWrapProperty#2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextWrapProperty/CSharp/Window1.xaml.cs#2)]
 [!code-vb[TextWrapProperty#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextWrapProperty/VisualBasic/Pane1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TextBlock.TextWrapping%2A>
- <xref:System.Windows.TextWrapping>
