---
title: "Procedura: Cercare l'elemento di origine in un gestore eventi"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 4cdf1434f2d341cbc1e65541fd02ab4b5cad194d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536737"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Procedura: Cercare l'elemento di origine in un gestore eventi
In questo esempio viene illustrato come trovare l'elemento di origine in un gestore eventi.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente mostra un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi che è dichiarato in un file code-behind. Quando un utente fa clic sul pulsante con il gestore di è collegato a, il gestore di modifica un valore della proprietà. Usa il codice del gestore il <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà dei dati dell'evento indirizzato che viene segnalati negli argomenti di evento per modificare il <xref:System.Windows.FrameworkElement.Width%2A> sul valore della proprietà di <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.RoutedEventArgs>
- [Cenni preliminari sugli eventi indirizzati](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
