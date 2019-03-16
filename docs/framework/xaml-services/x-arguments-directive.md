---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: 351974786b9f4748499279d29202e2051d9268fd
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2019
ms.locfileid: "58043332"
---
# <a name="xarguments-directive"></a><span data-ttu-id="7515e-102">Direttiva x:Arguments</span><span class="sxs-lookup"><span data-stu-id="7515e-102">x:Arguments Directive</span></span>
<span data-ttu-id="7515e-103">Argomenti di costruzione di pacchetti per una dichiarazione dell'elemento oggetto costruttore non predefinito in XAML o per una dichiarazione dell'oggetto metodo factory.</span><span class="sxs-lookup"><span data-stu-id="7515e-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="7515e-104">Utilizzo di un elemento XAML (costruttore non predefinito)</span><span class="sxs-lookup"><span data-stu-id="7515e-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="7515e-105">Utilizzo di un elemento XAML (metodo factory)</span><span class="sxs-lookup"><span data-stu-id="7515e-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="7515e-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="7515e-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="7515e-107">Uno o più elementi di oggetti che specificano gli argomenti da passare per il metodo factory o costruttore non predefinito sottostante.</span><span class="sxs-lookup"><span data-stu-id="7515e-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="7515e-108">Utilizzo tipico consiste nell'usare il testo di inizializzazione all'interno di elementi oggetto per specificare i valori di argomento effettivo.</span><span class="sxs-lookup"><span data-stu-id="7515e-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="7515e-109">Vedere la sezione esempi.</span><span class="sxs-lookup"><span data-stu-id="7515e-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="7515e-110">L'ordine degli elementi è significativo.</span><span class="sxs-lookup"><span data-stu-id="7515e-110">The order of the elements is significant.</span></span> <span data-ttu-id="7515e-111">I tipi XAML in ordine necessario corrispondono ai tipi e digitare ordine sottostante factory o costruttore di overload del metodo.</span><span class="sxs-lookup"><span data-stu-id="7515e-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="7515e-112">Il nome del metodo factory che deve elaborare qualsiasi `x:Arguments` argomenti.</span><span class="sxs-lookup"><span data-stu-id="7515e-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="7515e-113">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="7515e-113">Dependencies</span></span>  
 <span data-ttu-id="7515e-114">`x:FactoryMethod` può modificare l'ambito e il comportamento in cui `x:Arguments` si applica.</span><span class="sxs-lookup"><span data-stu-id="7515e-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="7515e-115">Se nessun `x:FactoryMethod` viene specificato, `x:Arguments` si applica a alternative (diverso) delle firme dei costruttori di backup.</span><span class="sxs-lookup"><span data-stu-id="7515e-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="7515e-116">Se `x:FactoryMethod` viene specificato, `x:Arguments` si applica a un overload del metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="7515e-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7515e-117">Note</span><span class="sxs-lookup"><span data-stu-id="7515e-117">Remarks</span></span>  
 <span data-ttu-id="7515e-118">XAML 2006 possono supportare l'inizializzazione non predefinito tramite il testo di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="7515e-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="7515e-119">Tuttavia, l'applicazione pratica di una tecnica di costruzione di testo di inizializzazione è limitato.</span><span class="sxs-lookup"><span data-stu-id="7515e-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="7515e-120">Testo di inizializzazione viene considerato come una singola stringa di testo; Pertanto, solo aggiunge funzionalità per l'inizializzazione di un singolo parametro che non sia definito un convertitore di tipi per il comportamento di costruzione che consente di analizzare gli elementi di informazioni personalizzate e i delimitatori personalizzati dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="7515e-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="7515e-121">Inoltre, la stringa di testo alla logica dell'oggetto è potenzialmente convertitore di tipi predefiniti nativi del parser XAML specificato per le primitive diverso da una stringa true.</span><span class="sxs-lookup"><span data-stu-id="7515e-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="7515e-122">Il `x:Arguments` sull'utilizzo XAML non utilizzo dell'elemento di proprietà nel senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="7515e-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="7515e-123">È più simile a altre direttive, ad esempio `x:Code` dove l'elemento delimita un intervallo in cui il markup deve essere interpretato come diversa da quella predefinita per il contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="7515e-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="7515e-124">In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni sui tipi di argomento, che viene usate dal parser XAML per determinare quali firma del metodo factory costruttore specifico un `x:Arguments` utilizzo sta provando a fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="7515e-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="7515e-125">`x:Arguments` per un elemento dell'oggetto in fase di costruzione devono precedere eventuali altri elementi proprietà, contenuto, il testo interno o stringhe di inizializzazione dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="7515e-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="7515e-126">Gli elementi oggetto all'interno di `x:Arguments` possono includere attributi e le stringhe di inizializzazione, come consentito dal tipo XAML e il relativo metodo di costruttore o factory sottostante.</span><span class="sxs-lookup"><span data-stu-id="7515e-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="7515e-127">Per l'oggetto o gli argomenti, è possibile specificare tipi XAML personalizzati o XAML che non rientrano in caso contrario, lo spazio dei nomi XAML predefinito facendo riferimento a mapping del prefisso stabiliti.</span><span class="sxs-lookup"><span data-stu-id="7515e-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="7515e-128">Processori XAML usano le linee guida seguenti per determinare come gli argomenti specificati nel `x:Arguments` deve essere utilizzato per costruire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7515e-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="7515e-129">Se `x:FactoryMethod` viene specificato, viene confrontata con le informazioni sull'oggetto specificato `x:FactoryMethod` (si noti che il valore di `x:FactoryMethod` è il nome del metodo e il metodo denominato può avere gli overload.</span><span class="sxs-lookup"><span data-stu-id="7515e-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="7515e-130">Se `x:FactoryMethod` non viene specificato, le informazioni viene confrontato con il set di tutti gli overload di un costruttore pubblico dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7515e-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="7515e-131">Logica di elaborazione XAML quindi confronta il numero di parametri e seleziona l'overload con il grado corrispondente.</span><span class="sxs-lookup"><span data-stu-id="7515e-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="7515e-132">Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi dei parametri in base ai tipi XAML degli elementi oggetto specificati.</span><span class="sxs-lookup"><span data-stu-id="7515e-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="7515e-133">Se non esiste ancora più di una corrispondenza, il comportamento del processore XAML è definito.</span><span class="sxs-lookup"><span data-stu-id="7515e-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="7515e-134">Se un `x:FactoryMethod` è specificato, ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7515e-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="7515e-135">Un utilizzo dell'attributo XAML `<x:Arguments>string</x:Arguments>` sia tecnicamente possibile.</span><span class="sxs-lookup"><span data-stu-id="7515e-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="7515e-136">Tuttavia, ciò non fornisce alcuna funzionalità oltre a ciò che avveniva in caso contrario, tramite i convertitori di tipi e il testo di inizializzazione e usando questa sintassi non è l'intenzione di progettazione di funzionalità del metodo factory di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="7515e-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="7515e-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="7515e-137">Examples</span></span>  
 <span data-ttu-id="7515e-138">Nell'esempio seguente illustra un costruttore non predefinito, firma, quindi l'utilizzo XAML di `x:Arguments` che accede alla firma.</span><span class="sxs-lookup"><span data-stu-id="7515e-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="7515e-139">L'esempio seguente mostra una firma di metodo factory di destinazione, quindi l'utilizzo XAML di `x:Arguments` che accede alla firma.</span><span class="sxs-lookup"><span data-stu-id="7515e-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7515e-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7515e-140">See also</span></span>
- [<span data-ttu-id="7515e-141">Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7515e-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](defining-custom-types-for-use-with-net-framework-xaml-services.md)
- [<span data-ttu-id="7515e-142">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7515e-142">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
