---
title: 'Procedura: Registrare una proprietà associata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- attached properties [WPF], registering
- registering attached properties [WPF]
ms.assetid: eb47bd94-0451-4f8d-8fb6-95f7812ac05b
ms.openlocfilehash: 4c678a64b62b8f4db24cf39ffbafac52e56c9982
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768680"
---
# <a name="how-to-register-an-attached-property"></a><span data-ttu-id="172e6-102">Procedura: Registrare una proprietà associata</span><span class="sxs-lookup"><span data-stu-id="172e6-102">How to: Register an Attached Property</span></span>
<span data-ttu-id="172e6-103">Questo esempio mostra come registrare una proprietà associata e fornire funzioni di accesso pubbliche, in modo da poter usare la proprietà sia in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] che nel codice.</span><span class="sxs-lookup"><span data-stu-id="172e6-103">This example shows how to register an attached property and provide public accessors so that you can use the property in both [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] and code.</span></span> <span data-ttu-id="172e6-104">Le proprietà associate rappresentano un concetto della sintassi definito da [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="172e6-104">Attached properties are a syntax concept defined by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="172e6-105">La maggior parte delle proprietà associate per i tipi [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] viene anche implementata come proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="172e6-105">Most attached properties for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] types are also implemented as dependency properties.</span></span> <span data-ttu-id="172e6-106">È possibile usare le proprietà di dipendenza in qualsiasi <xref:System.Windows.DependencyObject> tipi.</span><span class="sxs-lookup"><span data-stu-id="172e6-106">You can use dependency properties on any <xref:System.Windows.DependencyObject> types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="172e6-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="172e6-107">Example</span></span>  
 <span data-ttu-id="172e6-108">Nell'esempio seguente viene illustrato come registrare una proprietà associata come proprietà di dipendenza, usando il <xref:System.Windows.DependencyProperty.RegisterAttached%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="172e6-108">The following example shows how to register an attached property as a dependency property, by using the <xref:System.Windows.DependencyProperty.RegisterAttached%2A> method.</span></span> <span data-ttu-id="172e6-109">La classe del provider può fornire metadati predefiniti per la proprietà applicabile quando la proprietà viene usata in un'altra classe, a meno che tale classe non esegua l'override dei metadati.</span><span class="sxs-lookup"><span data-stu-id="172e6-109">The provider class has the option of providing default metadata for the property that is applicable when the property is used on another class, unless that class overrides the metadata.</span></span> <span data-ttu-id="172e6-110">In questo esempio il valore predefinito della proprietà `IsBubbleSource` viene impostato su `false`.</span><span class="sxs-lookup"><span data-stu-id="172e6-110">In this example, the default value of the `IsBubbleSource` property is set to `false`.</span></span>  
  
 <span data-ttu-id="172e6-111">La classe del provider per una proprietà associata (anche se non è registrata come proprietà di dipendenza) deve fornire funzioni di accesso get e set statiche basate sulla convenzione di denominazione `Set`*[NomeProprietàAssociata]* e `Get`*[NomeProprietàAssociata]*.</span><span class="sxs-lookup"><span data-stu-id="172e6-111">The provider class for an attached property (even if it is not registered as a dependency property) must provide static get and set accessors that follow the naming convention `Set`*[AttachedPropertyName]* and `Get`*[AttachedPropertyName]*.</span></span> <span data-ttu-id="172e6-112">Queste funzioni di accesso sono necessarie per consentire al lettore [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in funzione di riconoscere la proprietà come attributo in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] e risolvere i tipi appropriati.</span><span class="sxs-lookup"><span data-stu-id="172e6-112">These accessors are required so that the acting [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader can recognize the property as an attribute in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] and resolve the appropriate types.</span></span>  
  
 [!code-csharp[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#registerattachedbubbler)]
 [!code-vb[WPFAquariumSln#RegisterAttachedBubbler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#registerattachedbubbler)]  
  
## <a name="see-also"></a><span data-ttu-id="172e6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="172e6-113">See also</span></span>

- <xref:System.Windows.DependencyProperty>
- [<span data-ttu-id="172e6-114">Panoramica sulle proprietà di dipendenza</span><span class="sxs-lookup"><span data-stu-id="172e6-114">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="172e6-115">Proprietà di dipendenza personalizzate</span><span class="sxs-lookup"><span data-stu-id="172e6-115">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="172e6-116">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="172e6-116">How-to Topics</span></span>](properties-how-to-topics.md)
