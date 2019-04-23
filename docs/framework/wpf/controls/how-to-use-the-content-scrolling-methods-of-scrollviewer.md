---
title: 'Procedura: Usare i metodi di scorrimento del contenuto di ScrollViewer'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IScrollInfo interface [WPF]
- scrolling methods [WPF]
- ScrollViewer control [WPF], scrolling methods
ms.assetid: 4708cc65-6510-45f8-82e6-30b0d3e30045
ms.openlocfilehash: e81c63de16d09de8435d5ec49a013bf8dc5927cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142155"
---
# <a name="how-to-use-the-content-scrolling-methods-of-scrollviewer"></a>Procedura: Usare i metodi di scorrimento del contenuto di ScrollViewer
Questo esempio viene illustrato come utilizzare i metodi di scorrimento di <xref:System.Windows.Controls.ScrollViewer> elemento. Questi metodi consentono lo scorrimento incrementale del contenuto, tramite la riga o di pagina, in un <xref:System.Windows.Controls.ScrollViewer>.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea una <xref:System.Windows.Controls.ScrollViewer> denominate `sv1`, che ospita un elemento figlio <xref:System.Windows.Controls.TextBlock> elemento. Poiché il <xref:System.Windows.Controls.TextBlock> è più grande del padre <xref:System.Windows.Controls.ScrollViewer>, vengono visualizzate le barre di scorrimento per abilitare lo scorrimento. <xref:System.Windows.Controls.Button> gli elementi che rappresentano i vari metodi di scorrimento sono ancorati a sinistra in un oggetto separato <xref:System.Windows.Controls.StackPanel>. Ciascuna <xref:System.Windows.Controls.Button> nella [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file chiama un metodo personalizzato correlato che controlla il comportamento dello scorrimento in <xref:System.Windows.Controls.ScrollViewer>.  
  
 [!code-xaml[ScrollViewerMethods#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml#1)]  
  
 L'esempio seguente usa il <xref:System.Windows.Controls.ScrollViewer.LineUp%2A> e <xref:System.Windows.Controls.ScrollViewer.LineDown%2A> metodi.  
  
 [!code-csharp[ScrollViewerMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ScrollViewerMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ScrollViewerMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ScrollViewerMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ScrollViewer>
- <xref:System.Windows.Controls.StackPanel>
