---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 5ec6e192688e1065ea847db6c175ad9da0e743fe
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071591"
---
# <a name="xarguments-directive"></a><span data-ttu-id="46b2b-102">Direttiva x:Arguments</span><span class="sxs-lookup"><span data-stu-id="46b2b-102">x:Arguments Directive</span></span>

<span data-ttu-id="46b2b-103">Crea pacchetti di argomenti di costruzione per una dichiarazione di elemento oggetto costruttore senza parametri in XAML o per una dichiarazione di oggetto metodo factory.</span><span class="sxs-lookup"><span data-stu-id="46b2b-103">Packages construction arguments for a non-parameterless constructor object element declaration in XAML, or for a factory method object declaration.</span></span>

## <a name="xaml-element-usage-nonparameterless-constructor"></a><span data-ttu-id="46b2b-104">Utilizzo degli elementi XAML (costruttore senza parametri)XAML Element Usage (Nonparameterless constructor)</span><span class="sxs-lookup"><span data-stu-id="46b2b-104">XAML Element Usage (Nonparameterless constructor)</span></span>

```xaml
<object ...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="46b2b-105">Utilizzo degli elementi XAML (metodo factory)XAML Element Usage (factory method)</span><span class="sxs-lookup"><span data-stu-id="46b2b-105">XAML Element Usage (factory method)</span></span>

```xaml
<object x:FactoryMethod="methodName"...>
  <x:Arguments>
    oneOrMoreObjectElements
  </x:Arguments>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="46b2b-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="46b2b-106">XAML Values</span></span>

|||
|-|-|
|`oneOrMoreObjectElements`|<span data-ttu-id="46b2b-107">Uno o più elementi oggetto che specificano gli argomenti da passare al costruttore non senza parametri di backup o al metodo factory.</span><span class="sxs-lookup"><span data-stu-id="46b2b-107">One or more object elements that specify arguments to be passed to the backing non-parameterless constructor or factory method.</span></span><br /><br /> <span data-ttu-id="46b2b-108">L'utilizzo tipico consiste nell'utilizzare il testo di inizializzazione all'interno degli elementi oggetto per specificare i valori effettivi dell'argomento.</span><span class="sxs-lookup"><span data-stu-id="46b2b-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="46b2b-109">Vedere la sezione Esempi.</span><span class="sxs-lookup"><span data-stu-id="46b2b-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="46b2b-110">L'ordine degli elementi è significativo.</span><span class="sxs-lookup"><span data-stu-id="46b2b-110">The order of the elements is significant.</span></span> <span data-ttu-id="46b2b-111">I tipi XAML nell'ordine devono corrispondere ai tipi e all'ordine dei tipi del costruttore di supporto o dell'overload del metodo factory.</span><span class="sxs-lookup"><span data-stu-id="46b2b-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|
|`methodName`|<span data-ttu-id="46b2b-112">Nome del metodo factory che `x:Arguments` deve elaborare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="46b2b-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|

## <a name="dependencies"></a><span data-ttu-id="46b2b-113">Dependencies</span><span class="sxs-lookup"><span data-stu-id="46b2b-113">Dependencies</span></span>

<span data-ttu-id="46b2b-114">`x:FactoryMethod`possibile modificare l'ambito `x:Arguments` e il comportamento laddove applicati.</span><span class="sxs-lookup"><span data-stu-id="46b2b-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>

<span data-ttu-id="46b2b-115">Se `x:FactoryMethod` non viene `x:Arguments` specificato alcun valore, si applica alle firme alternative (non predefinite) dei costruttori di backup.</span><span class="sxs-lookup"><span data-stu-id="46b2b-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>

<span data-ttu-id="46b2b-116">Se `x:FactoryMethod` viene `x:Arguments` specificato, si applica a un overload del metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="46b2b-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>

## <a name="remarks"></a><span data-ttu-id="46b2b-117">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="46b2b-117">Remarks</span></span>

<span data-ttu-id="46b2b-118">XAML 2006 può supportare l'inizializzazione non predefinita tramite testo di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="46b2b-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="46b2b-119">Tuttavia, l'applicazione pratica di una tecnica di costruzione del testo di inizializzazione è limitata.</span><span class="sxs-lookup"><span data-stu-id="46b2b-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="46b2b-120">Il testo di inizializzazione viene considerato come una singola stringa di testo; pertanto, aggiunge solo funzionalità per l'inizializzazione di un singolo parametro, a meno che non venga definito un convertitore di tipi per il comportamento di costruzione in grado di analizzare gli elementi di informazioni personalizzate e i delimitatori personalizzati dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="46b2b-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="46b2b-121">Inoltre, la stringa di testo per la logica dell'oggetto è potenzialmente il convertitore di tipi predefinito nativo del parser XAML per la gestione di primitive diverse da una stringa true.</span><span class="sxs-lookup"><span data-stu-id="46b2b-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>

