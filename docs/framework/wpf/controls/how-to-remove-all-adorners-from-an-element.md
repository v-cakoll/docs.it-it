---
title: 'Procedura: Rimuovere tutti gli strumenti decorativi da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: fe5303a3-b76e-4643-aafb-51419032b47b
ms.openlocfilehash: 8504bb1ec70de188033b2b092bbb66cf9da3dc11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770773"
---
# <a name="how-to-remove-all-adorners-from-an-element"></a><span data-ttu-id="86dd7-102">Procedura: Rimuovere tutti gli strumenti decorativi da un elemento</span><span class="sxs-lookup"><span data-stu-id="86dd7-102">How to: Remove all Adorners from an Element</span></span>
<span data-ttu-id="86dd7-103">Questo esempio viene illustrato come rimuovere tutti gli strumenti decorativi da un oggetto specificato a livello <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="86dd7-103">This example shows how to programmatically remove all adorners from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86dd7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="86dd7-104">Example</span></span>  
 <span data-ttu-id="86dd7-105">In questo esempio di codice piuttosto prolisso rimuove tutti gli strumenti decorativi nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="86dd7-105">This verbose code example removes all of the adorners in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="86dd7-106">Questo esempio vengono recuperati gli strumenti decorativi in una <xref:System.Windows.UIElement> denominate *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="86dd7-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="86dd7-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di alcun gli strumenti decorativi, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="86dd7-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="86dd7-108">Questo codice verifica la presenza di una matrice null in modo esplicito ed è ideale per le applicazioni in una matrice null deve essere abbastanza comune.</span><span class="sxs-lookup"><span data-stu-id="86dd7-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornerslong)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornerslong)]  
  
## <a name="example"></a><span data-ttu-id="86dd7-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="86dd7-109">Example</span></span>  
 <span data-ttu-id="86dd7-110">Questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="86dd7-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="86dd7-111">Questo codice non verificano in modo esplicito per una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> eccezione potrebbe essere generata.</span><span class="sxs-lookup"><span data-stu-id="86dd7-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="86dd7-112">Questo codice è ideale per le applicazioni in cui è prevista una matrice null sono rare.</span><span class="sxs-lookup"><span data-stu-id="86dd7-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removealladornersshort)]
 [!code-vb[AdornersMiscCode#_RemoveAllAdornersShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removealladornersshort)]  
  
## <a name="see-also"></a><span data-ttu-id="86dd7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86dd7-113">See also</span></span>

- [<span data-ttu-id="86dd7-114">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="86dd7-114">Adorners Overview</span></span>](adorners-overview.md)
