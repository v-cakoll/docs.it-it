---
title: Indicizzatori (Guida per programmatori C#)
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.indexers
dev_langs:
- CSharp
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 784308f3073114cd0c07cf15edae527a2654edec
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="b0b1f-102">Indicizzatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b0b1f-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="b0b1f-103">Gli indicizzatori consentono di indicizzare le istanze di una classe o struct esattamente come le matrici.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="b0b1f-104">Il valore indicizzato può essere impostato o recuperato senza specificare in modo esplicito un membro di istanza o tipo.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="b0b1f-105">Gli indicizzatori sono analoghi alle [proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md), con la differenza che le relative funzioni di accesso accettano i parametri.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="b0b1f-106">Nell'esempio seguente viene definita una classe generica con i semplici metodi delle funzioni di accesso [get](../../../csharp/language-reference/keywords/get.md) e [set](../../../csharp/language-reference/keywords/set.md) per assegnare e recuperare i valori.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="b0b1f-107">La classe `Program` crea un'istanza di questa classe per archiviare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 <span data-ttu-id="b0b1f-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b0b1f-108">[!code-cs[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b0b1f-109">Per altri esempi, vedere [Sezioni correlate](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="b0b1f-109">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="b0b1f-110">Definizioni del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="b0b1f-110">Expression Body Definitions</span></span>  
 
<span data-ttu-id="b0b1f-111">È normale che un indicizzatore ottenga o imposti una funzione di accesso in modo che sia costituita da una singola istruzione che restituisce o imposta un valore.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-111">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="b0b1f-112">I membri con corpo di espressione offrono una sintassi semplificata per supportare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-112">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="b0b1f-113">A partire da C# 6 è possibile implementare un indicizzatore di sola lettura come membro con corpo di espressione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-113">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

<span data-ttu-id="b0b1f-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b0b1f-114">[!code-cs[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]</span></span>  

<span data-ttu-id="b0b1f-115">Si noti che `=>` introduce il corpo dell'espressione e che la parola chiave `get` non è usata.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-115">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="b0b1f-116">A partire da C# 7, le funzioni di accesso get e set possono essere implementate entrambe come membri con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-116">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="b0b1f-117">In questo caso, è necessario usare entrambe le parole chiave `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-117">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="b0b1f-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b0b1f-118">For example:</span></span>

<span data-ttu-id="b0b1f-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b0b1f-119">[!code-cs[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]</span></span>  
  
## <a name="indexers-overview"></a><span data-ttu-id="b0b1f-120">Panoramica sugli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="b0b1f-120">Indexers Overview</span></span>  
  
-   <span data-ttu-id="b0b1f-121">Gli indicizzatori consentono di indicizzare gli oggetti in modo simile alle matrici.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-121">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="b0b1f-122">Una funzione di accesso `get` restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-122">A `get` accessor returns a value.</span></span> <span data-ttu-id="b0b1f-123">Una funzione di accesso `set` assegna un valore.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-123">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="b0b1f-124">La parola chiave [this](../../../csharp/language-reference/keywords/this.md) viene usata per definire gli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-124">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="b0b1f-125">La parola chiave [value](../../../csharp/language-reference/keywords/value.md) viene usata per definire il valore assegnato dall'indicizzatore `set`.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-125">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="b0b1f-126">Non è necessario che gli indicizzatori vengano indicizzati da un valore Integer, perché la definizione del meccanismo di ricerca specifico dipende dall'utente.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-126">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="b0b1f-127">Gli indicizzatori possono essere sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-127">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="b0b1f-128">Gli indicizzatori possono avere più di un parametro formale, ad esempio quando si accede a una matrice bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="b0b1f-128">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <span data-ttu-id="b0b1f-129"><a name="BKMK_RelatedSections"></a> Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="b0b1f-129"><a name="BKMK_RelatedSections"></a> Related Sections</span></span>  
  
-   [<span data-ttu-id="b0b1f-130">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="b0b1f-130">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="b0b1f-131">Indicizzatori nelle interfacce</span><span class="sxs-lookup"><span data-stu-id="b0b1f-131">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="b0b1f-132">Confronto tra proprietà e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="b0b1f-132">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="b0b1f-133">Limitazione dell'accessibilità delle funzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="b0b1f-133">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="b0b1f-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b0b1f-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0b1f-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0b1f-135">See Also</span></span>  
 <span data-ttu-id="b0b1f-136">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b0b1f-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b0b1f-137">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b0b1f-137">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