<span data-ttu-id="46b2b-122">L'utilizzo `x:Arguments` di XAML non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="46b2b-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="46b2b-123">È più simile ad altre direttive, ad `x:Code` esempio in cui l'elemento decontrassegna un intervallo in cui il markup deve essere interpretato come diverso da quello predefinito per il contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="46b2b-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="46b2b-124">In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni sui tipi di argomento, utilizzati dai parser XAML per determinare a quale firma del metodo factory del costruttore specifico un `x:Arguments` utilizzo sta tentando di fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="46b2b-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>

<span data-ttu-id="46b2b-125">`x:Arguments`per un elemento oggetto da costruire deve precedere qualsiasi altro elemento proprietà, contenuto, testo interno o stringhe di inizializzazione dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="46b2b-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="46b2b-126">Gli elementi `x:Arguments` dell'oggetto all'interno possono includere attributi e stringhe di inizializzazione, come consentito da tale tipo XAML e dal relativo costruttore o metodo factory di supporto.</span><span class="sxs-lookup"><span data-stu-id="46b2b-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="46b2b-127">Per l'oggetto o gli argomenti, è possibile specificare tipi XAML personalizzati o tipi XAML che non rientrano nello spazio dei nomi XAML predefinito facendo riferimento ai mapping dei prefissi stabiliti.</span><span class="sxs-lookup"><span data-stu-id="46b2b-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>

<span data-ttu-id="46b2b-128">I processori XAML usano le linee guida `x:Arguments` seguenti per determinare come devono essere usati gli argomenti specificati in per costruire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="46b2b-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="46b2b-129">Se `x:FactoryMethod` viene specificato, le informazioni `x:FactoryMethod` vengono confrontate `x:FactoryMethod` con l'oggetto specificato (si noti che il valore di è il nome del metodo e il metodo denominato può avere overload.</span><span class="sxs-lookup"><span data-stu-id="46b2b-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="46b2b-130">Se `x:FactoryMethod` non viene specificato, le informazioni vengono confrontate con il set di tutti gli overload del costruttore pubblico dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="46b2b-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="46b2b-131">La logica di elaborazione XAML confronta quindi il numero di parametri e seleziona l'overload con arity corrispondente.</span><span class="sxs-lookup"><span data-stu-id="46b2b-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="46b2b-132">Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi dei parametri in base ai tipi XAML degli elementi oggetto forniti.</span><span class="sxs-lookup"><span data-stu-id="46b2b-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="46b2b-133">Se è ancora presente più di una corrispondenza, il comportamento del processore XAML non è definito.</span><span class="sxs-lookup"><span data-stu-id="46b2b-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="46b2b-134">Se `x:FactoryMethod` viene specificato un oggetto ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="46b2b-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>

<span data-ttu-id="46b2b-135">L'utilizzo `<x:Arguments>string</x:Arguments>` di un attributo XAML è tecnicamente possibile.</span><span class="sxs-lookup"><span data-stu-id="46b2b-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="46b2b-136">Tuttavia, questo non fornisce funzionalità oltre a quanto potrebbe essere fatto altrimenti attraverso il testo di inizializzazione e convertitori di tipi, e l'utilizzo di questa sintassi non è l'intenzione di progettazione delle funzionalità del metodo factory di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="46b2b-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>

## <a name="examples"></a><span data-ttu-id="46b2b-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="46b2b-137">Examples</span></span>

<span data-ttu-id="46b2b-138">Nell'esempio seguente viene illustrata una firma del `x:Arguments` costruttore senza parametri, quindi l'utilizzo XAML di tale accede a tale firma.</span><span class="sxs-lookup"><span data-stu-id="46b2b-138">The following example shows a non-parameterless constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public class Food {
  private string _name;
  private Int32 _calories;
  public Food(string name, Int32 calories) {
      _name=name;
      _calories=calories;
  }
}
```

```xaml
<my:Food>
  <x:Arguments>
      <x:String>Apple</x:String>
      <x:Int32>150</x:Int32>
  </x:Arguments>
</my:Food>
```

<span data-ttu-id="46b2b-139">Nell'esempio seguente viene illustrata una firma `x:Arguments` del metodo factory di destinazione, quindi l'utilizzo XAML di tale accede a tale firma.</span><span class="sxs-lookup"><span data-stu-id="46b2b-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>

```csharp
public Food TryLookupFood(string name)
{
switch (name) {
  case "Apple": return new Food("Apple",150);
  case "Chocolate": return new Food("Chocolate",200);
  case "Cheese": return new Food("Cheese", 450);
  default: {return new Food(name,0);
}
}
```

```xaml
<my:Food x:FactoryMethod="TryLookupFood">
  <x:Arguments>
      <x:String>Apple</x:String>
  </x:Arguments>
</my:Food>
```

## <a name="see-also"></a><span data-ttu-id="46b2b-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="46b2b-140">See also</span></span>

- [<span data-ttu-id="46b2b-141">Definizione di tipi personalizzati da usare con i servizi XAML .NET</span><span class="sxs-lookup"><span data-stu-id="46b2b-141">Defining Custom Types for Use with .NET XAML Services</span></span>](define-custom-types.md)
- [<span data-ttu-id="46b2b-142">Panoramica di XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="46b2b-142">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
