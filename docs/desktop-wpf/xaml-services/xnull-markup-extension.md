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
ms.openlocfilehash: b83e893f951c15eca69fbb6b002369dd723ca469
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071430"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="63ac3-102">Estensione del markup x:Null</span><span class="sxs-lookup"><span data-stu-id="63ac3-102">x:Null Markup Extension</span></span>

<span data-ttu-id="63ac3-103">Specifica `null` come valore per un membro XAML.</span><span class="sxs-lookup"><span data-stu-id="63ac3-103">Specifies `null` as a value for a XAML member.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="63ac3-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="63ac3-104">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Null}" .../>
```

## <a name="remarks"></a><span data-ttu-id="63ac3-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="63ac3-105">Remarks</span></span>

<span data-ttu-id="63ac3-106">La parola chiave per un riferimento null è null.</span><span class="sxs-lookup"><span data-stu-id="63ac3-106">The keyword for a null reference in C# and C++ is null.</span></span> <span data-ttu-id="63ac3-107">La parola chiave di Microsoft `Nothing`Visual Basic per `{x:Null}` un riferimento null è , ma viene sempre utilizzata come utilizzo XAML indipendentemente dal linguaggio code-behind associato al codice XAML.</span><span class="sxs-lookup"><span data-stu-id="63ac3-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>

<span data-ttu-id="63ac3-108">L'estensione `x:Null` di markup non ha proprietà impostabili.</span><span class="sxs-lookup"><span data-stu-id="63ac3-108">The `x:Null` markup extension has no settable properties.</span></span>

<span data-ttu-id="63ac3-109">Un utilizzo null è spesso associato all'esposizione dei membri XAML di un valore CLR. <xref:System.Nullable%601></span><span class="sxs-lookup"><span data-stu-id="63ac3-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>

<span data-ttu-id="63ac3-110">L'estensione `x:Null` di markup, come tutte le`{,}`estensioni di markup XAML, usa le parentesi graffe ( ) per eseguire l'ecattività della gestione dei valori di attributo in modo che siano diversi dai valori letterali o dai riferimenti ai gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="63ac3-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="63ac3-111">La sintassi degli attributi è la sintassi utilizzata più di frequente con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="63ac3-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="63ac3-112">La sintassi `<x:Null />` di un elemento oggetto è `x:Null` tecnicamente possibile, ma viene raramente utilizzata perché l'estensione di markup non ha parametri posizionali o argomenti di costruzione.</span><span class="sxs-lookup"><span data-stu-id="63ac3-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>

<span data-ttu-id="63ac3-113">Per informazioni sulle estensioni di markup, vedere [Estensioni di markup e XAML WPF.](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)</span><span class="sxs-lookup"><span data-stu-id="63ac3-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>

<span data-ttu-id="63ac3-114">Nei servizi XAML .NET, la gestione di <xref:System.Windows.Markup.NullExtension> questa estensione di markup è definita dalla classe .</span><span class="sxs-lookup"><span data-stu-id="63ac3-114">In .NET XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="63ac3-115">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="63ac3-115">WPF Usage Notes</span></span>

<span data-ttu-id="63ac3-116">Si `null` noti che non è necessariamente il valore di annullamento iniziale per una proprietà di dipendenza di tipo riferimento.</span><span class="sxs-lookup"><span data-stu-id="63ac3-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="63ac3-117">Il valore predefinito iniziale può variare per ogni proprietà di dipendenza e può essere basato su metadati specifici della proprietà.</span><span class="sxs-lookup"><span data-stu-id="63ac3-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="63ac3-118">Molte proprietà di dipendenza `null` non accettano come valore, tramite markup o codice a causa delle implementazioni di callback di convalida.</span><span class="sxs-lookup"><span data-stu-id="63ac3-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="63ac3-119">Per ulteriori informazioni sulle proprietà di dipendenza, vedere [Cenni preliminari](../../framework/wpf/advanced/dependency-properties-overview.md)sulle proprietà di dipendenza .</span><span class="sxs-lookup"><span data-stu-id="63ac3-119">For more information about dependency properties, see [Dependency Properties Overview](../../framework/wpf/advanced/dependency-properties-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="63ac3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63ac3-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="63ac3-121">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="63ac3-121">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
- [<span data-ttu-id="63ac3-122">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="63ac3-122">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
