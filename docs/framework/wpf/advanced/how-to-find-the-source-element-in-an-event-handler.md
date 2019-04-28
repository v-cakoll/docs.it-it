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
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757508"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="f4ba5-102">Procedura: Cercare l'elemento di origine in un gestore eventi</span><span class="sxs-lookup"><span data-stu-id="f4ba5-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="f4ba5-103">In questo esempio viene illustrato come trovare l'elemento di origine in un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f4ba5-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4ba5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f4ba5-104">Example</span></span>  
 <span data-ttu-id="f4ba5-105">L'esempio seguente mostra un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi che è dichiarato in un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="f4ba5-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="f4ba5-106">Quando un utente fa clic sul pulsante con il gestore di è collegato a, il gestore di modifica un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="f4ba5-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="f4ba5-107">Usa il codice del gestore il <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà dei dati dell'evento indirizzato che viene segnalati negli argomenti di evento per modificare il <xref:System.Windows.FrameworkElement.Width%2A> sul valore della proprietà di <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.</span><span class="sxs-lookup"><span data-stu-id="f4ba5-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="f4ba5-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f4ba5-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="f4ba5-109">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="f4ba5-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="f4ba5-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="f4ba5-110">How-to Topics</span></span>](events-how-to-topics.md)
