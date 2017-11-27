---
title: Estensione del markup x:Array
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:Array
- xArray
helpviewer_keywords:
- x:Array [XAML Services]
- XAML [XAML Services], x:Array markup extension
ms.assetid: c5358e14-d24c-44c7-b5eb-6062a4fd981c
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 2cefdee5ca2d1b0a6c79325365aa101d767b6926
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="xarray-markup-extension"></a><span data-ttu-id="3d4ae-102">Estensione del markup x:Array</span><span class="sxs-lookup"><span data-stu-id="3d4ae-102">x:Array Markup Extension</span></span>
<span data-ttu-id="3d4ae-103">Fornisce supporto generale per le matrici di oggetti in XAML tramite un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-103">Provides general support for arrays of objects in XAML through a markup extension.</span></span> <span data-ttu-id="3d4ae-104">Corrisponde alla `x:ArrayExtension` tipo XAML in [MS-XAML].</span><span class="sxs-lookup"><span data-stu-id="3d4ae-104">This corresponds to the `x:ArrayExtension` XAML type in [MS-XAML].</span></span>  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="3d4ae-105">Utilizzo della sintassi XAML per gli elementi oggetto</span><span class="sxs-lookup"><span data-stu-id="3d4ae-105">XAML Object Element Usage</span></span>  
  
