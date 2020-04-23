---
title: Direttiva x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 5e864b6f5d664b079036a5d915e2f6f81b83639f
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "82071535"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="e0d45-102">Direttiva x:FactoryMethod</span><span class="sxs-lookup"><span data-stu-id="e0d45-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="e0d45-103">Specifica un metodo diverso da un costruttore che un processore XAML deve utilizzare per inizializzare un oggetto dopo la risoluzione del tipo di supporto.</span><span class="sxs-lookup"><span data-stu-id="e0d45-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="e0d45-104">Utilizzo degli attributi XAML, senza x:ArgumentsXAML Attribute Usage, no x:Arguments</span><span class="sxs-lookup"><span data-stu-id="e0d45-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="e0d45-105">Utilizzo degli attributi XAML, x:Arguments come elemento/iXAML Attribute Usage, x:Arguments as Element(s)</span><span class="sxs-lookup"><span data-stu-id="e0d45-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```xaml  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e0d45-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="e0d45-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="e0d45-107">Nome del metodo stringa di un metodo chiamato dai `object`processori XAML per inizializzare l'istanza specificata come .</span><span class="sxs-lookup"><span data-stu-id="e0d45-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="e0d45-108">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="e0d45-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="e0d45-109">Uno o più elementi oggetto per gli oggetti che specificano i parametri del metodo factory.</span><span class="sxs-lookup"><span data-stu-id="e0d45-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="e0d45-110">L'ordine è significativo; indica l'ordine in cui gli argomenti devono essere passati al metodo factory.</span><span class="sxs-lookup"><span data-stu-id="e0d45-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0d45-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="e0d45-111">Remarks</span></span>  
 <span data-ttu-id="e0d45-112">Se `methodname` è un metodo di istanza, non può essere qualificato.</span><span class="sxs-lookup"><span data-stu-id="e0d45-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="e0d45-113">Sono supportati i metodi statici come metodi factory.</span><span class="sxs-lookup"><span data-stu-id="e0d45-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="e0d45-114">Se `methodname` è un `methodname` metodo statico, `typeName.methodName` viene `typeName` fornito come combinazione, in cui denomina la classe che definisce il metodo factory statico.</span><span class="sxs-lookup"><span data-stu-id="e0d45-114">If `methodname` is a static method, `methodname` is provided as a `typeName.methodName` combination, where `typeName` names the class that defines the static factory method.</span></span> <span data-ttu-id="e0d45-115">`typeName`può essere qualificato con prefisso se si fa riferimento a un tipo in un xmlns mappato.</span><span class="sxs-lookup"><span data-stu-id="e0d45-115">`typeName` can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="e0d45-116">`typeName`può essere di `typeof(object)`tipo diverso da .</span><span class="sxs-lookup"><span data-stu-id="e0d45-116">`typeName` can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="e0d45-117">Il metodo factory deve essere un metodo pubblico dichiarato del tipo che supporta l'elemento oggetto pertinente.</span><span class="sxs-lookup"><span data-stu-id="e0d45-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="e0d45-118">Il metodo factory deve restituire un'istanza assegnabile all'oggetto pertinente.</span><span class="sxs-lookup"><span data-stu-id="e0d45-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="e0d45-119">I metodi factory non devono mai restituire null.</span><span class="sxs-lookup"><span data-stu-id="e0d45-119">Factory methods should never return null.</span></span>  
  
 <span data-ttu-id="e0d45-120">`x:Arguments`opera su un principio di migliore corrispondenza per le firme dei metodi factory.</span><span class="sxs-lookup"><span data-stu-id="e0d45-120">`x:Arguments` operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="e0d45-121">La corrispondenza valuta prima il conteggio dei parametri.</span><span class="sxs-lookup"><span data-stu-id="e0d45-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="e0d45-122">Se esiste più di una corrispondenza possibile per un conteggio di parametri, il tipo di parametro viene quindi valutato e viene determinata la corrispondenza migliore.</span><span class="sxs-lookup"><span data-stu-id="e0d45-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="e0d45-123">Se c'è ancora ambiguità dopo questa fase di valutazione, il comportamento del processore XAML non è definito.</span><span class="sxs-lookup"><span data-stu-id="e0d45-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="e0d45-124">L'utilizzo `x:FactoryMethod` dell'elemento non è l'utilizzo dell'elemento proprietà nel senso tipico, perché il markup della direttiva non fa riferimento al tipo dell'elemento oggetto contenitore.</span><span class="sxs-lookup"><span data-stu-id="e0d45-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="e0d45-125">Si prevede che l'utilizzo degli elementi sia meno comune dell'utilizzo degli attributi.</span><span class="sxs-lookup"><span data-stu-id="e0d45-125">It is expected that element usage is less common than attribute usage.</span></span> <span data-ttu-id="e0d45-126">`x:Arguments`(utilizzo di attributi o elementi) `x:FactoryMethod` può essere utilizzato insieme all'utilizzo dell'elemento, ma ciò non è illustrato in modo specifico nelle sezioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e0d45-126">`x:Arguments` (either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 <span data-ttu-id="e0d45-127">`x:FactoryMethod`come elemento deve precedere qualsiasi altro elemento `x:Arguments` proprietà, deve precedere qualsiasi fornito anche come elementi e deve precedere qualsiasi testo di contenuto/testo interno/inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="e0d45-127">`x:FactoryMethod` as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0d45-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e0d45-128">See also</span></span>

- [<span data-ttu-id="e0d45-129">Direttiva x:Arguments</span><span class="sxs-lookup"><span data-stu-id="e0d45-129">x:Arguments Directive</span></span>](xarguments-directive.md)
