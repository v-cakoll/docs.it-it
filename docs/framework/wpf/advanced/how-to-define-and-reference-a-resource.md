---
title: 'Procedura: definire e fare riferimento a una risorsa'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 322ac3e5ebfe2d820a4711d877396b9a1a2759a6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-and-reference-a-resource"></a><span data-ttu-id="462c5-102">Procedura: definire e fare riferimento a una risorsa</span><span class="sxs-lookup"><span data-stu-id="462c5-102">How to: Define and Reference a Resource</span></span>
<span data-ttu-id="462c5-103">In questo esempio viene illustrato come definire una risorsa e di farvi riferimento tramite un attributo in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="462c5-103">This example shows how to define a resource and reference it by using an attribute in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="462c5-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="462c5-104">Example</span></span>  
 <span data-ttu-id="462c5-105">L'esempio seguente definisce due tipi di risorse: un <xref:System.Windows.Media.SolidColorBrush> risorse e numerosi <xref:System.Windows.Style> risorse.</span><span class="sxs-lookup"><span data-stu-id="462c5-105">The following example defines two types of resources: a <xref:System.Windows.Media.SolidColorBrush> resource, and several <xref:System.Windows.Style> resources.</span></span> <span data-ttu-id="462c5-106">Il <xref:System.Windows.Media.SolidColorBrush> risorse `MyBrush` viene utilizzata per fornire il valore di diverse proprietà che accettano un <xref:System.Windows.Media.Brush> tipo valore.</span><span class="sxs-lookup"><span data-stu-id="462c5-106">The <xref:System.Windows.Media.SolidColorBrush> resource `MyBrush` is used to provide the value of several properties that each take a <xref:System.Windows.Media.Brush> type value.</span></span> <span data-ttu-id="462c5-107">Il <xref:System.Windows.Style> risorse `PageBackground`, `TitleText` e `Label` ogni destinazione di un particolare tipo di controllo.</span><span class="sxs-lookup"><span data-stu-id="462c5-107">The <xref:System.Windows.Style> resources `PageBackground`, `TitleText` and `Label` each target a particular control type.</span></span> <span data-ttu-id="462c5-108">Gli stili di impostano numerose proprietà sui controlli di destinazione, per tale risorsa di stile fa riferimento una chiave di risorsa, viene utilizzato per impostare il <xref:System.Windows.FrameworkElement.Style%2A> proprietà dei diversi elementi di controllo specifico, definito in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="462c5-108">The styles set a variety of different properties on the targeted controls, when that style resource is referenced by resource key and is used to set the <xref:System.Windows.FrameworkElement.Style%2A> property of several specific control elements defined in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].</span></span>  
  
 <span data-ttu-id="462c5-109">Si noti che una delle proprietà all'interno dei metodi di impostazione del `Label` stile fa riferimento anche il `MyBrush` risorsa definita in precedenza.</span><span class="sxs-lookup"><span data-stu-id="462c5-109">Note that one of the properties within the setters of the `Label` style also references the `MyBrush` resource defined earlier.</span></span> <span data-ttu-id="462c5-110">Questa è una tecnica comune, ma è importante ricordare che le risorse vengono analizzate e immessi in un dizionario risorse nell'ordine in cui vengono loro assegnati.</span><span class="sxs-lookup"><span data-stu-id="462c5-110">This is a common technique, but it is important to remember that resources are parsed and entered into a resource dictionary in the order that they are given.</span></span> <span data-ttu-id="462c5-111">Le risorse sono richieste anche l'ordine trovato nel dizionario, se si utilizza il [estensione di Markup StaticResource](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) per fare riferimento a esse all'interno di un'altra risorsa.</span><span class="sxs-lookup"><span data-stu-id="462c5-111">Resources are also requested by the order found within the dictionary if you use the [StaticResource Markup Extension](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md) to reference them from within another resource.</span></span> <span data-ttu-id="462c5-112">Assicurarsi che tutte le risorse a cui si fa riferimento sono definita in precedenza all'interno della raccolta di risorse rispetto a quella in cui è richiesta la risorsa.</span><span class="sxs-lookup"><span data-stu-id="462c5-112">Make sure that any resource that you reference is defined earlier within the resources collection than where that resource is then requested.</span></span> <span data-ttu-id="462c5-113">Se necessario, è possibile risolvere il rigido ordine di creazione di riferimenti a risorse tramite un [estensione di Markup DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) per fare riferimento alla risorsa in fase di esecuzione, ma occorre tenere presente che questa DynamicResource tecnica incide sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="462c5-113">If necessary, you can work around the strict creation order of resource refererences by using a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) to reference the resource at runtime instead, but you should be aware that this DynamicResource technique has performance consequences.</span></span> <span data-ttu-id="462c5-114">Per informazioni dettagliate, vedere [risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="462c5-114">For details, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a><span data-ttu-id="462c5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="462c5-115">See Also</span></span>  
 [<span data-ttu-id="462c5-116">Risorse XAML</span><span class="sxs-lookup"><span data-stu-id="462c5-116">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="462c5-117">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="462c5-117">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
