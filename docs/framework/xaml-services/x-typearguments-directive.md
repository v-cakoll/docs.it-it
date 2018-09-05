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
ms.openlocfilehash: 28eda94914125f2c5849a471671c8e283475c82c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43670782"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="581ab-102">Direttiva x:TypeArguments</span><span class="sxs-lookup"><span data-stu-id="581ab-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="581ab-103">Passa vincoli di tipo generico per il costruttore del tipo generico.</span><span class="sxs-lookup"><span data-stu-id="581ab-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="581ab-104">Uso della sintassi XAML per gli attributi</span><span class="sxs-lookup"><span data-stu-id="581ab-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="581ab-105">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="581ab-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="581ab-106">Una dichiarazione di elemento oggetto di un tipo XAML, supportata da un tipo generico di CLR.</span><span class="sxs-lookup"><span data-stu-id="581ab-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="581ab-107">Se `object` fa riferimento a un tipo XAML non dello spazio dei nomi XAML predefinito `object` richiede un prefisso per indicare lo spazio dei nomi XAML in cui `object` esiste.</span><span class="sxs-lookup"><span data-stu-id="581ab-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="581ab-108">Stringa che dichiara uno o più XAML digitare nomi sotto forma di stringhe, che fornisce gli argomenti tipo per il tipo generico di CLR.</span><span class="sxs-lookup"><span data-stu-id="581ab-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="581ab-109">Vedere la sezione Osservazioni per le note sulla sintassi aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="581ab-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="581ab-110">Note</span><span class="sxs-lookup"><span data-stu-id="581ab-110">Remarks</span></span>  
 <span data-ttu-id="581ab-111">Nella maggior parte dei casi, i tipi di XAML vengono usati come un elemento di informazione in un `typeString` stringa hanno il prefisso.</span><span class="sxs-lookup"><span data-stu-id="581ab-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="581ab-112">I tipi tipici dei vincoli generici di Common Language Runtime (ad esempio, <xref:System.Int32> e <xref:System.String>) provengono da librerie di classi base di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="581ab-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="581ab-113">Tali librerie non sono spazi dei nomi XAML predefinito specifico del framework mappate al tipico e pertanto, richiedono un mapping del prefisso per l'utilizzo XAML.</span><span class="sxs-lookup"><span data-stu-id="581ab-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="581ab-114">È possibile specificare più di un nome di tipo XAML usando una virgola di delimitazione.</span><span class="sxs-lookup"><span data-stu-id="581ab-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="581ab-115">Se i vincoli generici usano tipi generici, gli argomenti di tipo di vincolo annidata possono essere contenuti in parentesi ().</span><span class="sxs-lookup"><span data-stu-id="581ab-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="581ab-116">Si noti che questa definizione di `x:TypeArguments` è specifico di servizi XAML di .NET Framework e usando il supporto CLR.</span><span class="sxs-lookup"><span data-stu-id="581ab-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="581ab-117">Una definizione a livello di linguaggio è reperibile nel [ \[MS-XAML\] sezione 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span><span class="sxs-lookup"><span data-stu-id="581ab-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="581ab-118">Esempi di utilizzo</span><span class="sxs-lookup"><span data-stu-id="581ab-118">Usage Examples</span></span>  
 <span data-ttu-id="581ab-119">Per questi esempi, si supponga che siano dichiarate per le definizioni dello spazio dei nomi XAML seguenti:</span><span class="sxs-lookup"><span data-stu-id="581ab-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="581ab-120">Elenco\<stringa ></span><span class="sxs-lookup"><span data-stu-id="581ab-120">List\<String></span></span>  
 <span data-ttu-id="581ab-121">`<scg:List x:TypeArguments="sys:String" ...>` Crea un'istanza di una nuova <xref:System.Collections.Generic.List%601> con un <xref:System.String> argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="581ab-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="581ab-122">Dizionario\<String, String ></span><span class="sxs-lookup"><span data-stu-id="581ab-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="581ab-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` Crea un'istanza di una nuova <xref:System.Collections.Generic.Dictionary%602> con due <xref:System.String> gli argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="581ab-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="581ab-124">Coda di < oggetto KeyValuePair\<String, String >></span><span class="sxs-lookup"><span data-stu-id="581ab-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="581ab-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` Crea un'istanza di una nuova <xref:System.Collections.Generic.Queue%601> che ha un vincolo <xref:System.Collections.Generic.KeyValuePair%602> con gli argomenti di tipo di vincolo interno <xref:System.String> e <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="581ab-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="581ab-126">Utilizzi XAML generica di XAML 2006 e WPF</span><span class="sxs-lookup"><span data-stu-id="581ab-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="581ab-127">Per l'uso di XAML 2006 e XAML che viene usato per le applicazioni WPF, le limitazioni seguenti per `x:TypeArguments` e gli utilizzi di tipo generico da XAML in generale:</span><span class="sxs-lookup"><span data-stu-id="581ab-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
