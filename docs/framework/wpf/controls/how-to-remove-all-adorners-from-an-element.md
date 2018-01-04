---
title: 'Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento'
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
helpviewer_keywords: adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0f7bb16c2cd641579706609ff14ca16cc57bd620
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="6c796-102">Procedura: rimuovere tutti gli strumenti decorativi visuali da un elemento</span><span class="sxs-lookup"><span data-stu-id="6c796-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="6c796-103">In questo esempio viene illustrato come rimuovere a livello di codice tutti gli strumenti decorativi da un oggetto specificato <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="6c796-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c796-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c796-104">Example</span></span>  
 <span data-ttu-id="6c796-105">Questo esempio di codice dettagliato rimuove tutti gli strumenti decorativi nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="6c796-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="6c796-106">Questo esempio vengono recuperati gli strumenti decorativi su un <xref:System.Windows.UIElement> denominato *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="6c796-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="6c796-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> senza strumenti decorativi visuali, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="6c796-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="6c796-108">Questo codice verifica la presenza di una matrice null, in modo esplicito ed è più adatto per le applicazioni in una matrice null deve essere abbastanza comune.</span><span class="sxs-lookup"><span data-stu-id="6c796-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="6c796-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="6c796-109">Example</span></span>  
 <span data-ttu-id="6c796-110">In questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="6c796-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="6c796-111">Questo codice non controllano in modo esplicito una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> può essere generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6c796-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="6c796-112">Questo codice è più adatto per le applicazioni in cui in cui è prevista una matrice null rari.</span><span class="sxs-lookup"><span data-stu-id="6c796-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="6c796-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c796-113">See Also</span></span>  
 [<span data-ttu-id="6c796-114">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="6c796-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
