---
title: Direttiva x:TypeArguments
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 69da9329f140121b66c71d4cf2e99e9d14a1b207
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071353"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="60109-102">Direttiva x:TypeArguments</span><span class="sxs-lookup"><span data-stu-id="60109-102">x:TypeArguments Directive</span></span>

<span data-ttu-id="60109-103">Passa gli argomenti di tipo vincolanti di un generico al costruttore del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="60109-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="60109-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="60109-104">XAML Attribute Usage</span></span>

```xaml
<object x:TypeArguments="typeString" .../>
```

## <a name="xaml-values"></a><span data-ttu-id="60109-105">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="60109-105">XAML Values</span></span>

|||
|-|-|
|`object`|<span data-ttu-id="60109-106">Dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico CLR.</span><span class="sxs-lookup"><span data-stu-id="60109-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="60109-107">Se `object` fa riferimento a un tipo XAML che `object` non proviene dallo spazio `object` dei nomi XAML predefinito, richiede un prefisso per indicare lo spazio dei nomi XAML laddove è presente.</span><span class="sxs-lookup"><span data-stu-id="60109-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|
|`typeString`|<span data-ttu-id="60109-108">Stringa che dichiara uno o più nomi di tipo XAML come stringhe, che fornisce gli argomenti di tipo per il tipo generico CLR.</span><span class="sxs-lookup"><span data-stu-id="60109-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="60109-109">Vedere Osservazioni per ulteriori note sulla sintassi.</span><span class="sxs-lookup"><span data-stu-id="60109-109">See Remarks for additional syntax notes.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60109-110">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="60109-110">Remarks</span></span>

<span data-ttu-id="60109-111">Nella maggior parte dei casi, i tipi XAML `typeString` utilizzati come elemento di informazioni in una stringa sono preceduti dal prefisso.</span><span class="sxs-lookup"><span data-stu-id="60109-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="60109-112">Tipi tipici di vincoli <xref:System.Int32> generici CLR (ad esempio, e <xref:System.String>) provengono da librerie di classi base CLR.</span><span class="sxs-lookup"><span data-stu-id="60109-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="60109-113">Tali librerie non sono mappate a tipici spazi dei nomi XAML predefiniti specifici del framework e pertanto richiedono un mapping del prefisso per l'utilizzo di XAML.</span><span class="sxs-lookup"><span data-stu-id="60109-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>

<span data-ttu-id="60109-114">È possibile specificare più di un nome di tipo XAML utilizzando un delimitatore virgola.</span><span class="sxs-lookup"><span data-stu-id="60109-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>

<span data-ttu-id="60109-115">Se i vincoli generici stessi utilizzano tipi generici, gli argomenti di tipo del vincolo annidato possono essere contenuti tra parentesi ().</span><span class="sxs-lookup"><span data-stu-id="60109-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>

<span data-ttu-id="60109-116">Si noti `x:TypeArguments` che questa definizione di è specifica dei servizi XAML .NET e l'utilizzo del backup CLR.</span><span class="sxs-lookup"><span data-stu-id="60109-116">Note that this definition of `x:TypeArguments` is specific to .NET XAML Services and using CLR backing.</span></span> <span data-ttu-id="60109-117">Una definizione a livello di linguaggio è disponibile nella [ \[sezione 5.3.11 di MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))</span><span class="sxs-lookup"><span data-stu-id="60109-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>

## <a name="usage-examples"></a><span data-ttu-id="60109-118">Esempi di uso</span><span class="sxs-lookup"><span data-stu-id="60109-118">Usage Examples</span></span>

<span data-ttu-id="60109-119">Per questi esempi, si supponga che siano dichiarate le definizioni dello spazio dei nomi XAML seguenti:For these examples, assume that the following XAML namespace definitions are declared:</span><span class="sxs-lookup"><span data-stu-id="60109-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>

```xaml
xmlns:sys="clr-namespace:System;assembly=mscorlib"
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"
```

### <a name="liststring"></a><span data-ttu-id="60109-120">Stringa\<elenco></span><span class="sxs-lookup"><span data-stu-id="60109-120">List\<String></span></span>

<span data-ttu-id="60109-121">`<scg:List x:TypeArguments="sys:String" ...>`crea un'istanza di una nuova <xref:System.Collections.Generic.List%601> con un <xref:System.String> argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="60109-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>

### <a name="dictionarystringstring"></a><span data-ttu-id="60109-122">Stringa\<dizionario,> stringa</span><span class="sxs-lookup"><span data-stu-id="60109-122">Dictionary\<String,String></span></span>

<span data-ttu-id="60109-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`crea un'istanza di una nuova <xref:System.Collections.Generic.Dictionary%602> con due <xref:System.String> argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="60109-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>

### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="60109-124">Coda<Stringa\<KeyValuePair,>> String</span><span class="sxs-lookup"><span data-stu-id="60109-124">Queue<KeyValuePair\<String,String>></span></span>

