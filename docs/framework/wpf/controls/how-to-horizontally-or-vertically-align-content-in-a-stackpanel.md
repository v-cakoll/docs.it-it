---
title: 'Procedura: Allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: 03348aa0eb5b6c1791c27683c1c6c6a5d4a8a9d4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186043"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Procedura: Allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel
In questo esempio mostra come regolare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> del contenuto all'interno di un <xref:System.Windows.Controls.StackPanel> elemento e anche come regolare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> del contenuto figlio.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea tre <xref:System.Windows.Controls.ListBox> elementi in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Ciascuna <xref:System.Windows.Controls.ListBox> rappresenta i possibili valori del <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> le proprietà di un <xref:System.Windows.Controls.StackPanel>. Quando un utente seleziona un valore in una qualsiasi del <xref:System.Windows.Controls.ListBox> elementi, la proprietà associata del <xref:System.Windows.Controls.StackPanel> e del relativo figlio <xref:System.Windows.Controls.Button> modificare gli elementi.  
  
 [!code-xaml[StackPanelIntroSamp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Il file code-behind seguente definisce le modifiche agli eventi che sono associati le <xref:System.Windows.Controls.ListBox> modifica di selezione. <xref:System.Windows.Controls.StackPanel> viene identificato per la <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](~/samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
