---
title: "Procedura: cercare l'elemento di origine in un gestore eventi"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: c3ae893cd7fd7780854d6eb6ffd682feadb5c5a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544004"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="a3f7d-102">Procedura: cercare l'elemento di origine in un gestore eventi</span><span class="sxs-lookup"><span data-stu-id="a3f7d-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="a3f7d-103">In questo esempio viene illustrato come trovare l'elemento di origine in un gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="a3f7d-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3f7d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a3f7d-104">Example</span></span>  
 <span data-ttu-id="a3f7d-105">Nell'esempio seguente un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestore eventi che è dichiarato in un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="a3f7d-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="a3f7d-106">Quando un utente fa clic sul pulsante che è associato il gestore per, il gestore imposta un valore di proprietà.</span><span class="sxs-lookup"><span data-stu-id="a3f7d-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="a3f7d-107">Utilizza il codice del gestore di <xref:System.Windows.RoutedEventArgs.Source%2A> proprietà dei dati dell'evento indirizzato che viene segnalati negli argomenti dell'evento per modificare il <xref:System.Windows.FrameworkElement.Width%2A> sul valore della proprietà di <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.</span><span class="sxs-lookup"><span data-stu-id="a3f7d-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="a3f7d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3f7d-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="a3f7d-109">Cenni preliminari sugli eventi indirizzati</span><span class="sxs-lookup"><span data-stu-id="a3f7d-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="a3f7d-110">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="a3f7d-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
