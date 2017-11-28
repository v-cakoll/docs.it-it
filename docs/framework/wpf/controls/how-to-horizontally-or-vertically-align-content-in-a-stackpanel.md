---
title: 'Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel'
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
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bccf0455c736d14bd77113841603022d4c362787
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a>Procedura: allineare orizzontalmente o verticalmente il contenuto in un elemento StackPanel
In questo esempio viene illustrato come modificare il <xref:System.Windows.Controls.StackPanel.Orientation%2A> del contenuto all'interno di un <xref:System.Windows.Controls.StackPanel> elemento e come modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> del contenuto figlio.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente crea tre <xref:System.Windows.Controls.ListBox> elementi [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]. Ogni <xref:System.Windows.Controls.ListBox> rappresenta i valori possibili del <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, e <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> le proprietà di un <xref:System.Windows.Controls.StackPanel>. Quando un utente seleziona un valore in uno del <xref:System.Windows.Controls.ListBox> elementi, la proprietà associata del <xref:System.Windows.Controls.StackPanel> e del relativo figlio <xref:System.Windows.Controls.Button> modificare gli elementi.  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 Il file code-behind seguente definisce le modifiche agli eventi che sono associati le <xref:System.Windows.Controls.ListBox> di selezione cambia. <xref:System.Windows.Controls.StackPanel>identificato dal <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.StackPanel>  
 <xref:System.Windows.Controls.ListBox>  
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>  
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>  
 [Cenni preliminari sugli elementi Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
