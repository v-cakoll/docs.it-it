---
title: Estensione del markup x:Null
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: 7dbea2c7d4010d8defc572dbdc14a0dfd6d7601e
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484713"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="44e42-102">Estensione del markup x:Null</span><span class="sxs-lookup"><span data-stu-id="44e42-102">x:Null Markup Extension</span></span>
<span data-ttu-id="44e42-103">Specifica `null` come valore per un membro XAML.</span><span class="sxs-lookup"><span data-stu-id="44e42-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="44e42-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="44e42-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="44e42-105">Note</span><span class="sxs-lookup"><span data-stu-id="44e42-105">Remarks</span></span>  
 <span data-ttu-id="44e42-106">La parola chiave per un riferimento null C# in C++ e è null.</span><span class="sxs-lookup"><span data-stu-id="44e42-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="44e42-107">La parola chiave Microsoft Visual Basic per un riferimento null `Nothing`è, ma si usa `{x:Null}` sempre come utilizzo XAML indipendentemente dal linguaggio code-behind associato a XAML.</span><span class="sxs-lookup"><span data-stu-id="44e42-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="44e42-108">L' `x:Null` estensione di markup non dispone di proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="44e42-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="44e42-109">Un utilizzo null è spesso associato all'esposizione del membro XAML di un valore <xref:System.Nullable%601> CLR.</span><span class="sxs-lookup"><span data-stu-id="44e42-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="44e42-110">L' `x:Null` estensione di markup, come tutte le estensioni di markup XAML, USA le`{,}`parentesi graffe () per l'escape della gestione dei valori di attributo in modo che non siano valori letterali o riferimenti al gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="44e42-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="44e42-111">La sintassi degli attributi è la sintassi utilizzata più di frequente con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="44e42-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="44e42-112">Una sintassi `<x:Null />` dell'elemento oggetto è tecnicamente possibile, ma viene usata raramente perché `x:Null` l'estensione di markup non contiene parametri posizionali o argomenti di costruzione.</span><span class="sxs-lookup"><span data-stu-id="44e42-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="44e42-113">Per informazioni sulle estensioni di markup, vedere [estensioni di markup e XAML WPF](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="44e42-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="44e42-114">In .NET Framework servizi XAML, la gestione di questa estensione di markup viene definita dalla <xref:System.Windows.Markup.NullExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="44e42-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="44e42-115">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="44e42-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="44e42-116">Si noti `null` che non è necessariamente il valore iniziale non impostato per una proprietà di dipendenza di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="44e42-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="44e42-117">Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato su metadati specifici della proprietà.</span><span class="sxs-lookup"><span data-stu-id="44e42-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="44e42-118">Molte proprietà di dipendenza non accettano `null` come valore, tramite markup o codice a causa delle implementazioni di callback di convalida.</span><span class="sxs-lookup"><span data-stu-id="44e42-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="44e42-119">Per ulteriori informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari sulle proprietà di dipendenza](../wpf/advanced/dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="44e42-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e42-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="44e42-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="44e42-121">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="44e42-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="44e42-122">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="44e42-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
