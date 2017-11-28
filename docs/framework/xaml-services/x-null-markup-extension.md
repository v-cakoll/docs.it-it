---
title: Estensione del markup x:Null
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- Null
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: a60d74bdf3343d02eaf912ac7700f36a649f659c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="cb21e-102">Estensione del markup x:Null</span><span class="sxs-lookup"><span data-stu-id="cb21e-102">x:Null Markup Extension</span></span>
<span data-ttu-id="cb21e-103">Specifica `null` come valore per un membro XAML.</span><span class="sxs-lookup"><span data-stu-id="cb21e-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="cb21e-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="cb21e-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="cb21e-105">Note</span><span class="sxs-lookup"><span data-stu-id="cb21e-105">Remarks</span></span>  
 <span data-ttu-id="cb21e-106">La parola chiave per un riferimento null in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] e [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] è null.</span><span class="sxs-lookup"><span data-stu-id="cb21e-106">The keyword for a null reference in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="cb21e-107">Il [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] è la parola chiave per un riferimento null `Nothing`, ma si utilizza sempre `{x:Null}` come l'utilizzo XAML indipendentemente dal linguaggio di codice è possibile associare il codice XAML.</span><span class="sxs-lookup"><span data-stu-id="cb21e-107">The [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="cb21e-108">Il `x:Null` estensione di markup non contiene proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="cb21e-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="cb21e-109">Un utilizzo null spesso è associato l'esposizione del membro XAML di un tipo CLR <xref:System.Nullable%601> valore.</span><span class="sxs-lookup"><span data-stu-id="cb21e-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="cb21e-110">Il `x:Null` estensione di markup, ad esempio tutte le estensioni di markup XAML, utilizza le parentesi graffe (`{,}`) per eseguire l'escape la gestione dei valori di attributo affinché siano diversi da valori letterali o riferimenti del gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="cb21e-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="cb21e-111">Sintassi dell'attributo è in genere utilizzati con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="cb21e-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="cb21e-112">La sintassi degli elementi oggetto `<x:Null />` è tecnicamente possibile, ma viene usato raramente perché il `x:Null` estensione di markup non dispone di parametri posizionali o gli argomenti di costruzione.</span><span class="sxs-lookup"><span data-stu-id="cb21e-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="cb21e-113">Per informazioni sulle estensioni di markup, vedere [le estensioni di Markup e XAML WPF](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="cb21e-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="cb21e-114">Nei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.NullExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="cb21e-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="cb21e-115">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="cb21e-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="cb21e-116">Si noti che `null` non è necessariamente il valore iniziale non impostato per una proprietà di dipendenza di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="cb21e-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="cb21e-117">Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato sui metadati specifici della proprietà.</span><span class="sxs-lookup"><span data-stu-id="cb21e-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="cb21e-118">Molte proprietà di dipendenza non accettano `null` come valore, tramite markup o codice a causa delle implementazioni dei callback di convalida.</span><span class="sxs-lookup"><span data-stu-id="cb21e-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="cb21e-119">Per ulteriori informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cb21e-119">For more information about dependency properties, see [Dependency Properties Overview](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb21e-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb21e-120">See Also</span></span>  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [<span data-ttu-id="cb21e-121">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="cb21e-121">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="cb21e-122">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="cb21e-122">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
