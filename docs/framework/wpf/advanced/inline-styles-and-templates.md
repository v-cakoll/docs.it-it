---
title: Stili e modelli inline
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dccf0b274121ff4fe88c9270119a2f631ffcf29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="31b71-102">Stili e modelli inline</span><span class="sxs-lookup"><span data-stu-id="31b71-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="31b71-103">fornisce <xref:System.Windows.Style> oggetti e oggetti modello (<xref:System.Windows.FrameworkTemplate> sottoclassi) come un modo per definire l'aspetto visivo di un elemento nelle risorse, in modo che possono essere utilizzati più volte.</span><span class="sxs-lookup"><span data-stu-id="31b71-103"> provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="31b71-104">Per questo motivo, gli attributi [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che accettano i tipi <xref:System.Windows.Style> e <xref:System.Windows.FrameworkTemplate> quasi sempre dei riferimenti alle risorse per gli stili e modelli anziché definirne di nuovi inline.</span><span class="sxs-lookup"><span data-stu-id="31b71-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="31b71-105">Limitazioni dei modelli e stili in linea</span><span class="sxs-lookup"><span data-stu-id="31b71-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="31b71-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], proprietà di stile e modello possono essere impostate tecnicamente in uno dei due modi.</span><span class="sxs-lookup"><span data-stu-id="31b71-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="31b71-107">È possibile utilizzare la sintassi degli attributi per fare riferimento a uno stile definito all'interno di una risorsa, ad esempio `<` *oggetto*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="31b71-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="31b71-108">In alternativa, è possibile utilizzare la sintassi degli elementi di proprietà per definire uno stile inline, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="31b71-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="31b71-109">`<`*oggetto*`>`</span><span class="sxs-lookup"><span data-stu-id="31b71-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="31b71-110">`<`*oggetto*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="31b71-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="31b71-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="31b71-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="31b71-112">`</`*oggetto*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="31b71-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="31b71-113">`</`*oggetto*`>`</span><span class="sxs-lookup"><span data-stu-id="31b71-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="31b71-114">L'utilizzo dell'attributo è molto più comune.</span><span class="sxs-lookup"><span data-stu-id="31b71-114">The attribute usage is much more common.</span></span> <span data-ttu-id="31b71-115">Uno stile che è definita in linea e non definito nelle risorse è necessariamente limitato solo all'elemento contenitore e non possa essere utilizzato nuovamente con la stessa facilità poiché non dispone di alcuna chiave di risorsa.</span><span class="sxs-lookup"><span data-stu-id="31b71-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="31b71-116">In generale è più versatile e utile uno stile definito dalla risorsa ed è più conforme al [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] principio di modello di separazione logica di programma nel codice dalla progettazione nel markup di programmazione.</span><span class="sxs-lookup"><span data-stu-id="31b71-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="31b71-117">In genere non è necessario impostare uno stile o un modello inline, anche se si intende solo utilizzare tale stile o modello in tale percorso.</span><span class="sxs-lookup"><span data-stu-id="31b71-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="31b71-118">La maggior parte degli elementi che può richiedere uno stile o modello supportano inoltre una proprietà di contenuto e un modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="31b71-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="31b71-119">Se si usa solo l'albero logico creare una sola volta tramite stili o modelli, sarebbe ancora più semplice compilare solo tale proprietà di contenuto con gli elementi figlio equivalente nel markup diretto.</span><span class="sxs-lookup"><span data-stu-id="31b71-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="31b71-120">In tal modo del tutto i meccanismi di stili e modelli.</span><span class="sxs-lookup"><span data-stu-id="31b71-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="31b71-121">Altri tipi di sintassi abilitate per le estensioni di markup che restituiscono un oggetto sono inoltre disponibili per gli stili e modelli.</span><span class="sxs-lookup"><span data-stu-id="31b71-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="31b71-122">Due queste estensioni che dispongono di scenari possibili includono [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) e <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="31b71-122">Two such extensions that have possible scenarios include [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31b71-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="31b71-123">See Also</span></span>  
 [<span data-ttu-id="31b71-124">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="31b71-124">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
