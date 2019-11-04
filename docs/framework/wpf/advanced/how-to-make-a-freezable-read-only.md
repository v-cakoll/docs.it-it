---
title: 'Procedura: impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: 4185966d864be425bc631953461f6f27ab983bee
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460066"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="10ba4-102">Procedura: impostare la proprietà di sola lettura per un oggetto Freezable</span><span class="sxs-lookup"><span data-stu-id="10ba4-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="10ba4-103">In questo esempio viene illustrato come creare un <xref:System.Windows.Freezable> di sola lettura chiamando il relativo metodo <xref:System.Windows.Freezable.Freeze%2A>.</span><span class="sxs-lookup"><span data-stu-id="10ba4-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="10ba4-104">Non è possibile bloccare un oggetto <xref:System.Windows.Freezable> se una delle condizioni seguenti è `true` sull'oggetto:</span><span class="sxs-lookup"><span data-stu-id="10ba4-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
- <span data-ttu-id="10ba4-105">Dispone di proprietà animate o con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="10ba4-105">It has animated or data bound properties.</span></span>  
  
- <span data-ttu-id="10ba4-106">Dispone di proprietà impostate da una risorsa dinamica.</span><span class="sxs-lookup"><span data-stu-id="10ba4-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="10ba4-107">Per ulteriori informazioni sulle risorse dinamiche, vedere le [risorse XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="10ba4-107">For more information about dynamic resources, see the [XAML Resources](../../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
- <span data-ttu-id="10ba4-108">Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="10ba4-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="10ba4-109">Se queste condizioni vengono `false` per l'oggetto <xref:System.Windows.Freezable> e non si intende modificarle, provare a bloccarlo per ottenere vantaggi in termini di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="10ba4-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10ba4-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="10ba4-110">Example</span></span>  
 <span data-ttu-id="10ba4-111">Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.</span><span class="sxs-lookup"><span data-stu-id="10ba4-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="10ba4-112">Per ulteriori informazioni sugli oggetti <xref:System.Windows.Freezable>, vedere [Cenni preliminari sugli oggetti Freezable](freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="10ba4-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ba4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10ba4-113">See also</span></span>

- <xref:System.Windows.Freezable>
- <xref:System.Windows.Freezable.CanFreeze%2A>
- <xref:System.Windows.Freezable.Freeze%2A>
- [<span data-ttu-id="10ba4-114">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="10ba4-114">Freezable Objects Overview</span></span>](freezable-objects-overview.md)
- [<span data-ttu-id="10ba4-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="10ba4-115">How-to Topics</span></span>](base-elements-how-to-topics.md)
