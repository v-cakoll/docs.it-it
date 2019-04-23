---
title: 'Procedura: Rimuovere uno strumento decorativo da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 256dd6fa0117f88aec2ef6b60c6dcd4c33b57855
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59212401"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="9af59-102">Procedura: Rimuovere uno strumento decorativo da un elemento</span><span class="sxs-lookup"><span data-stu-id="9af59-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="9af59-103">In questo esempio viene illustrato come rimuovere a livello di codice un adorner specifico da un oggetto specificato <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="9af59-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9af59-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9af59-104">Example</span></span>  
 <span data-ttu-id="9af59-105">In questo esempio di codice piuttosto prolisso rimuove il primo strumento decorativo nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="9af59-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="9af59-106">Questo esempio vengono recuperati gli strumenti decorativi in una <xref:System.Windows.UIElement> denominate *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="9af59-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="9af59-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di alcun gli strumenti decorativi, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="9af59-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="9af59-108">Questo codice verifica la presenza di una matrice null in modo esplicito ed è ideale per le applicazioni in una matrice null deve essere abbastanza comune.</span><span class="sxs-lookup"><span data-stu-id="9af59-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="9af59-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="9af59-109">Example</span></span>  
 <span data-ttu-id="9af59-110">Questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="9af59-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="9af59-111">Questo codice non verificano in modo esplicito per una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> eccezione potrebbe essere generata.</span><span class="sxs-lookup"><span data-stu-id="9af59-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="9af59-112">Questo codice è ideale per le applicazioni in cui è prevista una matrice null sono rare.</span><span class="sxs-lookup"><span data-stu-id="9af59-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="9af59-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9af59-113">See also</span></span>

- [<span data-ttu-id="9af59-114">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="9af59-114">Adorners Overview</span></span>](adorners-overview.md)