-   <span data-ttu-id="581ab-128">Solo l'elemento radice di un file XAML può supportare un utilizzo generico di XAML che fa riferimento a un tipo generico.</span><span class="sxs-lookup"><span data-stu-id="581ab-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
-   <span data-ttu-id="581ab-129">L'elemento radice deve eseguire il mapping a un tipo generico con almeno un argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="581ab-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="581ab-130">Un esempio è <xref:System.Windows.Navigation.PageFunction%601>.</span><span class="sxs-lookup"><span data-stu-id="581ab-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="581ab-131">Le funzioni di pagina sono lo scenario principale per il supporto di utilizzo generico di XAML in WPF.</span><span class="sxs-lookup"><span data-stu-id="581ab-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
-   <span data-ttu-id="581ab-132">L'elemento oggetto XAML elemento radice per il tipo generico debba anche dichiarare una classe parziale che usa `x:Class`.</span><span class="sxs-lookup"><span data-stu-id="581ab-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="581ab-133">Questo vale anche se la definizione di un controllo WPF di azione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="581ab-133">This is true even if defining a WPF build action.</span></span>  
  
-   <span data-ttu-id="581ab-134">`x:TypeArguments` non è possibile fare riferimento a vincoli generici annidati.</span><span class="sxs-lookup"><span data-stu-id="581ab-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="581ab-135">XAML 2009 o XAML 2006 senza WPF 3.0 o 3.5 WPF delle dipendenze</span><span class="sxs-lookup"><span data-stu-id="581ab-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="581ab-136">Nei servizi XAML di .NET Framework per XAML 2006 o XAML 2009, sono flessibili le restrizioni sull'utilizzo XAML generico basate su WPF.</span><span class="sxs-lookup"><span data-stu-id="581ab-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="581ab-137">È possibile creare un'istanza di un elemento oggetto generico in qualsiasi posizione nel markup XAML in grado di supportare il modello di sistema e l'oggetto di tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="581ab-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="581ab-138">Se si utilizza XAML 2009, anziché eseguire il mapping di CLR di base dei tipi per ottenere i tipi XAML per primitive di linguaggio comuni, è possibile usare [i tipi nativi per primitive del linguaggio XAML comuni](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) come elementi di informazione in un `typeString`.</span><span class="sxs-lookup"><span data-stu-id="581ab-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="581ab-139">Ad esempio, si potrebbe dichiarare seguenti (non illustrato mapping del prefisso, ma x è lo spazio dei nomi XAML del linguaggio XAML di XAML 2009):</span><span class="sxs-lookup"><span data-stu-id="581ab-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="581ab-140">In WPF e quando la destinazione [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile usare le funzionalità di XAML 2009 con `x:TypeArguments` ma solo per XAML loose (XAML non è compilato dal markup).</span><span class="sxs-lookup"><span data-stu-id="581ab-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="581ab-141">Il codice XAML compilato dal markup per WPF e il modulo BAML di XAML non supportano attualmente le parole chiave e le funzionalità di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="581ab-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="581ab-142">Se è necessario di una compilazione di markup di XAML, è necessario operare con le restrizioni indicate nella sezione "XAML 2006 e WPF XAML utilizzi generici".</span><span class="sxs-lookup"><span data-stu-id="581ab-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="581ab-143">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="581ab-143">See Also</span></span>  
 [<span data-ttu-id="581ab-144">Direttiva x:Class</span><span class="sxs-lookup"><span data-stu-id="581ab-144">x:Class Directive</span></span>](../../../docs/framework/xaml-services/x-class-directive.md)  
 [<span data-ttu-id="581ab-145">Estensione di markup x:Type</span><span class="sxs-lookup"><span data-stu-id="581ab-145">x:Type Markup Extension</span></span>](../../../docs/framework/xaml-services/x-type-markup-extension.md)  
 [<span data-ttu-id="581ab-146">Tipi incorporati per primitive del linguaggio XAML comuni</span><span class="sxs-lookup"><span data-stu-id="581ab-146">Built-in Types for Common XAML Language Primitives</span></span>](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)  
 [<span data-ttu-id="581ab-147">Generics in XAML</span><span class="sxs-lookup"><span data-stu-id="581ab-147">Generics in XAML</span></span>](../../../docs/framework/xaml-services/generics-in-xaml.md)
