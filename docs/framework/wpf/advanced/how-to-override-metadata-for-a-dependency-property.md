---
title: "Procedura: Eseguire l'override dei metadati per una proprietà di dipendenza"
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
helpviewer_keywords:
- metadata [WPF], overriding for dependency properties
- dependency properties [WPF], overriding metadata for
- overriding metadata for dependency properties [WPF]
ms.assetid: f90f026e-60d8-428a-933d-edf0dba4441f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e7cb01c81b5fb24830cbe0cc39befbadaf4405e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-metadata-for-a-dependency-property"></a><span data-ttu-id="cd754-102">Procedura: Eseguire l'override dei metadati per una proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="cd754-102">How to: Override Metadata for a Dependency Property</span></span>
<span data-ttu-id="cd754-103">Questo esempio viene illustrato come eseguire l'override di metadati di proprietà di dipendenza predefinito provengono da una classe ereditata, chiamando il <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> (metodo) e fornendo i metadati specifici del tipo.</span><span class="sxs-lookup"><span data-stu-id="cd754-103">This example shows how to override default dependency property metadata that comes from an inherited class, by calling the <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> method and providing type-specific metadata.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd754-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="cd754-104">Example</span></span>  
 <span data-ttu-id="cd754-105">Definendo il <xref:System.Windows.PropertyMetadata>, una classe possa definire i comportamenti della proprietà di dipendenza, ad esempio il callback predefinito valore e proprietà del sistema.</span><span class="sxs-lookup"><span data-stu-id="cd754-105">By defining its <xref:System.Windows.PropertyMetadata>, a class can define the dependency property's behaviors, such as its default value and property system callbacks.</span></span> <span data-ttu-id="cd754-106">Molte classi della proprietà di dipendenza dispongono già di metadati predefiniti stabiliti nell'ambito del processo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="cd754-106">Many dependency property classes already have default metadata established as part of their registration process.</span></span> <span data-ttu-id="cd754-107">Sono incluse le proprietà di dipendenza che fanno parte delle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cd754-107">This includes the dependency properties that are part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)].</span></span> <span data-ttu-id="cd754-108">Una classe che eredita la proprietà di dipendenza tramite l'ereditarietà di classe può eseguire l'override dei metadati originali in modo che le caratteristiche della proprietà che è possibile modificare tramite i metadati soddisfino qualsiasi requisito specifico della sottoclasse.</span><span class="sxs-lookup"><span data-stu-id="cd754-108">A class that inherits the dependency property through its class inheritance can override the original metadata so that the characteristics of the property that can be altered through metadata will match any subclass-specific requirements.</span></span>  
  
 <span data-ttu-id="cd754-109">L'override dei metadati di una proprietà di dipendenza deve essere eseguito prima che la proprietà venga resa utilizzabile dal sistema di proprietà, vale a dire nel momento in cui vengono create istanze specifiche degli oggetti che registrano la proprietà.</span><span class="sxs-lookup"><span data-stu-id="cd754-109">Overriding metadata on a dependency property must be done prior to that property being placed in use by the property system (this equates to the time that specific instances of objects that register the property are instantiated).</span></span> <span data-ttu-id="cd754-110">Le chiamate a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> deve essere eseguita all'interno dei costruttori statici del tipo che fornisce se stesso come il `forType` parametro di <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="cd754-110">Calls to <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> must be performed within the static constructors of the type that provides itself as the `forType` parameter of <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.</span></span> <span data-ttu-id="cd754-111">Il tentativo di modificare i metadati dopo la creazione delle istanze del tipo di proprietario non genererà eccezioni, ma darà come risultato comportamenti incoerenti nel sistema di proprietà.</span><span class="sxs-lookup"><span data-stu-id="cd754-111">If you attempt to change metadata once instances of the owner type exist, this will not raise exceptions, but will result in inconsistent behaviors in the property system.</span></span> <span data-ttu-id="cd754-112">Inoltre, l'override dei metadati può essere eseguito solo una volta per tipo.</span><span class="sxs-lookup"><span data-stu-id="cd754-112">Also, metadata can only be overridden once per type.</span></span> <span data-ttu-id="cd754-113">I tentativi successivi di eseguire l'override dei metadati sullo stesso tipo genereranno un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="cd754-113">Subsequent attempts to override metadata on the same type will raise an exception.</span></span>  
  
 <span data-ttu-id="cd754-114">Nell'esempio seguente la classe personalizzata `MyAdvancedStateControl` esegue l'override dei metadati forniti per `StateProperty` da `MyAdvancedStateControl` con i nuovi metadati delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="cd754-114">In the following example, the custom class `MyAdvancedStateControl` overrides the metadata provided for `StateProperty` by `MyAdvancedStateControl` with new property metadata.</span></span> <span data-ttu-id="cd754-115">Ad esempio, il valore predefinito di `StateProperty` sarà `true` quando viene eseguita una query sulla proprietà in un'istanza `MyAdvancedStateControl` appena creata.</span><span class="sxs-lookup"><span data-stu-id="cd754-115">For instance, the default value of the `StateProperty` is now `true` when the property is queried on a newly constructed `MyAdvancedStateControl` instance.</span></span>  
  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#myadvancedstatecontrol)]
[!code-vb[PropertySystemEsoterics#MyAdvancedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#myadvancedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="cd754-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cd754-116">See Also</span></span>  
 <xref:System.Windows.DependencyProperty>  
 [<span data-ttu-id="cd754-117">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="cd754-117">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [<span data-ttu-id="cd754-118">Proprietà di dipendenza personalizzate</span><span class="sxs-lookup"><span data-stu-id="cd754-118">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="cd754-119">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="cd754-119">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/properties-how-to-topics.md)
