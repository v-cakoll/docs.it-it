---
title: 'Procedura: Impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: e0cc5d73f9b9f15fc02bf20a70c84da1a7c535c9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671668"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="7ce8b-102">Procedura: Impostare la proprietà di sola lettura per un oggetto Freezable</span><span class="sxs-lookup"><span data-stu-id="7ce8b-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="7ce8b-103">In questo esempio viene illustrato come effettuare una <xref:System.Windows.Freezable> sola lettura chiamando relativo <xref:System.Windows.Freezable.Freeze%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="7ce8b-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="7ce8b-104">Non è possibile bloccare una <xref:System.Windows.Freezable> dell'oggetto se una delle condizioni seguenti è `true` sull'oggetto:</span><span class="sxs-lookup"><span data-stu-id="7ce8b-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="7ce8b-105">È stata eseguita l'animazione o le proprietà con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="7ce8b-106">Include proprietà impostate da una risorsa dinamica.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="7ce8b-107">Per altre informazioni sulle risorse dinamiche, vedere la [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="7ce8b-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="7ce8b-108">Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="7ce8b-109">Se si verificano queste condizioni `false` per il <xref:System.Windows.Freezable> oggetto e non si intende modificarlo, prendere in considerazione il blocco in modo da migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ce8b-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="7ce8b-110">Example</span></span>  
 <span data-ttu-id="7ce8b-111">Nell'esempio seguente si blocca una <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.</span><span class="sxs-lookup"><span data-stu-id="7ce8b-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="7ce8b-112">Per altre informazioni sulle <xref:System.Windows.Freezable> oggetti, vedere la [Cenni preliminari sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7ce8b-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce8b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ce8b-113">See also</span></span>
- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="7ce8b-114">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="7ce8b-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)
- [<span data-ttu-id="7ce8b-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="7ce8b-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
