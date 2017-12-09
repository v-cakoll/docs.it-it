---
title: Indicizzatori (Guida per programmatori C#)
ms.date: 03/10/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.indexers
helpviewer_keywords:
- indexers [C#]
- C# language, indexers
ms.assetid: 022cd27d-d5e0-4cfe-8b97-dc018cc3355d
caps.latest.revision: "29"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db49a602b83940cab3f87dea17accb92a2be825d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="indexers-c-programming-guide"></a><span data-ttu-id="30008-102">Indicizzatori (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="30008-102">Indexers (C# Programming Guide)</span></span>

<span data-ttu-id="30008-103">Gli indicizzatori consentono di indicizzare le istanze di una classe o struct esattamente come le matrici.</span><span class="sxs-lookup"><span data-stu-id="30008-103">Indexers allow instances of a class or struct to be indexed just like arrays.</span></span> <span data-ttu-id="30008-104">Il valore indicizzato può essere impostato o recuperato senza specificare in modo esplicito un membro di istanza o tipo.</span><span class="sxs-lookup"><span data-stu-id="30008-104">The indexed value can be set or retrieved without explicitly specifying a type or instance member.</span></span> <span data-ttu-id="30008-105">Gli indicizzatori sono analoghi alle [proprietà](../../../csharp/programming-guide/classes-and-structs/properties.md), con la differenza che le relative funzioni di accesso accettano i parametri.</span><span class="sxs-lookup"><span data-stu-id="30008-105">Indexers resemble [properties](../../../csharp/programming-guide/classes-and-structs/properties.md) except that their accessors take parameters.</span></span>  
 
 <span data-ttu-id="30008-106">Nell'esempio seguente viene definita una classe generica con i semplici metodi delle funzioni di accesso [get](../../../csharp/language-reference/keywords/get.md) e [set](../../../csharp/language-reference/keywords/set.md) per assegnare e recuperare i valori.</span><span class="sxs-lookup"><span data-stu-id="30008-106">The following example defines a generic class with simple [get](../../../csharp/language-reference/keywords/get.md) and [set](../../../csharp/language-reference/keywords/set.md) accessor methods to assign and retrieve values.</span></span> <span data-ttu-id="30008-107">La classe `Program` crea un'istanza di questa classe per archiviare le stringhe.</span><span class="sxs-lookup"><span data-stu-id="30008-107">The `Program` class creates an instance of this class for storing strings.</span></span>  
  
 [!code-csharp[indexers#1](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-1.cs)]  
  
> [!NOTE]
>  <span data-ttu-id="30008-108">Per altri esempi, vedere [Sezioni correlate](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span><span class="sxs-lookup"><span data-stu-id="30008-108">For more examples, see [Related Sections](../../../csharp/programming-guide/indexers/index.md#BKMK_RelatedSections).</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="30008-109">Definizioni del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="30008-109">Expression Body Definitions</span></span>  
 
<span data-ttu-id="30008-110">È normale che un indicizzatore ottenga o imposti una funzione di accesso in modo che sia costituita da una singola istruzione che restituisce o imposta un valore.</span><span class="sxs-lookup"><span data-stu-id="30008-110">It is common for an indexer's get or set accessor to consist of a single statement that either returns or sets a value.</span></span> <span data-ttu-id="30008-111">I membri con corpo di espressione offrono una sintassi semplificata per supportare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="30008-111">Expression-bodied members provide a simplified syntax to support this scenario.</span></span> <span data-ttu-id="30008-112">A partire da C# 6 è possibile implementare un indicizzatore di sola lettura come membro con corpo di espressione, come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="30008-112">Starting with C# 6, a read-only indexer can be implemented as an expression-bodied member, as the following example shows.</span></span>

[!code-csharp[indexers#2](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-2.cs)]  

<span data-ttu-id="30008-113">Si noti che `=>` introduce il corpo dell'espressione e che la parola chiave `get` non è usata.</span><span class="sxs-lookup"><span data-stu-id="30008-113">Note that `=>` introduces the expression body, and that the `get` keyword is not used.</span></span> 

<span data-ttu-id="30008-114">A partire da C# 7, le funzioni di accesso get e set possono essere implementate entrambe come membri con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="30008-114">Starting with C# 7, both the get and set accessor can be an implemented as expression-bodied members.</span></span> <span data-ttu-id="30008-115">In questo caso, è necessario usare entrambe le parole chiave `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="30008-115">In this case, both `get` and `set` keywords must be used.</span></span> <span data-ttu-id="30008-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="30008-116">For example:</span></span>

[!code-csharp[indexers#3](../../../../samples/snippets/csharp/programming-guide/indexers/indexer-3.cs)]  
  
## <a name="indexers-overview"></a><span data-ttu-id="30008-117">Panoramica sugli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="30008-117">Indexers Overview</span></span>  
  
-   <span data-ttu-id="30008-118">Gli indicizzatori consentono di indicizzare gli oggetti in modo simile alle matrici.</span><span class="sxs-lookup"><span data-stu-id="30008-118">Indexers enable objects to be indexed in a similar manner to arrays.</span></span>  
  
-   <span data-ttu-id="30008-119">Una funzione di accesso `get` restituisce un valore.</span><span class="sxs-lookup"><span data-stu-id="30008-119">A `get` accessor returns a value.</span></span> <span data-ttu-id="30008-120">Una funzione di accesso `set` assegna un valore.</span><span class="sxs-lookup"><span data-stu-id="30008-120">A `set` accessor assigns a value.</span></span>  
  
-   <span data-ttu-id="30008-121">La parola chiave [this](../../../csharp/language-reference/keywords/this.md) viene usata per definire gli indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="30008-121">The [this](../../../csharp/language-reference/keywords/this.md) keyword is used to define the indexer.</span></span>  
  
-   <span data-ttu-id="30008-122">La parola chiave [value](../../../csharp/language-reference/keywords/value.md) viene usata per definire il valore assegnato dall'indicizzatore `set`.</span><span class="sxs-lookup"><span data-stu-id="30008-122">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` indexer.</span></span>  
  
-   <span data-ttu-id="30008-123">Non è necessario che gli indicizzatori vengano indicizzati da un valore Integer, perché la definizione del meccanismo di ricerca specifico dipende dall'utente.</span><span class="sxs-lookup"><span data-stu-id="30008-123">Indexers do not have to be indexed by an integer value; it is up to you how to define the specific look-up mechanism.</span></span>  
  
-   <span data-ttu-id="30008-124">Gli indicizzatori possono essere sottoposti a overload.</span><span class="sxs-lookup"><span data-stu-id="30008-124">Indexers can be overloaded.</span></span>  
  
-   <span data-ttu-id="30008-125">Gli indicizzatori possono avere più di un parametro formale, ad esempio quando si accede a una matrice bidimensionale.</span><span class="sxs-lookup"><span data-stu-id="30008-125">Indexers can have more than one formal parameter, for example, when accessing a two-dimensional array.</span></span>  
  
##  <a name="BKMK_RelatedSections"></a> <span data-ttu-id="30008-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="30008-126">Related Sections</span></span>  
  
-   [<span data-ttu-id="30008-127">Uso degli indicizzatori</span><span class="sxs-lookup"><span data-stu-id="30008-127">Using Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="30008-128">Indicizzatori nelle interfacce</span><span class="sxs-lookup"><span data-stu-id="30008-128">Indexers in Interfaces</span></span>](../../../csharp/programming-guide/indexers/indexers-in-interfaces.md)  
  
-   [<span data-ttu-id="30008-129">Confronto tra proprietà e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="30008-129">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="30008-130">Limitazione dell'accessibilità delle funzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="30008-130">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="30008-131">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="30008-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="30008-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30008-132">See Also</span></span>  
 [<span data-ttu-id="30008-133">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="30008-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="30008-134">Proprietà</span><span class="sxs-lookup"><span data-stu-id="30008-134">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
