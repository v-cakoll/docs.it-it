---
title: Estensione del markup x:Static
ms.date: 03/30/2017
f1_keywords:
- StaticExtension
- xStatic
- x:Static
helpviewer_keywords:
- x:Static markup extension [XAML Services]
- Static markup extension in XAML [XAML Services]
- XAML [XAML Services], x:Static markup extension
ms.assetid: 056aee79-7cdd-434f-8174-dfc856cad343
ms.openlocfilehash: fb9ee6807135f17fd9e0c799533bba28b369ebe2
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "82072025"
---
# <a name="xstatic-markup-extension"></a><span data-ttu-id="e0811-102">Estensione del markup x:Static</span><span class="sxs-lookup"><span data-stu-id="e0811-102">x:Static Markup Extension</span></span>

<span data-ttu-id="e0811-103">Fa riferimento a qualsiasi entità di codice statico per valore definita in modo conforme a CLS (Common Language Specification).</span><span class="sxs-lookup"><span data-stu-id="e0811-103">References any static by-value code entity that is defined in a Common Language Specification (CLS)–compliant way.</span></span> <span data-ttu-id="e0811-104">La proprietà statica a cui si fa riferimento può essere utilizzata per fornire il valore di una proprietà in XAML.</span><span class="sxs-lookup"><span data-stu-id="e0811-104">The static property that is referenced can be used to provide the value of a property in XAML.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="e0811-105">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="e0811-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Static prefix:typeName.staticMemberName}" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="e0811-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="e0811-106">XAML Values</span></span>

| | |
|-|-|
|`prefix`|<span data-ttu-id="e0811-107">Facoltativa.</span><span class="sxs-lookup"><span data-stu-id="e0811-107">Optional.</span></span> <span data-ttu-id="e0811-108">Prefisso che fa riferimento a uno spazio dei nomi XAML mappato e non predefinito.</span><span class="sxs-lookup"><span data-stu-id="e0811-108">A prefix that refers to a mapped, non-default XAML namespace.</span></span> <span data-ttu-id="e0811-109">`prefix`viene mostrato in modo esplicito nell'utilizzo perché raramente si fa riferimento a proprietà statiche che provengono da uno spazio dei nomi XAML predefinito.</span><span class="sxs-lookup"><span data-stu-id="e0811-109">`prefix` is shown explicitly in the usage because you rarely reference static properties that come from a default XAML namespace.</span></span> <span data-ttu-id="e0811-110">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="e0811-110">See Remarks.</span></span>|
|`typeName`|<span data-ttu-id="e0811-111">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0811-111">Required.</span></span> <span data-ttu-id="e0811-112">Nome del tipo che definisce il membro statico desiderato.</span><span class="sxs-lookup"><span data-stu-id="e0811-112">The name of the type that defines the desired static member.</span></span>|
|`staticMemberName`|<span data-ttu-id="e0811-113">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0811-113">Required.</span></span> <span data-ttu-id="e0811-114">Nome del membro del valore statico desiderato (una costante, una proprietà statica, un campo o un valore di enumerazione).</span><span class="sxs-lookup"><span data-stu-id="e0811-114">The name of the desired static value member (a constant, a static property, a field, or an enumeration value).</span></span>|

## <a name="remarks"></a><span data-ttu-id="e0811-115">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e0811-115">Remarks</span></span>

<span data-ttu-id="e0811-116">L'entità di codice a cui viene fatto riferimento deve essere una delle seguenti:</span><span class="sxs-lookup"><span data-stu-id="e0811-116">The code entity that is referenced must be one of the following:</span></span>

- <span data-ttu-id="e0811-117">Una costante</span><span class="sxs-lookup"><span data-stu-id="e0811-117">A constant</span></span>
- <span data-ttu-id="e0811-118">Una proprietà statica</span><span class="sxs-lookup"><span data-stu-id="e0811-118">A static property</span></span>
- <span data-ttu-id="e0811-119">Un campo</span><span class="sxs-lookup"><span data-stu-id="e0811-119">A field</span></span>
- <span data-ttu-id="e0811-120">Valore di enumerazioneAn enumeration value</span><span class="sxs-lookup"><span data-stu-id="e0811-120">An enumeration value</span></span>