<span data-ttu-id="60109-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`crea un'istanza di <xref:System.Collections.Generic.Queue%601> un <xref:System.Collections.Generic.KeyValuePair%602> nuovo che ha <xref:System.String> <xref:System.String>un vincolo di con gli argomenti di tipo vincolo interno e .</span><span class="sxs-lookup"><span data-stu-id="60109-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>

## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="60109-126">XAML 2006 e gli utilizzi XAML generici WPF</span><span class="sxs-lookup"><span data-stu-id="60109-126">XAML 2006 and WPF Generic XAML Usages</span></span>

<span data-ttu-id="60109-127">Per l'utilizzo di XAML 2006 e XAML utilizzato per `x:TypeArguments` le applicazioni WPFWPF, esistono le restrizioni seguenti per gli utilizzi di tipi generici da XAML in generale:</span><span class="sxs-lookup"><span data-stu-id="60109-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>

- <span data-ttu-id="60109-128">Solo l'elemento radice di un file XAML può supportare un utilizzo XAML generico che fa riferimento a un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="60109-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>

- <span data-ttu-id="60109-129">L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="60109-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="60109-130">Un esempio è <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="60109-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="60109-131">Le funzioni di pagina sono lo scenario principale per il supporto dell'utilizzo generico XAML in WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="60109-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>

- <span data-ttu-id="60109-132">L'elemento oggetto XAML dell'elemento radice per `x:Class`il generico deve inoltre dichiarare una classe parziale utilizzando .</span><span class="sxs-lookup"><span data-stu-id="60109-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="60109-133">Questo vale anche se si definisce un'azione di compilazione WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="60109-133">This is true even if defining a WPF build action.</span></span>

- <span data-ttu-id="60109-134">`x:TypeArguments`impossibile fare riferimento a vincoli generici annidati.</span><span class="sxs-lookup"><span data-stu-id="60109-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>

## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="60109-135">XAML 2009 o XAML 2006 senza dipendenza WPF 3.0 o WPF 3.5</span><span class="sxs-lookup"><span data-stu-id="60109-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>

<span data-ttu-id="60109-136">Nei servizi XAML .NET per XAML 2006 o XAML 2009, le restrizioni relative a WPF sull'utilizzo di XAML generico sono rilassate.</span><span class="sxs-lookup"><span data-stu-id="60109-136">In .NET XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="60109-137">È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML che il sistema di tipi di supporto e il modello a oggetti possono supportare.</span><span class="sxs-lookup"><span data-stu-id="60109-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>

<span data-ttu-id="60109-138">Se si utilizza XAML 2009 anziché eseguire il mapping dei tipi di base CLR per ottenere tipi XAML per primitive di linguaggio comuni, è possibile utilizzare [tipi incorporati per le primitive](types-for-primitives.md) del linguaggio XAML comuni come elementi di informazioni in un `typeString`oggetto .</span><span class="sxs-lookup"><span data-stu-id="60109-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](types-for-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="60109-139">Ad esempio, è possibile dichiarare quanto segue (mapping di prefisso non illustrato, ma x è lo spazio dei nomi XAML del linguaggio XAML per XAML 2009):For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="60109-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>

```xaml
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>
```

<span data-ttu-id="60109-140">In WPF wpf e quando la destinazione di .NET Framework 4 o .NET Core 3.0 (o versione successiva), è possibile utilizzare le funzionalità di XAML 2009 con `x:TypeArguments` ma solo per XAML separato (XAML che non è compilato dal markup).</span><span class="sxs-lookup"><span data-stu-id="60109-140">In WPF and when targeting .NET Framework 4 or .NET Core 3.0 (or later), you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="60109-141">Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="60109-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="60109-142">Se è necessario compilare il codice XAML, è necessario operare in base alle restrizioni indicate nella sezione [XAML 2006 e in XAML generico.](#xaml-2006-and-wpf-generic-xaml-usages)</span><span class="sxs-lookup"><span data-stu-id="60109-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the [XAML 2006 and WPF Generic XAML Usages](#xaml-2006-and-wpf-generic-xaml-usages) section.</span></span> <span data-ttu-id="60109-143">BAML è supportato solo in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="60109-143">BAML is only supported in .NET Framework.</span></span>

## <a name="see-also"></a><span data-ttu-id="60109-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60109-144">See also</span></span>

- [<span data-ttu-id="60109-145">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="60109-145">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="60109-146">Estensione del markup x:Type</span><span class="sxs-lookup"><span data-stu-id="60109-146">x:Type Markup Extension</span></span>](xtype-markup-extension.md)
- [<span data-ttu-id="60109-147">Tipi incorporati per primitive del linguaggio XAML comuni</span><span class="sxs-lookup"><span data-stu-id="60109-147">Built-in Types for Common XAML Language Primitives</span></span>](types-for-primitives.md)
- [<span data-ttu-id="60109-148">Generics in XAML</span><span class="sxs-lookup"><span data-stu-id="60109-148">Generics in XAML</span></span>](generics.md)
