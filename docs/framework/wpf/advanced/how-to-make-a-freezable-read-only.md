---
title: 'Procedura: impostare la proprietà di sola lettura per un oggetto Freezable'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Freezable objects [WPF], making read-only
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
ms.openlocfilehash: be3abd74a71fc711cd9f4bf6796b7d55017355ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543432"
---
# <a name="how-to-make-a-freezable-read-only"></a><span data-ttu-id="67d14-102">Procedura: impostare la proprietà di sola lettura per un oggetto Freezable</span><span class="sxs-lookup"><span data-stu-id="67d14-102">How to: Make a Freezable Read-Only</span></span>
<span data-ttu-id="67d14-103">Questo esempio viene illustrato come rendere un <xref:System.Windows.Freezable> sola lettura, chiamare il relativo <xref:System.Windows.Freezable.Freeze%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="67d14-103">This example shows how to make a <xref:System.Windows.Freezable> read-only by calling its <xref:System.Windows.Freezable.Freeze%2A> method.</span></span>  
  
 <span data-ttu-id="67d14-104">Non è possibile bloccare un <xref:System.Windows.Freezable> oggetto se una qualsiasi delle condizioni seguenti è `true` sull'oggetto:</span><span class="sxs-lookup"><span data-stu-id="67d14-104">You cannot freeze a <xref:System.Windows.Freezable> object if any one of the following conditions is `true` about the object:</span></span>  
  
-   <span data-ttu-id="67d14-105">È stata eseguita l'animazione o la proprietà con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="67d14-105">It has animated or data bound properties.</span></span>  
  
-   <span data-ttu-id="67d14-106">Include le proprietà impostate da una risorsa dinamica.</span><span class="sxs-lookup"><span data-stu-id="67d14-106">It has properties that are set by a dynamic resource.</span></span> <span data-ttu-id="67d14-107">Per ulteriori informazioni sulle risorse dinamiche, vedere il [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="67d14-107">For more information about dynamic resources, see the [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
-   <span data-ttu-id="67d14-108">Contiene <xref:System.Windows.Freezable> oggetti secondari che non possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="67d14-108">It contains <xref:System.Windows.Freezable> sub-objects that cannot be frozen.</span></span>  
  
 <span data-ttu-id="67d14-109">Se queste condizioni sono `false` per il <xref:System.Windows.Freezable> oggetto e non si desidera modificarlo, è consigliabile bloccarlo per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="67d14-109">If these conditions are `false` for your <xref:System.Windows.Freezable> object and you do not intend to modify it, consider freezing it to gain performance benefits.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67d14-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="67d14-110">Example</span></span>  
 <span data-ttu-id="67d14-111">Nell'esempio seguente viene bloccato un <xref:System.Windows.Media.SolidColorBrush>, che è un tipo di <xref:System.Windows.Freezable> oggetto.</span><span class="sxs-lookup"><span data-stu-id="67d14-111">The following example freezes a <xref:System.Windows.Media.SolidColorBrush>, which is a type of <xref:System.Windows.Freezable> object.</span></span>  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 <span data-ttu-id="67d14-112">Per ulteriori informazioni su <xref:System.Windows.Freezable> degli oggetti, vedere il [panoramica sugli oggetti Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span><span class="sxs-lookup"><span data-stu-id="67d14-112">For more information about <xref:System.Windows.Freezable> objects, see the [Freezable Objects Overview](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d14-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67d14-113">See Also</span></span>  
 <xref:System.Windows.Freezable>  
 <xref:System.Windows.Freezable.CanFreeze%2A>  
 <xref:System.Windows.Freezable.Freeze%2A>  
 [<span data-ttu-id="67d14-114">Cenni preliminari sugli oggetti Freezable</span><span class="sxs-lookup"><span data-stu-id="67d14-114">Freezable Objects Overview</span></span>](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [<span data-ttu-id="67d14-115">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="67d14-115">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)
