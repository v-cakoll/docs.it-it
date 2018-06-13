---
title: Direttiva x:Arguments
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: e0e7f380ec176e80d2422878a2e676d64985d660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564878"
---
# <a name="xarguments-directive"></a><span data-ttu-id="6b1c9-102">Direttiva x:Arguments</span><span class="sxs-lookup"><span data-stu-id="6b1c9-102">x:Arguments Directive</span></span>
<span data-ttu-id="6b1c9-103">Argomenti di costruzione di pacchetti per una dichiarazione di elemento oggetto costruttore non predefinito in XAML o per una dichiarazione di oggetto del metodo factory.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-103">Packages construction arguments for a non-default constructor object element declaration in XAML, or for a factory method object declaration.</span></span>  
  
## <a name="xaml-element-usage-nondefault-constructor"></a><span data-ttu-id="6b1c9-104">Utilizzo dell'elemento XAML (costruttore non predefinito)</span><span class="sxs-lookup"><span data-stu-id="6b1c9-104">XAML Element Usage (Nondefault constructor)</span></span>  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a><span data-ttu-id="6b1c9-105">Utilizzo dell'elemento XAML (metodo factory)</span><span class="sxs-lookup"><span data-stu-id="6b1c9-105">XAML Element Usage (factory method)</span></span>  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6b1c9-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="6b1c9-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|<span data-ttu-id="6b1c9-107">Uno o più elementi di oggetti che specificano gli argomenti da passare per il backup non predefinito costruttore o metodo factory.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-107">One or more object elements that specify arguments to be passed to the backing non-default constructor or factory method.</span></span><br /><br /> <span data-ttu-id="6b1c9-108">Utilizzo tipico consiste nell'utilizzare il testo di inizializzazione all'interno gli elementi oggetto per specificare i valori di argomento effettivo.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-108">Typical usage is to use initialization text within the object elements to specify the actual argument values.</span></span> <span data-ttu-id="6b1c9-109">Vedere la sezione esempi.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-109">See Examples section.</span></span><br /><br /> <span data-ttu-id="6b1c9-110">L'ordine degli elementi è significativo.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-110">The order of the elements is significant.</span></span> <span data-ttu-id="6b1c9-111">I tipi XAML in ordine necessario corrispondono ai tipi e digitare ordine backup costruttore o overload del metodo.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-111">The XAML types in order must match the types and type order of the backing constructor or factory method overload.</span></span>|  
|`methodName`|<span data-ttu-id="6b1c9-112">Il nome del metodo factory che deve elaborare tutti `x:Arguments` argomenti.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-112">The name of the factory method that should process any `x:Arguments` arguments.</span></span>|  
  
