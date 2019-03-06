---
title: 'Procedura: Rimuovere uno strumento decorativo da un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adorners [WPF], removing
ms.assetid: 97cf4d9f-0596-429e-8526-32a30aa4ae99
ms.openlocfilehash: 0c74fe9ed1e7190ce4ff26a7dbae1413f950ba7e
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374076"
---
# <a name="how-to-remove-an-adorner-from-an-element"></a><span data-ttu-id="4dbe0-102">Procedura: Rimuovere uno strumento decorativo da un elemento</span><span class="sxs-lookup"><span data-stu-id="4dbe0-102">How to: Remove an Adorner from an Element</span></span>
<span data-ttu-id="4dbe0-103">In questo esempio viene illustrato come rimuovere a livello di codice un adorner specifico da un oggetto specificato <xref:System.Windows.UIElement>.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-103">This example shows how to programmatically remove a specific adorner from a specified <xref:System.Windows.UIElement>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dbe0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="4dbe0-104">Example</span></span>  
 <span data-ttu-id="4dbe0-105">In questo esempio di codice piuttosto prolisso rimuove il primo strumento decorativo nella matrice di Adorner restituito da <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-105">This verbose code example removes the first adorner in the array of adorners returned by <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A>.</span></span>  <span data-ttu-id="4dbe0-106">Questo esempio vengono recuperati gli strumenti decorativi in una <xref:System.Windows.UIElement> denominate *myTextBox*.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-106">This example happens to retrieve the adorners on a <xref:System.Windows.UIElement> named *myTextBox*.</span></span>  <span data-ttu-id="4dbe0-107">Se l'elemento specificato nella chiamata a <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> non dispone di alcun gli strumenti decorativi, `null` viene restituito.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-107">If the element specified in the call to <xref:System.Windows.Documents.AdornerLayer.GetAdorners%2A> has no adorners, `null` is returned.</span></span>  <span data-ttu-id="4dbe0-108">Questo codice verifica la presenza di una matrice null in modo esplicito ed è ideale per le applicazioni in una matrice null deve essere abbastanza comune.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-108">This code explicitly checks for a null array, and is best suited for applications where a null array is expected to be relatively common.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornerlong)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerLong](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornerlong)]  
  
## <a name="example"></a><span data-ttu-id="4dbe0-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="4dbe0-109">Example</span></span>  
 <span data-ttu-id="4dbe0-110">Questo esempio di codice ridotto è funzionalmente equivalente all'esempio dettagliato illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-110">This condensed code example is functionally equivalent to the verbose example shown above.</span></span> <span data-ttu-id="4dbe0-111">Questo codice non verificano in modo esplicito per una matrice null, pertanto è possibile che un <xref:System.NullReferenceException> eccezione potrebbe essere generata.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-111">This code does not explicitly check for a null array, so it is possible that a <xref:System.NullReferenceException> exception may be raised.</span></span>  <span data-ttu-id="4dbe0-112">Questo codice è ideale per le applicazioni in cui è prevista una matrice null sono rare.</span><span class="sxs-lookup"><span data-stu-id="4dbe0-112">This code is best suited for applications where a null array is expected to be rare.</span></span>  
  
 [!code-csharp[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornersMiscCode/CSharp/Window1.xaml.cs#_removespecificadornershort)]
 [!code-vb[AdornersMiscCode#_RemoveSpecificAdornerShort](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornersMiscCode/visualbasic/window1.xaml.vb#_removespecificadornershort)]  
  
## <a name="see-also"></a><span data-ttu-id="4dbe0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4dbe0-113">See also</span></span>
- [<span data-ttu-id="4dbe0-114">Panoramica sugli strumenti decorativi</span><span class="sxs-lookup"><span data-stu-id="4dbe0-114">Adorners Overview</span></span>](adorners-overview.md)
