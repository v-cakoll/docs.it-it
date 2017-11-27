---
title: "Procedura: aggiungere un tipo di proprietario per una proprietà di dipendenza"
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
- classes [WPF], adding as owners of dependency properties
- dependency properties [WPF], adding classes as owners of
ms.assetid: edcce050-0576-4edb-a31a-3f909637b452
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 079f08e1c330b710748ea6bb1aab8ccfb7ae7016
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-owner-type-for-a-dependency-property"></a><span data-ttu-id="10e32-102">Procedura: aggiungere un tipo di proprietario per una proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="10e32-102">How to: Add an Owner Type for a Dependency Property</span></span>
<span data-ttu-id="10e32-103">In questo esempio viene illustrato come aggiungere una classe come proprietario di una proprietà di dipendenza registrato per un tipo diverso.</span><span class="sxs-lookup"><span data-stu-id="10e32-103">This example shows how to add a class as an owner of a dependency property registered for a different type.</span></span> <span data-ttu-id="10e32-104">In questo modo, il [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] lettore e sistema di proprietà sono entrambi in grado di riconoscere la classe come proprietario della proprietà aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="10e32-104">By doing this, the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader and property system are both able to recognize the class as an additional owner of the property.</span></span> <span data-ttu-id="10e32-105">L'aggiunta come proprietario consente alla classe aggiunta fornire i metadati specifici del tipo.</span><span class="sxs-lookup"><span data-stu-id="10e32-105">Adding as owner optionally allows the adding class to provide type-specific metadata.</span></span>  
  
 <span data-ttu-id="10e32-106">Nell'esempio seguente, `StateProperty` è una proprietà registrata per il `MyStateControl` classe.</span><span class="sxs-lookup"><span data-stu-id="10e32-106">In the following example, `StateProperty` is a property registered by the `MyStateControl` class.</span></span> <span data-ttu-id="10e32-107">La classe `UnrelatedStateControl` viene aggiunto come proprietario del `StateProperty` utilizzando il <xref:System.Windows.DependencyProperty.AddOwner%2A> (metodo), in particolare utilizzando la firma che consente di nuovi metadati per la proprietà di dipendenza nello stato attuale per il tipo di aggiunta.</span><span class="sxs-lookup"><span data-stu-id="10e32-107">The class `UnrelatedStateControl` adds itself as an owner of the `StateProperty` using the <xref:System.Windows.DependencyProperty.AddOwner%2A> method, specifically using the signature that allows for new metadata for the dependency property as it exists on the adding type.</span></span> <span data-ttu-id="10e32-108">Si noti che è necessario fornire [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] funzioni di accesso per la proprietà è simile all'esempio illustrato nel [implementare una proprietà di dipendenza](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) esempio, nonché esporre nuovamente l'identificatore della proprietà di dipendenza nella classe da aggiungere come proprietario.</span><span class="sxs-lookup"><span data-stu-id="10e32-108">Notice that you should provide [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] accessors for the property similar to the example shown in the [Implement a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-implement-a-dependency-property.md) example, as well as re-expose the dependency property identifier on the class being added as owner.</span></span>  
  
 <span data-ttu-id="10e32-109">Senza wrapper, la proprietà di dipendenza funzionerà comunque dal punto di vista dell'accesso a livello di programmazione utilizzando <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="10e32-109">Without wrappers, the dependency property would still work from the perspective of programmatic access using <xref:System.Windows.DependencyObject.GetValue%2A> or <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="10e32-110">Ma si desidera in genere parallela di questo comportamento del sistema di proprietà con il [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] wrapper della proprietà.</span><span class="sxs-lookup"><span data-stu-id="10e32-110">But you typically want to parallel this property-system behavior with the [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] property wrappers.</span></span> <span data-ttu-id="10e32-111">I wrapper rendono più semplice impostare la proprietà di dipendenza a livello di codice e consentono di impostare le proprietà come [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributi.</span><span class="sxs-lookup"><span data-stu-id="10e32-111">The wrappers make it easier to set the dependency property programmatically, and make it possible to set the properties as [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] attributes.</span></span>  
  
 <span data-ttu-id="10e32-112">Per informazioni su come eseguire l'override dei metadati predefiniti, vedere [eseguire l'Override dei metadati per una proprietà di dipendenza](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span><span class="sxs-lookup"><span data-stu-id="10e32-112">To find out how to override default metadata, see [Override Metadata for a Dependency Property](../../../../docs/framework/wpf/advanced/how-to-override-metadata-for-a-dependency-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10e32-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="10e32-113">Example</span></span>  
 [!code-csharp[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#mystatecontrol)]
 [!code-vb[PropertySystemEsoterics#MyStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#mystatecontrol)]  
[!code-csharp[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertySystemEsoterics/CSharp/SDKSampleLibrary/class1.cs#unrelatedstatecontrol)]
[!code-vb[PropertySystemEsoterics#UnrelatedStateControl](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertySystemEsoterics/visualbasic/sdksamplelibrary/class1.vb#unrelatedstatecontrol)]  
  
## <a name="see-also"></a><span data-ttu-id="10e32-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10e32-114">See Also</span></span>  
 [<span data-ttu-id="10e32-115">Proprietà di dipendenza personalizzate</span><span class="sxs-lookup"><span data-stu-id="10e32-115">Custom Dependency Properties</span></span>](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [<span data-ttu-id="10e32-116">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="10e32-116">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)