```  
<x:Array Type="typeName">  
  arrayContents  
</x:Array>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="3d4ae-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="3d4ae-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`typeName`|<span data-ttu-id="3d4ae-107">Il nome del tipo che il `x:Array` conterrà.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-107">The name of the type that your `x:Array` will contain.</span></span> <span data-ttu-id="3d4ae-108">`typeName`potrebbe essere (e spesso è) come prefisso per un file XAML le definizioni dei tipi dello spazio dei nomi che contiene il codice XAML.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-108">`typeName` may be (and often is) prefixed for a XAML namespace that contains the XAML type definitions.</span></span>|  
|`arrayContents`|<span data-ttu-id="3d4ae-109">Il contenuto di elementi che è stato assegnato le funzioni intrinseche `ArrayExtension.Items` proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-109">The items content that is assigned to the intrinsic `ArrayExtension.Items` property.</span></span> <span data-ttu-id="3d4ae-110">In genere, questi elementi vengono specificati come uno o più elementi di oggetto contenuti all'interno di `x:Array` apertura e chiusura.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-110">Typically, these items are specified as one or more object elements contained within the `x:Array` opening and closing tags.</span></span> <span data-ttu-id="3d4ae-111">Gli oggetti specificati di seguito possono essere assegnabile al tipo XAML specificato `typeName`.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-111">Objects specified here are expected to be assignable to the XAML type specified in `typeName`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d4ae-112">Note</span><span class="sxs-lookup"><span data-stu-id="3d4ae-112">Remarks</span></span>  
 <span data-ttu-id="3d4ae-113">`Type`è un attributo obbligatorio per tutti i `x:Array` elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-113">`Type` is a required attribute for all `x:Array` object elements.</span></span> <span data-ttu-id="3d4ae-114">Oggetto `Type` valore del parametro non è necessario utilizzare un `x:Type` estensione di markup; breve nome del tipo è un tipo XAML, che può essere specificato come stringa.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-114">A `Type` parameter value does not need to use an `x:Type` markup extension; the short name of the type is   a XAML type, which can be specified as a string.</span></span>  
  
 <span data-ttu-id="3d4ae-115">Nell'implementazione dei servizi XAML di .NET Framework, la relazione tra il tipo di sintassi XAML per gli input e output CLR <xref:System.Type> della matrice creata viene influenzata dal contesto del servizio per le estensioni di markup.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-115">In the .NET Framework XAML Services implementation, the relationship between the input XAML type and the output CLR <xref:System.Type> of the created array is influenced by service context for markup extensions.</span></span> <span data-ttu-id="3d4ae-116">L'output <xref:System.Type> è il <xref:System.Xaml.XamlType.UnderlyingType%2A> il tipo di input XAML, dopo avere cercato necessari <xref:System.Xaml.XamlType> in base al contesto dello schema XAML e <xref:System.Windows.Markup.IXamlTypeResolver> servizio fornisce il contesto.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-116">The output <xref:System.Type> is the <xref:System.Xaml.XamlType.UnderlyingType%2A> of the input XAML type, after looking up the necessary <xref:System.Xaml.XamlType> based on XAML schema context and the <xref:System.Windows.Markup.IXamlTypeResolver> service the context provides.</span></span>  
  
 <span data-ttu-id="3d4ae-117">Durante l'elaborazione, il contenuto della matrice viene assegnato le `ArrayExtension.Items` proprietà intrinseca.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-117">When processed, the array contents are assigned to the `ArrayExtension.Items` intrinsic property.</span></span> <span data-ttu-id="3d4ae-118">Nel <xref:System.Windows.Markup.ArrayExtension> implementazione, è rappresentato da <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-118">In the <xref:System.Windows.Markup.ArrayExtension> implementation, this is represented by <xref:System.Windows.Markup.ArrayExtension.Items%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="3d4ae-119">Nell'implementazione dei servizi XAML di .NET Framework, la gestione di questa estensione di markup viene definita per la <xref:System.Windows.Markup.ArrayExtension> classe.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-119">In the .NET Framework XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.ArrayExtension> class.</span></span> <span data-ttu-id="3d4ae-120"><xref:System.Windows.Markup.ArrayExtension>non è bloccato e può essere utilizzato come base per un'implementazione dell'estensione di markup per un tipo di matrice personalizzato.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-120"><xref:System.Windows.Markup.ArrayExtension> is not sealed, and could be used as the basis for a markup extension implementation for a custom array type.</span></span>  
  
 <span data-ttu-id="3d4ae-121">`x:Array`è che più destinato generale di estensibilità del linguaggio in XAML.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-121">`x:Array` is more intended for general language extensibility in XAML.</span></span> <span data-ttu-id="3d4ae-122">Ma `x:Array` può anche essere utile per specificare i valori XAML di determinate proprietà che accettano le raccolte con supporto XAML come contenuto strutturato della proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-122">But `x:Array` can also be useful for specifying XAML values of certain properties that take XAML-supported collections as their structured property content.</span></span> <span data-ttu-id="3d4ae-123">Ad esempio, è possibile specificare il contenuto di un <xref:System.Collections.IEnumerable> proprietà con un `x:Array` utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-123">For example, you could specify the contents of an <xref:System.Collections.IEnumerable> property with an `x:Array` usage.</span></span>  
  
 <span data-ttu-id="3d4ae-124">`x:Array` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-124">`x:Array` is a markup extension.</span></span> <span data-ttu-id="3d4ae-125">Le estensioni di markup in genere vengono implementate quando per i valori dell'attributo devono essere utilizzati caratteri escape in modo che non vengano considerati come valori letterali o nomi di gestori e il requisito è più globale del semplice utilizzo di convertitori dei tipi su alcuni tipi o proprietà.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-125">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="3d4ae-126">`x:Array`parzialmente rappresenta un'eccezione alla regola perché invece di fornire la gestione dei valori di attributo alternativo, `x:Array` fornisce la gestione alternativa del contenuto di testo interno.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-126">`x:Array` is partially an exception to that rule because instead of providing alternative attribute value handling, `x:Array` provides alternative handling of its inner text content.</span></span> <span data-ttu-id="3d4ae-127">Questo comportamento consente i tipi che potrebbero non essere supportati da un modello di contenuto esistente per essere raggruppati in una matrice e a cui fa riferimento in un secondo momento nel code-behind accedere alla matrice denominata; è possibile chiamare <xref:System.Array> metodi per ottenere i singoli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-127">This behavior enables types that might not be supported by an existing content model to be grouped into an array and referenced later in code-behind by accessing the named array; you can call <xref:System.Array> methods to get individual array items.</span></span>  
  
 <span data-ttu-id="3d4ae-128">Tutte le estensioni di markup in XAML utilizzano le parentesi graffe ({,}`)` nella relativa sintassi degli attributi, che è la convenzione mediante il quale un processore XAML riconosce che il valore dell'attributo deve essere elaborato da un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-128">All markup extensions in XAML use the braces ({,}`)` in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must process the attribute value.</span></span> <span data-ttu-id="3d4ae-129">Per ulteriori informazioni sulle estensioni di markup in generale, vedere [convertitori di tipi ed estensioni di Markup per XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="3d4ae-129">For more information about markup extensions in general, see [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md).</span></span>  
  
 <span data-ttu-id="3d4ae-130">In XAML 2009, `x:Array` è definito come un tipo primitivo anziché un'estensione di markup del linguaggio.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-130">In XAML 2009, `x:Array` is defined as a language primitive instead of a markup extension.</span></span> <span data-ttu-id="3d4ae-131">Per ulteriori informazioni, vedere [tipi incorporati per primitive del linguaggio XAML comuni](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).</span><span class="sxs-lookup"><span data-stu-id="3d4ae-131">For more information, see [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md).</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="3d4ae-132">Note sull'utilizzo WPF</span><span class="sxs-lookup"><span data-stu-id="3d4ae-132">WPF Usage Notes</span></span>  
 <span data-ttu-id="3d4ae-133">In genere, gli elementi di oggetti che popolano un `x:Array` non sono gli elementi esistenti nel [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] spazio dei nomi XAML e richiedono un mapping del prefisso di uno spazio dei nomi XAML non predefinito.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-133">Typically, the object elements that populate an `x:Array` are not elements that exist in the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] XAML namespace, and require a prefix mapping to a non-default XAML namespace.</span></span>  
  
 <span data-ttu-id="3d4ae-134">Ad esempio, ecco una semplice matrice di due stringhe, con la `sys` prefisso (e anche `x`) definiti a livello della matrice.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-134">For example, the following is a simple array of two strings, with the `sys` prefix (and also `x`) defined at the level of the array.</span></span>  
  
 <span data-ttu-id="3d4ae-135">[xaml]</span><span class="sxs-lookup"><span data-stu-id="3d4ae-135">[xaml]</span></span>  
  
 `<x:Array Type="sys:String" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`  
  
 `xmlns:sys="clr-namespace:System;assembly=mscorlib">`  
  
 `<sys:String>Hello</sys:String>`  
  
 `<sys:String>World</sys:String>`  
  
 `</x:Array>`  
  
 <span data-ttu-id="3d4ae-136">Per i tipi personalizzati che vengono utilizzati come elementi di matrice, la classe deve inoltre supportare i requisiti per la creazione di un'istanza in XAML come elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="3d4ae-136">For custom types that are used as array elements, the class must also support the requirements for being instantiated in XAML as object elements.</span></span> <span data-ttu-id="3d4ae-137">Per ulteriori informazioni, vedere [classi XAML e personalizzate per WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="3d4ae-137">For more information, see [XAML and Custom Classes for WPF](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4ae-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d4ae-138">See Also</span></span>  
 [<span data-ttu-id="3d4ae-139">Estensioni di markup e XAML WPF</span><span class="sxs-lookup"><span data-stu-id="3d4ae-139">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="3d4ae-140">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="3d4ae-140">Types Migrated from WPF to System.Xaml</span></span>](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)