## <a name="dependencies"></a><span data-ttu-id="6b1c9-113">Dipendenze</span><span class="sxs-lookup"><span data-stu-id="6b1c9-113">Dependencies</span></span>  
 <span data-ttu-id="6b1c9-114">`x:FactoryMethod` può modificare l'ambito e il comportamento in `x:Arguments` si applica.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-114">`x:FactoryMethod` can modify the scope and behavior where `x:Arguments` applies.</span></span>  
  
 <span data-ttu-id="6b1c9-115">Se non `x:FactoryMethod` è specificato, `x:Arguments` si applica a alternative (non-impostazione predefinita) firme dei costruttori di backup.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-115">If no `x:FactoryMethod` is specified, `x:Arguments` applies to alternate (non-default) signatures of the backing constructors.</span></span>  
  
 <span data-ttu-id="6b1c9-116">Se `x:FactoryMethod` è specificato, `x:Arguments` si applica a un overload del metodo denominato.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-116">If `x:FactoryMethod` is specified, `x:Arguments` applies to an overload of the named method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b1c9-117">Note</span><span class="sxs-lookup"><span data-stu-id="6b1c9-117">Remarks</span></span>  
 <span data-ttu-id="6b1c9-118">XAML 2006 supporta l'inizializzazione non predefinita, tramite il testo di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-118">XAML 2006 can support non-default initialization through initialization text.</span></span> <span data-ttu-id="6b1c9-119">Tuttavia, l'applicazione di una tecnica di costruzione di testo di inizializzazione è limitato.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-119">However, the practical application of an initialization text construction technique is limited.</span></span> <span data-ttu-id="6b1c9-120">Testo di inizializzazione viene considerato come una stringa di testo singola. Pertanto, solo aggiunge funzionalità per l'inizializzazione di un singolo parametro a meno che non è definito un convertitore di tipi per il comportamento di costruzione che consente di analizzare gli elementi di informazioni personalizzate e delimitatori personalizzati dalla stringa.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-120">Initialization text is treated as a single text string; therefore, it only adds capability for a single parameter initialization unless a type converter is defined for the construction behavior that can parse custom information items and custom delimiters from the string.</span></span> <span data-ttu-id="6b1c9-121">Inoltre, la stringa di testo alla logica dell'oggetto è potenzialmente convertitore di tipi predefiniti nativo del parser XAML specificato per le primitive diverso da una stringa true.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-121">Also, the text string to object logic is potentially a given XAML parser's native default type converter for handling primitives other than a true string.</span></span>  
  
 <span data-ttu-id="6b1c9-122">Il `x:Arguments` utilizzo di XAML non è utilizzo dell'elemento proprietà in senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-122">The `x:Arguments` XAML usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="6b1c9-123">È più simile alle altre direttive, ad esempio `x:Code` in cui l'elemento delimita un intervallo in cui il markup deve essere interpretato come diverso da quello predefinito per il contenuto figlio.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-123">It is more akin to other directives such as `x:Code` where the element demarks a range in which the markup should be interpreted as other than the default for child contents.</span></span> <span data-ttu-id="6b1c9-124">In questo caso, il tipo XAML di ogni elemento oggetto comunica informazioni relative ai tipi di argomenti, che viene usate dal parser XAML per determinare quali firma del metodo factory costruttore specifico un `x:Arguments` utilizzo sta tentando di fare riferimento.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-124">In this case, the XAML type of each object element communicates information about the argument types, which is used by XAML parsers to determine which specific constructor factory method signature an `x:Arguments` usage is attempting to reference.</span></span>  
  
 <span data-ttu-id="6b1c9-125">`x:Arguments` per un elemento oggetto in fase di costruzione devono precedere eventuali altri elementi di proprietà, contenuto, testo interno o stringhe di inizializzazione dell'elemento oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-125">`x:Arguments` for an object element being constructed must precede any other property elements, content, inner text, or initialization strings of the object element.</span></span> <span data-ttu-id="6b1c9-126">Gli elementi oggetto all'interno di `x:Arguments` possono includere attributi e stringhe di inizializzazione, come consentito dal tipo XAML e il relativo metodo di costruttore o di backup.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-126">The object elements within `x:Arguments` can include attributes and initialization strings, as permitted by that XAML type and its backing constructor or factory method.</span></span> <span data-ttu-id="6b1c9-127">Per l'oggetto o gli argomenti, è possibile specificare tipi XAML personalizzati o tipi XAML che non rientrano in caso contrario lo spazio dei nomi XAML predefinito facendo riferimento a mapping del prefisso stabilita.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-127">For either the object or the arguments, you can specify custom XAML types or XAML types that are otherwise outside the default XAML namespace by referencing established prefix mappings.</span></span>  
  
 <span data-ttu-id="6b1c9-128">Processori XAML utilizzano le linee guida seguenti per determinare la modalità con cui gli argomenti specificati nella `x:Arguments` deve essere utilizzato per costruire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-128">XAML processors use the following guidelines to determine how the arguments specified in `x:Arguments` should be used to construct an object.</span></span> <span data-ttu-id="6b1c9-129">Se `x:FactoryMethod` è specificato, le informazioni vengono confrontate specificata `x:FactoryMethod` (si noti che il valore di `x:FactoryMethod` è il nome del metodo e il metodo denominato può disporre di overload.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-129">If `x:FactoryMethod` is specified, information is compared to the specified `x:FactoryMethod` (note that the value of `x:FactoryMethod` is the method name, and the named method can have overloads.</span></span> <span data-ttu-id="6b1c9-130">Se `x:FactoryMethod` non viene specificato, le informazioni vengono confrontate al set di tutti gli overload di costruttore pubblico dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-130">If `x:FactoryMethod` is not specified, information is compared to the set of all public constructor overloads of the object.</span></span> <span data-ttu-id="6b1c9-131">Logica di elaborazione XAML quindi confronta il numero di parametri e seleziona l'overload con grado corrispondente.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-131">XAML processing logic then compares the number of parameters and selects the overload with matching arity.</span></span> <span data-ttu-id="6b1c9-132">Se è presente più di una corrispondenza, il processore XAML deve confrontare i tipi dei parametri in base ai tipi di sintassi XAML per gli elementi oggetto fornito.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-132">If there is more than one match, the XAML processor should compare the types of the parameters based on the XAML types of the provided object elements.</span></span> <span data-ttu-id="6b1c9-133">Se è ancora più corrispondenze, non è definito il comportamento del processore XAML.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-133">If there is still more than one match, the XAML processor behavior is undefined.</span></span> <span data-ttu-id="6b1c9-134">Se un `x:FactoryMethod` è specificato, ma il metodo non può essere risolto, un processore XAML deve generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-134">If a `x:FactoryMethod` is specified but the method cannot be resolved, a XAML processor should throw an exception.</span></span>  
  
 <span data-ttu-id="6b1c9-135">Attributo XAML `<x:Arguments>string</x:Arguments>` è tecnicamente possibile.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-135">A XAML attribute usage `<x:Arguments>string</x:Arguments>` is technically possible.</span></span> <span data-ttu-id="6b1c9-136">Tuttavia, ciò non fornisce alcuna funzionalità oltre a ciò che potrebbe avvenire in caso contrario tramite i convertitori di tipi e di testo di inizializzazione e utilizzando questa sintassi, non è l'intenzione di progettazione delle funzionalità di metodo factory di XAML 2009.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-136">However, this provides no capabilities beyond what could be done otherwise through initialization text and type converters, and using this syntax is not the design intention of the XAML 2009 factory method features.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6b1c9-137">Esempi</span><span class="sxs-lookup"><span data-stu-id="6b1c9-137">Examples</span></span>  
 <span data-ttu-id="6b1c9-138">L'esempio seguente mostra un costruttore non predefinito, firma, quindi l'utilizzo di XAML `x:Arguments` che accede alla firma.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-138">The following example shows a non-default constructor signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
 <span data-ttu-id="6b1c9-139">L'esempio seguente mostra una firma del metodo factory di destinazione, quindi l'utilizzo di XAML `x:Arguments` che accede alla firma.</span><span class="sxs-lookup"><span data-stu-id="6b1c9-139">The following example shows a target factory method signature, then the XAML usage of `x:Arguments` that accesses that signature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6b1c9-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b1c9-140">See Also</span></span>  
 [<span data-ttu-id="6b1c9-141">Definizione di tipi personalizzati da utilizzare con i servizi XAML di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6b1c9-141">Defining Custom Types for Use with .NET Framework XAML Services</span></span>](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [<span data-ttu-id="6b1c9-142">Cenni preliminari su XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="6b1c9-142">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