<span data-ttu-id="e0811-121">Se si specifica qualsiasi altra entità di codice, ad esempio una proprietà non statica, si verifica un errore in fase di compilazione se il codice XAML viene compilato markup o un'eccezione di analisi in fase di caricamento XAML.</span><span class="sxs-lookup"><span data-stu-id="e0811-121">Specifying any other code entity, such as a nonstatic property, causes a compile-time error if the XAML is markup compiled, or a XAML load-time parse exception.</span></span>

<span data-ttu-id="e0811-122">È possibile `x:Static` creare riferimenti a campi statici o proprietà che non si trovano nello spazio dei nomi XAML predefinito per il documento XAML corrente. tuttavia, ciò richiede un mapping di prefisso.</span><span class="sxs-lookup"><span data-stu-id="e0811-122">You can make `x:Static` references to static fields or properties that are not in the default XAML namespace for the current XAML document; however, this requires a prefix mapping.</span></span> <span data-ttu-id="e0811-123">Gli spazi dei nomi XAML sono quasi sempre definiti nell'elemento radice del documento XAML.</span><span class="sxs-lookup"><span data-stu-id="e0811-123">XAML namespaces are almost always defined on the root element of the XAML document.</span></span>

<span data-ttu-id="e0811-124">Le operazioni di ricerca per le proprietà statiche possono essere eseguite dai servizi XAML .NET e dai relativi reader XAML e writer XAML, quando vengono eseguite con il contesto dello schema XAML predefinito.</span><span class="sxs-lookup"><span data-stu-id="e0811-124">The lookup operations for static properties can be performed by .NET XAML Services and its XAML readers and XAML writers, when they are running with the default XAML schema context.</span></span> <span data-ttu-id="e0811-125">Questo contesto dello schema XAML può usare la reflection CLR per fornire i valori statici necessari per la costruzione dell'oggetto grafico.</span><span class="sxs-lookup"><span data-stu-id="e0811-125">This XAML schema context can use CLR reflection to provide the necessary static values for object graph construction.</span></span> <span data-ttu-id="e0811-126">L'impostazione `typeName` specificata è in realtà un nome di tipo XAML, non un nome di tipo CLR, anche se questi sono essenzialmente lo stesso nome quando si usa il contesto dello schema XAML predefinito o quando si utilizzano tutti i framework di implementazione XAML basati su CLR esistenti.</span><span class="sxs-lookup"><span data-stu-id="e0811-126">The `typeName` you specify is actually a XAML type name, not a CLR type name, although these are essentially the same name when using the default XAML schema context or when using all existing CLR-based XAML-implementing frameworks.</span></span>

<span data-ttu-id="e0811-127">Prestare attenzione `x:Static` quando si effettuano riferimenti che non sono direttamente il tipo di valore di una proprietà.</span><span class="sxs-lookup"><span data-stu-id="e0811-127">Use caution when you make `x:Static` references that are not directly the type of a property's value.</span></span> <span data-ttu-id="e0811-128">Nella sequenza di elaborazione XAML, i valori forniti da un'estensione di markup non richiamano la conversione di valori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="e0811-128">In the XAML processing sequence, provided values from a markup extension do not invoke additional value conversion.</span></span> <span data-ttu-id="e0811-129">Questo vale anche `x:Static` se il riferimento crea una stringa di testo e una conversione di valore per i valori di attributo in base alla stringa di testo si verifica in genere per quel membro specifico o per qualsiasi valore del membro del tipo restituito.</span><span class="sxs-lookup"><span data-stu-id="e0811-129">This is true even if your `x:Static` reference creates a text string, and a value conversion for attribute values based on text string typically occurs either for that specific member or for any member values of the return type.</span></span>

