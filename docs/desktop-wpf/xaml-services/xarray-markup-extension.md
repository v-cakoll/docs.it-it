---
title: Estensione del markup x:Array
ms.date: 03/30/2017
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
ms.openlocfilehash: b332c43d7f9ffe2117c9afe1ed625c3e3c869813
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072046"
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="f7d6e-102">Estensione del markup x:Array</span><span class="sxs-lookup"><span data-stu-id="f7d6e-102">x:Array Markup Extension</span></span>

<span data-ttu-id="f7d6e-103">Fornisce supporto generale per matrici di oggetti in XAML tramite un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="f7d6e-104">Corrisponde al `x:ArrayExtension` tipo XAML in [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="f7d6e-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="f7d6e-105">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="f7d6e-105">XAML Object Element Usage</span></span>

```xaml
<x:Array Type="typeName">
  arrayContents
</x:Array>
```

## <a name="xaml-values"></a><span data-ttu-id="f7d6e-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="f7d6e-106">XAML Values</span></span>

|||
|-|-|
|`typeName`|<span data-ttu-id="f7d6e-107">Nome del tipo che `x:Array` il tipo conterrà.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="f7d6e-108">`typeName`può essere (e spesso è) prefisso per uno spazio dei nomi XAML che contiene le definizioni di tipo XAML.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|
|`arrayContents`|<span data-ttu-id="f7d6e-109">Contenuto degli elementi assegnato alla `ArrayExtension.Items` proprietà intrinseca.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="f7d6e-110">In genere, questi elementi vengono specificati come `x:Array` uno o più elementi oggetto contenuti all'interno dei tag di apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="f7d6e-111">Gli oggetti specificati qui devono essere assegnabili `typeName`al tipo XAML specificato in .</span><span class="sxs-lookup"><span data-stu-id="f7d6e-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f7d6e-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f7d6e-112">Remarks</span></span>

<span data-ttu-id="f7d6e-113">`Type`è un attributo `x:Array` obbligatorio per tutti gli elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="f7d6e-114">Non `Type` è necessario che un `x:Type` valore di parametro utilizzi un'estensione di markup. il nome breve del tipo è un tipo XAML, che può essere specificato come stringa.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>

<span data-ttu-id="f7d6e-115">Nell'implementazione dei servizi XAML .NET, la relazione <xref:System.Type> tra il tipo XAML di input e CLR di output della matrice creata è influenzata dal contesto del servizio per le estensioni di markup.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-115">In .NET XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="f7d6e-116">L'output <xref:System.Type> <xref:System.Xaml.XamlType.UnderlyingType%2A> è il del tipo XAML di <xref:System.Xaml.XamlType> input, dopo aver <xref:System.Windows.Markup.IXamlTypeResolver> cercato il necessario in base al contesto dello schema XAML e al servizio fornito dal contesto.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>

<span data-ttu-id="f7d6e-117">Durante l'elaborazione, il `ArrayExtension.Items` contenuto della matrice viene assegnato alla proprietà intrinseca.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="f7d6e-118">Nell'implementazione, <xref:System.Windows.Markup.ArrayExtension> questo <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>è rappresentato da .</span><span class="sxs-lookup"><span data-stu-id="f7d6e-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="f7d6e-119">Nell'implementazione dei servizi XAML .NET, la <xref:System.Windows.Markup.ArrayExtension> gestione di questa estensione di markup è definita dalla classe .</span><span class="sxs-lookup"><span data-stu-id="f7d6e-119">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="f7d6e-120"><xref:System.Windows.Markup.ArrayExtension>non è sealed e può essere utilizzato come base per un'implementazione dell'estensione di markup per un tipo di matrice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>

<span data-ttu-id="f7d6e-121">`x:Array`è più destinato all'estensibilità generale del linguaggio in XAML.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="f7d6e-122">Ma `x:Array` può anche essere utile per specificare i valori XAML di determinate proprietà che accettano raccolte supportate da XAML come contenuto della proprietà strutturata.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="f7d6e-123">Ad esempio, è possibile specificare il contenuto di una <xref:System.Collections.IEnumerable> proprietà con un `x:Array` utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>

<span data-ttu-id="f7d6e-124">`x:Array` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="f7d6e-125">Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="f7d6e-126">`x:Array`è parzialmente un'eccezione a tale regola `x:Array` perché invece di fornire una gestione alternativa del valore dell'attributo, fornisce una gestione alternativa del relativo contenuto di testo interno.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="f7d6e-127">Questo comportamento consente ai tipi che potrebbero non essere supportati da un modello di contenuto esistente di essere raggruppati in una matrice e di fare riferimento in un secondo momento nel code-behind accedendo alla matrice denominata. è possibile <xref:System.Array> chiamare i metodi per ottenere singoli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>

<span data-ttu-id="f7d6e-128">Tutte le estensioni di markup{,} `)` in XAML usano le parentesi graffe (nella sintassi degli attributi, che è la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve elaborare il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="f7d6e-129">Per altre informazioni sulle estensioni di markup in generale, vedere Convertitori di tipi ed estensioni di [markup per XAML.](type-converters-and-markup-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="f7d6e-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](type-converters-and-markup-extensions.md).</span></span>

<span data-ttu-id="f7d6e-130">In XAML 2009, `x:Array` è definito come una primitiva del linguaggio anziché un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="f7d6e-131">Per ulteriori informazioni, vedere [Tipi incorporati per le primitive](types-for-primitives.md)di linguaggio XAML comuni .</span><span class="sxs-lookup"><span data-stu-id="f7d6e-131">For more information, see [Built-in Types for Common XAML Language Primitives](types-for-primitives.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="f7d6e-132">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="f7d6e-132">WPF Usage Notes</span></span>

<span data-ttu-id="f7d6e-133">In genere, gli elementi `x:Array` oggetto che popolano un non sono elementi presenti nello spazio dei nomi [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML e richiedono un mapping del prefisso a uno spazio dei nomi XAML non predefinito.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>

<span data-ttu-id="f7d6e-134">Ad esempio, di seguito è riportata una `sys` semplice matrice `x`di due stringhe, con il prefisso (e anche ) definito a livello della matrice.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>

```xaml
<x:Array Type="sys:String"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <sys:String>Hello</sys:String>
  <sys:String>World</sys:String>
</x:Array>
```

<span data-ttu-id="f7d6e-135">Per i tipi personalizzati utilizzati come elementi della matrice, la classe deve supportare anche i requisiti per la cui istanziare in XAML viene creata un'istanza in XAML come elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="f7d6e-135">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="f7d6e-136">Per altre informazioni, vedere [XAML e classi personalizzate per WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="f7d6e-136">For more information, see [XAML and Custom Classes for WPF](../../framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f7d6e-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7d6e-137">See also</span></span>

- [<span data-ttu-id="f7d6e-138">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="f7d6e-138">Markup Extensions and WPF XAML</span></span>](../../framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="f7d6e-139">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="f7d6e-139">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
