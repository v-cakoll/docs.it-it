---
title: 'Procedura: trovare elementi generati da un oggetto DataTemplate'
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
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22d5f393d376935f04459e2713e9658c80af6efa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-datatemplate-generated-elements"></a>Procedura: trovare elementi generati da un oggetto DataTemplate
In questo esempio viene illustrato come trovare gli elementi che vengono generati da un <xref:System.Windows.DataTemplate>.  
  
## <a name="example"></a>Esempio  
 In questo esempio, è presente un <xref:System.Windows.Controls.ListBox> associato ad alcuni [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati:  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 Il <xref:System.Windows.Controls.ListBox> utilizza il seguente <xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 Se si desidera recuperare il <xref:System.Windows.Controls.TextBlock> generato dall'elemento il <xref:System.Windows.DataTemplate> di un determinato <xref:System.Windows.Controls.ListBoxItem>, è necessario ottenere il <xref:System.Windows.Controls.ListBoxItem>, trovare il <xref:System.Windows.Controls.ContentPresenter> all'interno che <xref:System.Windows.Controls.ListBoxItem>e quindi chiamare <xref:System.Windows.FrameworkTemplate.FindName%2A> sul <xref:System.Windows.DataTemplate> che è impostato su tale <xref:System.Windows.Controls.ContentPresenter>. Nell'esempio seguente viene illustrato come eseguire questi passaggi. A scopo dimostrativo, questo esempio viene creata una finestra di messaggio che viene visualizzato il testo del contenuto del <xref:System.Windows.DataTemplate>-blocco di testo generato.  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 Di seguito è l'implementazione di `FindVisualChild`, che utilizza il <xref:System.Windows.Media.VisualTreeHelper> metodi:  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: trovare elementi generati da un oggetto ControlTemplate](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [Cenni preliminari sull'associazione dati](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Procedure relative](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [Applicazione di stili e modelli](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [Ambiti dei nomi XAML WPF](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [Strutture ad albero in WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