<span data-ttu-id="e0811-130">La sintassi per gli attributi è quella più comunemente utilizzata con questa estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="e0811-130">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="e0811-131">Il token di stringa fornito dopo la stringa dell'identificatore `x:Static` viene assegnato come valore <xref:System.Windows.Markup.StaticExtension.Member%2A> della classe dell'estensione <xref:System.Windows.Markup.StaticExtension> sottostante.</span><span class="sxs-lookup"><span data-stu-id="e0811-131">The string token provided after the `x:Static` identifier string is assigned as the <xref:System.Windows.Markup.StaticExtension.Member%2A> value of the underlying <xref:System.Windows.Markup.StaticExtension> extension class.</span></span>

<span data-ttu-id="e0811-132">Esistono altri due utilizzi XAML tecnicamente possibili.</span><span class="sxs-lookup"><span data-stu-id="e0811-132">There are two other XAML usages that are technically possible.</span></span> <span data-ttu-id="e0811-133">Tuttavia, questi utilizzi sono meno comuni perché sono inutilmente dettagliati:However, these usages are less common because they are unnecessarily verbose:</span><span class="sxs-lookup"><span data-stu-id="e0811-133">However, these usages are less common because they are unnecessarily verbose:</span></span>

01. <span data-ttu-id="e0811-134">Sintassi degli elementi oggetto.</span><span class="sxs-lookup"><span data-stu-id="e0811-134">Object element syntax.</span></span>

    ```xaml
    <x:Static Member="prefix:typeName.staticMemberName" ... />
    ```

02. <span data-ttu-id="e0811-135">Sintassi dell'attributo con proprietà Member esplicita per la stringa di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e0811-135">Attribute syntax with explicit Member property for initialization string.</span></span>

    ```xaml
    <object property="{x:Static Member=prefix:typeName.staticMemberName}" ... />
    ```

<span data-ttu-id="e0811-136">Nell'implementazione dei servizi XAML .NET, la <xref:System.Windows.Markup.StaticExtension> gestione di questa estensione di markup è definita dalla classe .</span><span class="sxs-lookup"><span data-stu-id="e0811-136">In .NET XAML Services implementation, the handling for this markup extension is defined by the <xref:System.Windows.Markup.StaticExtension> class.</span></span>

