---
title: 'Procedura: rimuovere uno strumento decorativo da un elemento'
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
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 20d17ef43f99f6815334c0acbf7eb2040959751e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="45c51-102">Procedura: rimuovere uno strumento decorativo da un elemento</span><span class="sxs-lookup"><span data-stu-id="45c51-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="45c51-103">In questo esempio viene illustrato come rimuovere a livello di codice un adorner specifico da un oggetto specificato <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="45c51-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45c51-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="45c51-104">Example</span></span>  
 <span data-ttu-id="45c51-105">Questo esempio di codice dettagliato rimuove il primo strumento decorativo nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="45c51-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="45c51-106">Questo esempio vengono recuperati gli strumenti decorativi su un <xref:System.Windows.UIElement> denominato *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="45c51-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="45c51-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> senza strumenti decorativi visuali, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="45c51-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="45c51-108">Questo codice verifica la presenza di una matrice null, in modo esplicito ed è più adatto per le applicazioni in una matrice null deve essere abbastanza comune.</span><span class="sxs-lookup"><span data-stu-id="45c51-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="45c51-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="45c51-109">Example</span></span>  
 <span data-ttu-id="45c51-110">In questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="45c51-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="45c51-111">Questo codice non controllano in modo esplicito una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> può essere generata l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="45c51-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="45c51-112">Questo codice è più adatto per le applicazioni in cui in cui è prevista una matrice null rari.</span><span class="sxs-lookup"><span data-stu-id="45c51-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="45c51-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45c51-113">See Also</span></span>  
 [<span data-ttu-id="45c51-114">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="45c51-114">Adorners Overview</span></span>](../../../../docs/framework/wpf/controls/adorners-overview.md)
