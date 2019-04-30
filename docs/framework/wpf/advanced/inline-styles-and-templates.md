---
title: Stili e modelli inline
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051013"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="ad2c2-102">Stili e modelli inline</span><span class="sxs-lookup"><span data-stu-id="ad2c2-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="ad2c2-103">fornisce <xref:System.Windows.Style> oggetti e oggetti modello (<xref:System.Windows.FrameworkTemplate> sottoclassi) che consente di definire l'aspetto visivo di un elemento nelle risorse, in modo che possono essere usati più volte.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="ad2c2-104">Per questo motivo, gli attributi nel [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] che accettano i tipi <xref:System.Windows.Style> e <xref:System.Windows.FrameworkTemplate> quasi sempre dei riferimenti alle risorse per gli stili esistenti e i modelli anziché definire nuove colonne inline.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="ad2c2-105">Limitazioni dei modelli e stili Inline</span><span class="sxs-lookup"><span data-stu-id="ad2c2-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="ad2c2-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], le proprietà di stile e del modello possono essere impostate tecnicamente in uno dei due modi.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="ad2c2-107">È possibile usare la sintassi degli attributi per fare riferimento a uno stile che è stato definito all'interno di una risorsa, ad esempio `<` *oggetto*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="ad2c2-108">Oppure è possibile usare la sintassi degli elementi per definire uno stile inline, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ad2c2-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="ad2c2-109">`<` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="ad2c2-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="ad2c2-110">`<` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="ad2c2-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="ad2c2-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="ad2c2-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="ad2c2-112">`</` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="ad2c2-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="ad2c2-113">`</` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="ad2c2-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="ad2c2-114">L'utilizzo dell'attributo è molto più comune.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-114">The attribute usage is much more common.</span></span> <span data-ttu-id="ad2c2-115">Uno stile che viene definito inline e non definito nelle risorse necessariamente ha come ambito solo l'elemento che lo contiene e non possa essere utilizzato nuovamente con la stessa facilità perché non contiene alcuna chiave di risorsa.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="ad2c2-116">In genere è più versatile e utile uno stile definito dalla risorsa ed è più in linea generale [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] al principio di separare la logica di programma nel codice di progettazione nel markup del modello di programmazione.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="ad2c2-117">In genere non è necessario impostare uno stile o modello inline, anche se si intende solo utilizzare tale stile o modello in tale percorso.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="ad2c2-118">La maggior parte degli elementi che possono accettare uno stile o modello supportano anche una proprietà di contenuto e un modello di contenuto.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="ad2c2-119">Se si usa solo qualsiasi albero logico creare una sola volta tramite stili o modelli, sarebbe ancora più semplice compilare solo tale proprietà di contenuto con gli elementi figlio equivalente nel markup diretta.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="ad2c2-120">In tal modo del tutto i meccanismi di stili e modelli.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="ad2c2-121">Altri tipi di sintassi abilitate per le estensioni di markup che restituiscono un oggetto sono anche possibili per gli stili e modelli.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="ad2c2-122">Due tali estensioni con gli scenari possibili includono [TemplateBinding](templatebinding-markup-extension.md) e <xref:System.Windows.Data.Binding>.</span><span class="sxs-lookup"><span data-stu-id="ad2c2-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad2c2-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad2c2-123">See also</span></span>

- [<span data-ttu-id="ad2c2-124">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="ad2c2-124">Styling and Templating</span></span>](../controls/styling-and-templating.md)