<span data-ttu-id="e0811-137">`x:Static` è un'estensione di markup.</span><span class="sxs-lookup"><span data-stu-id="e0811-137">`x:Static` is a markup extension.</span></span> <span data-ttu-id="e0811-138">Tutte le estensioni `{` di `}` markup in XAML usano i caratteri e nella sintassi degli attributi, ovvero la convenzione in base alla quale un processore XAML riconosce che un'estensione di markup deve fornire un valore.</span><span class="sxs-lookup"><span data-stu-id="e0811-138">All markup extensions in XAML use the `{` and `}` characters in their attribute syntax, which is the convention by which a XAML processor recognizes that a markup extension must provide a value.</span></span> <span data-ttu-id="e0811-139">Per ulteriori informazioni sulle estensioni di markup, vedere [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0811-139">For more information about markup extensions, see [Markup Extensions for XAML Overview](markup-extensions-overview.md).</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="e0811-140">Note sull'utilizzo di WPF</span><span class="sxs-lookup"><span data-stu-id="e0811-140">WPF Usage Notes</span></span>

<span data-ttu-id="e0811-141">Lo spazio dei nomi XAML predefinito utilizzato per la programmazione WPFWPF non contiene molte proprietà statiche utili `{x:Static}` e la maggior parte delle proprietà statiche utili dispone di supporto, ad esempio convertitori di tipi che facilitano l'utilizzo senza richiedere .</span><span class="sxs-lookup"><span data-stu-id="e0811-141">The default XAML namespace you use for WPF programming does not contain many useful static properties, and most of the useful static properties have support such as type converters that facilitate the usage without requiring `{x:Static}` .</span></span> <span data-ttu-id="e0811-142">Per le proprietà statiche, è necessario eseguire il mapping di un prefisso per uno spazio dei nomi XAML se si verifica una delle condizioni seguenti:For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span><span class="sxs-lookup"><span data-stu-id="e0811-142">For static properties, you must map a prefix for a XAML namespace if one of the following is true:</span></span>

- <span data-ttu-id="e0811-143">Si fa riferimento a un tipo esistente in WPFWPF ma non`http://schemas.microsoft.com/winfx/2006/xaml/presentation`fa parte dello spazio dei nomi XAML predefinito per WPF ( ).</span><span class="sxs-lookup"><span data-stu-id="e0811-143">You are referencing a type that exists in WPF but is not part of the default XAML namespace for WPF (`http://schemas.microsoft.com/winfx/2006/xaml/presentation`).</span></span> <span data-ttu-id="e0811-144">Si tratta di uno `x:Static`scenario abbastanza comune per l'utilizzo di .</span><span class="sxs-lookup"><span data-stu-id="e0811-144">This is a fairly common scenario for using `x:Static`.</span></span> <span data-ttu-id="e0811-145">Ad esempio, è `x:Static` possibile utilizzare un riferimento <xref:System> con un mapping dello spazio dei nomi XAML <xref:System.Environment> allo spazio dei nomi CLR e all'assembly mscorlib per fare riferimento alle proprietà statiche della classe.</span><span class="sxs-lookup"><span data-stu-id="e0811-145">For example, you might use an `x:Static` reference with a XAML namespace mapping to the <xref:System> CLR namespace and mscorlib assembly in order to reference the static properties of the <xref:System.Environment> class.</span></span>

- <span data-ttu-id="e0811-146">Si fa riferimento a un tipo da un assembly personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e0811-146">You are referencing a type from a custom assembly.</span></span>

- <span data-ttu-id="e0811-147">Si fa riferimento a un tipo esistente in un assembly WPF, ma tale tipo si trova all'interno di uno spazio dei nomi CLR di cui non è stato eseguito il mapping per far parte dello spazio dei nomi XAML predefinito WPF.</span><span class="sxs-lookup"><span data-stu-id="e0811-147">You are referencing a type that exists in a WPF assembly, but that type is within a CLR namespace that was not mapped to be part of the WPF default XAML namespace.</span></span> <span data-ttu-id="e0811-148">Il mapping degli spazi dei nomi CLR nello spazio dei nomi XAML predefinito per WPF viene eseguito mediante definizioni nei vari assembly WPF (per ulteriori informazioni su questo concetto, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span><span class="sxs-lookup"><span data-stu-id="e0811-148">The mapping of CLR namespaces into the default XAML namespace for WPF is performed by definitions in the various WPF assemblies (for more information about this concept, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)).</span></span> <span data-ttu-id="e0811-149">Gli spazi dei nomi CLR non mappati possono esistere se tale spazio dei nomi <xref:System.Windows.Threading>CLR è composto principalmente da definizioni di classe che in genere non sono destinate a XAML, ad esempio .</span><span class="sxs-lookup"><span data-stu-id="e0811-149">Non-mapped CLR namespaces can exist if that CLR namespace is composed mostly of class definitions that are not typically intended for XAML, such as <xref:System.Windows.Threading>.</span></span>

<span data-ttu-id="e0811-150">Per altre informazioni su come usare prefissi e spazi dei nomi XAML per WPF, vedere [Spazi dei nomi XAML e Mapping degli spazi dei nomi per XAML WPF.](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)</span><span class="sxs-lookup"><span data-stu-id="e0811-150">For more information on how to use prefixes and XAML namespaces for WPF, see [XAML Namespaces and Namespace Mapping for WPF XAML](../../framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0811-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0811-151">See also</span></span>

- [<span data-ttu-id="e0811-152">Estensione del markup x:Type</span><span class="sxs-lookup"><span data-stu-id="e0811-152">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="e0811-153">Tipi migrati da WPF a System.Xaml</span><span class="sxs-lookup"><span data-stu-id="e0811-153">Types Migrated from WPF to System.Xaml</span></span>](../../framework/wpf/advanced/types-migrated-from-wpf-to-system.md)
