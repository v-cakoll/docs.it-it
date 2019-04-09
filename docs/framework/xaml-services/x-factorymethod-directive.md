---
title: Direttiva x:FactoryMethod
ms.date: 03/30/2017
helpviewer_keywords:
- XAML. x:FactoryMethod directive [XAML Services]
- FactoryMethod directive in XAML [XAML Services]
- x:FactoryMethod directive [XAML Services]
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
ms.openlocfilehash: 8fff4d62e07bdfd4ecc27d2692c391251afdd6d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190691"
---
# <a name="xfactorymethod-directive"></a><span data-ttu-id="06b18-102">Direttiva x:FactoryMethod</span><span class="sxs-lookup"><span data-stu-id="06b18-102">x:FactoryMethod Directive</span></span>
<span data-ttu-id="06b18-103">Specifica un metodo diverso da un costruttore che un processore XAML deve usare per inizializzare un oggetto dopo aver risolto il relativo tipo sottostante.</span><span class="sxs-lookup"><span data-stu-id="06b18-103">Specifies a method other than a constructor that a XAML processor should use to initialize an object after resolving its backing type.</span></span>  
  
## <a name="xaml-attribute-usage-no-xarguments"></a><span data-ttu-id="06b18-104">Utilizzo dell'attributo XAML, non X:Arguments</span><span class="sxs-lookup"><span data-stu-id="06b18-104">XAML Attribute Usage, no x:Arguments</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## <a name="xaml-attribute-usage-xarguments-as-elements"></a><span data-ttu-id="06b18-105">Utilizzo dell'attributo XAML, X:Arguments come uno o più elementi</span><span class="sxs-lookup"><span data-stu-id="06b18-105">XAML Attribute Usage, x:Arguments as Element(s)</span></span>  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="06b18-106">Valori XAML</span><span class="sxs-lookup"><span data-stu-id="06b18-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`methodname`|<span data-ttu-id="06b18-107">Il nome del metodo di un metodo che chiamano processori XAML per inizializzare l'istanza specificata come stringa `object`.</span><span class="sxs-lookup"><span data-stu-id="06b18-107">The string method name of a method that XAML processors call to initialize the instance specified as `object`.</span></span> <span data-ttu-id="06b18-108">Vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="06b18-108">See Remarks.</span></span>|  
|`oneOrMoreObjectElements`|<span data-ttu-id="06b18-109">Uno o più elementi oggetto per gli oggetti che specificano i parametri del metodo factory.</span><span class="sxs-lookup"><span data-stu-id="06b18-109">One or more object elements for objects that specify factory method parameters.</span></span> <span data-ttu-id="06b18-110">L'ordine è significativo; indica l'ordine in cui gli argomenti devono essere passati al metodo factory.</span><span class="sxs-lookup"><span data-stu-id="06b18-110">Order is significant; it signifies the order in which arguments should be passed to the factory method.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06b18-111">Note</span><span class="sxs-lookup"><span data-stu-id="06b18-111">Remarks</span></span>  
 <span data-ttu-id="06b18-112">Se `methodname` è un metodo di istanza, non può essere qualificato.</span><span class="sxs-lookup"><span data-stu-id="06b18-112">If `methodname` is an instance method, it cannot be qualified.</span></span>  
  
 <span data-ttu-id="06b18-113">Sono supportati i metodi statici come i metodi factory.</span><span class="sxs-lookup"><span data-stu-id="06b18-113">Static methods as factory methods are supported.</span></span> <span data-ttu-id="06b18-114">Se `methodname` è un metodo statico `methodname` fornita come una *nomeTipo*. *methodName* combinazione, in cui *typeName* denomina la classe che definisce il metodo factory statico.</span><span class="sxs-lookup"><span data-stu-id="06b18-114">If `methodname` is a static method, `methodname` is provided as a *typeName*.*methodName* combination, where *typeName* names the class that defines the static factory method.</span></span> <span data-ttu-id="06b18-115">*typeName* può essere qualificato come prefisso se si fa riferimento a un tipo in un xmlns mappato.</span><span class="sxs-lookup"><span data-stu-id="06b18-115">*typeName* can be prefix-qualified if referring to a type in a mapped xmlns.</span></span> <span data-ttu-id="06b18-116">*typeName* può essere un tipo diverso da `typeof(object)`.</span><span class="sxs-lookup"><span data-stu-id="06b18-116">*typeName* can be a different type than `typeof(object)`.</span></span>  
  
 <span data-ttu-id="06b18-117">Il metodo factory deve essere un metodo dichiarato pubblico del tipo che supporta l'elemento oggetto pertinente.</span><span class="sxs-lookup"><span data-stu-id="06b18-117">The factory method must be a declared public method of the type that backs the relevant object element.</span></span>  
  
 <span data-ttu-id="06b18-118">Il metodo factory deve restituire un'istanza che può essere assegnata all'oggetto pertinente.</span><span class="sxs-lookup"><span data-stu-id="06b18-118">The factory method must return an instance that is assignable to the relevant object.</span></span> <span data-ttu-id="06b18-119">I metodi factory non devono mai restituire null.</span><span class="sxs-lookup"><span data-stu-id="06b18-119">Factory methods should never return null.</span></span>  
  
 `x:Arguments` <span data-ttu-id="06b18-120">opera su un principio di corrispondenza migliore per le firme dei metodi factory.</span><span class="sxs-lookup"><span data-stu-id="06b18-120">operates on a principle of best match for signatures of factory methods.</span></span> <span data-ttu-id="06b18-121">Corrispondenza valuta innanzitutto il numero dei parametri.</span><span class="sxs-lookup"><span data-stu-id="06b18-121">Matching evaluates the parameter count first.</span></span> <span data-ttu-id="06b18-122">Se è presente più di una corrispondenza possibile per un numero di parametri, tipo di parametro viene quindi valutata e la migliore corrispondenza viene determinata.</span><span class="sxs-lookup"><span data-stu-id="06b18-122">If there is more than one possible match for a parameter count, parameter type is then evaluated and best match is determined.</span></span> <span data-ttu-id="06b18-123">Se c'è ancora ambiguità dopo questa fase della valutazione, il comportamento del processore XAML è definito.</span><span class="sxs-lookup"><span data-stu-id="06b18-123">If there is still ambiguity after this phase of evaluation, XAML processor behavior is undefined.</span></span>  
  
 <span data-ttu-id="06b18-124">Il `x:FactoryMethod` utilizzo dell'elemento non utilizzo dell'elemento di proprietà nel senso tradizionale, perché il markup della direttiva non fa riferimento il tipo dell'elemento oggetto che lo contiene.</span><span class="sxs-lookup"><span data-stu-id="06b18-124">The `x:FactoryMethod` element usage is not property element usage in the typical sense, because the directive markup does not reference the containing object element's type.</span></span> <span data-ttu-id="06b18-125">È previsto che l'utilizzo elemento è meno comune rispetto all'utilizzo dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="06b18-125">It is expected that element usage is less common than attribute usage.</span></span> `x:Arguments` <span data-ttu-id="06b18-126">(utilizzo di attributo o elemento) può essere utilizzato insieme a `x:FactoryMethod` utilizzo dell'elemento, ma questo non è specificamente illustrato nelle sezioni dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="06b18-126">(either attribute or element usage) can be used along with `x:FactoryMethod` element usage, but this is not specifically shown in the Usage sections.</span></span>  
  
 `x:FactoryMethod` <span data-ttu-id="06b18-127">come un elemento deve precedere qualsiasi altro elemento proprietà, devono precedere qualsiasi `x:Arguments` anche fornita come elementi e devono precedere qualsiasi testo contenuto/interno. il testo di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="06b18-127">as an element must precede any other property elements, must precede any `x:Arguments` also provided as elements, and must precede any content/inner text/initialization text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06b18-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06b18-128">See also</span></span>

- [<span data-ttu-id="06b18-129">Direttiva x:Arguments</span><span class="sxs-lookup"><span data-stu-id="06b18-129">x:Arguments Directive</span></span>](x-arguments-directive.md)
