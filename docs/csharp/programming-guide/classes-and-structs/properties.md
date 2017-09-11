---
title: "Proprietà (Guida per programmatori C#)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- cs.properties
dev_langs:
- CSharp
helpviewer_keywords:
- properties [C#]
- C# language, properties
ms.assetid: e295a8a2-b357-4ee7-a12e-385a44146fa8
caps.latest.revision: 38
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
ms.openlocfilehash: 127299a617cacee15f87964a12bb3877a2586204
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="properties-c-programming-guide"></a><span data-ttu-id="06e89-102">Proprietà (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="06e89-102">Properties (C# Programming Guide)</span></span>

<span data-ttu-id="06e89-103">Una proprietà è un membro che fornisce un meccanismo flessibile per leggere, scrivere o calcolare il valore di un campo privato.</span><span class="sxs-lookup"><span data-stu-id="06e89-103">A property is a member that provides a flexible mechanism to read, write, or compute the value of a private field.</span></span> <span data-ttu-id="06e89-104">Le proprietà possono essere usate come se fossero membri dati pubblici, ma sono in realtà metodi speciali denominati *funzioni di accesso*.</span><span class="sxs-lookup"><span data-stu-id="06e89-104">Properties can be used as if they are public data members, but they are actually special methods called *accessors*.</span></span> <span data-ttu-id="06e89-105">Questo consente di accedere facilmente ai dati e di alzare di livello la sicurezza e la flessibilità dei metodi.</span><span class="sxs-lookup"><span data-stu-id="06e89-105">This enables data to be accessed easily and still helps promote the safety and flexibility of methods.</span></span>  

## <a name="properties-overview"></a><span data-ttu-id="06e89-106">Panoramica delle proprietà</span><span class="sxs-lookup"><span data-stu-id="06e89-106">Properties overview</span></span>  
  
- <span data-ttu-id="06e89-107">Le proprietà consentono a una classe di esporre un modo pubblico per ottenere e impostare i valori, nascondendo però il codice di implementazione o di verifica.</span><span class="sxs-lookup"><span data-stu-id="06e89-107">Properties enable a class to expose a public way of getting and setting values, while hiding implementation or verification code.</span></span>  
  
- <span data-ttu-id="06e89-108">Una funzione di accesso della proprietà [get](../../../csharp/language-reference/keywords/get.md) viene usata per restituire il valore della proprietà, mentre una funzione di accesso della proprietà [set](../../../csharp/language-reference/keywords/set.md) viene usata per assegnare un nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="06e89-108">A [get](../../../csharp/language-reference/keywords/get.md) property accessor is used to return the property value, and a [set](../../../csharp/language-reference/keywords/set.md) property accessor is used to assign a new value.</span></span> <span data-ttu-id="06e89-109">Queste funzioni di accesso possono avere diversi livelli di accesso.</span><span class="sxs-lookup"><span data-stu-id="06e89-109">These accessors can have different access levels.</span></span> <span data-ttu-id="06e89-110">Per altre informazioni, vedere [Limitazione dell'accessibilità delle funzioni di accesso](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="06e89-110">For more information, see [Restricting Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
- <span data-ttu-id="06e89-111">La parola chiave [value](../../../csharp/language-reference/keywords/value.md) viene usata per definire il valore che deve essere assegnato dalla funzione di accesso `set`.</span><span class="sxs-lookup"><span data-stu-id="06e89-111">The [value](../../../csharp/language-reference/keywords/value.md) keyword is used to define the value being assigned by the `set` accessor.</span></span>  
- <span data-ttu-id="06e89-112">Le proprietà possono essere di *lettura/scrittura* con entrambe le funzione di accesso `get` e `set`, di *sola lettura* con la funzione di accesso `get` e senza la funzione di accesso `set` o di *sola scrittura* con la funzione di accesso `set` e senza la funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="06e89-112">Properties can be *read-write* (they have both a `get` and a `set` accessor), *read-only* (they have a `get` accessor but no `set` accessor), or *write-only* (they have a `set` accessor, but no `get` accessor).</span></span> <span data-ttu-id="06e89-113">Le proprietà di sola scrittura sono rare e vengono in genere usate per limitare l'accesso ai dati sensibili.</span><span class="sxs-lookup"><span data-stu-id="06e89-113">Write-only properties are rare and are most commonly used to restrict access to sensitive data.</span></span>

- <span data-ttu-id="06e89-114">Le proprietà semplici che non richiedono alcun codice di funzione di accesso personalizzata possono essere implementate come definizioni del corpo dell'espressione o come [proprietà implementate automaticamente](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="06e89-114">Simple properties that require no custom accessor code can be implemented either as expression body definitions or as [auto-implemented properties](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md).</span></span>
 
## <a name="properties-with-backing-fields"></a><span data-ttu-id="06e89-115">Proprietà con campi sottostanti</span><span class="sxs-lookup"><span data-stu-id="06e89-115">Properties with backing fields</span></span>

<span data-ttu-id="06e89-116">Un modello di base per l'implementazione di una proprietà prevede l'uso di un campo sottostante privato per l'impostazione e il recupero del valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="06e89-116">One basic pattern for implementing a property involves using a private backing field for setting and retrieving the property value.</span></span> <span data-ttu-id="06e89-117">La funzione di accesso `get` restituisce il valore del campo privato e la funzione di accesso `set` può eseguire una convalida dei dati prima di assegnare un valore al campo privato.</span><span class="sxs-lookup"><span data-stu-id="06e89-117">The `get` accessor returns the value of the private field, and the `set` accessor may perform some data validation before assigning a value to the private field.</span></span> <span data-ttu-id="06e89-118">Entrambe le funzioni di accesso possono anche eseguire una conversione o un calcolo nei dati prima che vengano archiviati o restituiti.</span><span class="sxs-lookup"><span data-stu-id="06e89-118">Both accessors may also perform some conversion or computation on the data before it is stored or returned.</span></span>

<span data-ttu-id="06e89-119">L'esempio seguente illustra il modello.</span><span class="sxs-lookup"><span data-stu-id="06e89-119">The following example illustrates this pattern.</span></span> <span data-ttu-id="06e89-120">Nell'esempio la classe `TimePeriod` rappresenta un intervallo di tempo.</span><span class="sxs-lookup"><span data-stu-id="06e89-120">In this example, the `TimePeriod` class represents an interval of time.</span></span> <span data-ttu-id="06e89-121">Internamente la classe archivia l'intervallo di tempo in secondi in un campo privato denominato `seconds`.</span><span class="sxs-lookup"><span data-stu-id="06e89-121">Internally, the class stores the time interval in seconds in a private field named `seconds`.</span></span> <span data-ttu-id="06e89-122">Una proprietà di lettura/scrittura denominata `Hours` consente al cliente di specificare l'intervallo di tempo in ore.</span><span class="sxs-lookup"><span data-stu-id="06e89-122">A read-write property named `Hours` allows the customer to specify the time interval in hours.</span></span> <span data-ttu-id="06e89-123">Entrambe le funzioni di accesso `get` e `set` eseguono la conversione necessaria tra ore e secondi.</span><span class="sxs-lookup"><span data-stu-id="06e89-123">Both the `get` and the `set` accessors perform the necessary conversion between hours and seconds.</span></span> <span data-ttu-id="06e89-124">Inoltre, la funzione di accesso `set` convalida i dati e genera @System.ArgumentOutOfRangeException se il numero di ore non è valido.</span><span class="sxs-lookup"><span data-stu-id="06e89-124">In addition, the `set` accessor validates the data and throws an @System.ArgumentOutOfRangeException if the number of hours is invalid.</span></span> 
   
 <span data-ttu-id="06e89-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span><span class="sxs-lookup"><span data-stu-id="06e89-125">[!code-cs[Properties#1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-1.cs)]</span></span>  
  
## <a name="expression-body-definitions"></a><span data-ttu-id="06e89-126">Definizioni del corpo dell'espressione</span><span class="sxs-lookup"><span data-stu-id="06e89-126">Expression body definitions</span></span>  

 <span data-ttu-id="06e89-127">Le funzioni di accesso delle proprietà sono spesso costituite da istruzioni a riga singola che assegnano o restituiscono il risultato di un'espressione.</span><span class="sxs-lookup"><span data-stu-id="06e89-127">Property accessors often consist of single-line statements that just assign or return the result of an expression.</span></span> <span data-ttu-id="06e89-128">È possibile implementare queste proprietà come membri con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="06e89-128">You can implement these properties as expression-bodied members.</span></span> <span data-ttu-id="06e89-129">Le definizioni del corpo dell'espressione sono costituite dal simbolo `=>` seguito dall'espressione per l'assegnazione o il recupero dalla proprietà.</span><span class="sxs-lookup"><span data-stu-id="06e89-129">Expression body definitions consist of the `=>` symbol followed by the expression to assign to or retrieve from the property.</span></span>

 <span data-ttu-id="06e89-130">A partire da C# 6, le proprietà di sola lettura possono implementare la funzione di accesso `get` come membro con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="06e89-130">Starting with C# 6, read-only properties can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="06e89-131">In questo caso non viene usata la parola chiave della funzione di accesso `get` né la parola chiave `return`.</span><span class="sxs-lookup"><span data-stu-id="06e89-131">In this case, neither the `get` accessor keyword nor the `return` keyword is used.</span></span> <span data-ttu-id="06e89-132">L'esempio seguente implementa la proprietà `Name` di sola lettura come membro con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="06e89-132">The following example implements the read-only `Name` property as an expression-bodied member.</span></span>

 <span data-ttu-id="06e89-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span><span class="sxs-lookup"><span data-stu-id="06e89-133">[!code-cs[Properties#2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-2.cs)]</span></span>  

 <span data-ttu-id="06e89-134">A partire da C# 7, entrambe le funzioni di accesso `get` e `set` possono essere implementate come membri con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="06e89-134">Starting with C# 7, both the `get` and the `set` accessor can be implemented as expression-bodied members.</span></span> <span data-ttu-id="06e89-135">In questo caso, è necessario che siano presenti le parole chiave `get` e `set`.</span><span class="sxs-lookup"><span data-stu-id="06e89-135">In this case, the `get` and `set` keywords must be present.</span></span> <span data-ttu-id="06e89-136">L'esempio seguente illustra l'uso di definizioni del corpo dell'espressione per entrambe le funzioni di accesso.</span><span class="sxs-lookup"><span data-stu-id="06e89-136">The following example illustrates the use of expression body definitions for both accessors.</span></span> <span data-ttu-id="06e89-137">Si noti che la parola chiave `return` non viene usata con la funzione di accesso `get`.</span><span class="sxs-lookup"><span data-stu-id="06e89-137">Note that the `return` keyword is not used with the `get` accessor.</span></span>
 
  <span data-ttu-id="06e89-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span><span class="sxs-lookup"><span data-stu-id="06e89-138">[!code-cs[Properties#3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-3.cs)]</span></span>  

## <a name="auto-implemented-properties"></a><span data-ttu-id="06e89-139">Proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="06e89-139">Auto-implemented properties</span></span>

<span data-ttu-id="06e89-140">In alcuni casi, le funzioni di accesso `get` e `set` delle proprietà si limitano ad assegnare o a recuperare un valore da un campo sottostante senza includere alcuna logica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="06e89-140">In some cases, property `get` and `set` accessors just assign a value to or retrieve a value from a backing field without including any additional logic.</span></span> <span data-ttu-id="06e89-141">Usando le proprietà implementate automaticamente è possibile semplificare il codice e fare in modo che il compilatore C# specifichi automaticamente in modo trasparente il campo sottostante.</span><span class="sxs-lookup"><span data-stu-id="06e89-141">By using auto-implemented properties, you can simplify your code while having the C# compiler transparently provide the backing field for you.</span></span> 

<span data-ttu-id="06e89-142">Se una proprietà ha entrambe le funzioni di accesso `get` e `set`, entrambe le funzioni devono essere implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="06e89-142">If a property has both a `get` and a `set` accessor, both must be auto-implemented.</span></span> <span data-ttu-id="06e89-143">È possibile definire una proprietà implementata automaticamente usando le parole chiave `get` e `set` senza specificare alcuna implementazione.</span><span class="sxs-lookup"><span data-stu-id="06e89-143">You define an auto-implemented property by using the `get` and `set` keywords without providing any implementation.</span></span> <span data-ttu-id="06e89-144">L'esempio seguente ripete l'esempio precedente, ad eccezione del fatto che `Name` e `Price` sono proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="06e89-144">The following example repeats the previous one, except that `Name` and `Price` are auto-implemented properties.</span></span> <span data-ttu-id="06e89-145">Si noti che l'esempio rimuove anche il costruttore con parametri in modo che gli oggetti `SaleItem` vengano ora inizializzati con una chiamata al costruttore predefinito e un [inizializzatore di oggetto](object-and-collection-initializers.md).</span><span class="sxs-lookup"><span data-stu-id="06e89-145">Note that the example also removes the parameterized constructor, so that `SaleItem` objects are now initialized with a call to the default constructor and an [object initializer](object-and-collection-initializers.md).</span></span>

  <span data-ttu-id="06e89-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span><span class="sxs-lookup"><span data-stu-id="06e89-146">[!code-cs[Properties#4](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/properties-4.cs)]</span></span>  

## <a name="related-sections"></a><span data-ttu-id="06e89-147">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="06e89-147">Related sections</span></span>  
  
-   [<span data-ttu-id="06e89-148">Uso delle proprietà</span><span class="sxs-lookup"><span data-stu-id="06e89-148">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="06e89-149">Proprietà dell'interfaccia</span><span class="sxs-lookup"><span data-stu-id="06e89-149">Interface Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/interface-properties.md)  
  
-   [<span data-ttu-id="06e89-150">Confronto tra proprietà e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="06e89-150">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
  
-   [<span data-ttu-id="06e89-151">Limitazione dell'accessibilità delle funzioni di accesso</span><span class="sxs-lookup"><span data-stu-id="06e89-151">Restricting Accessor Accessibility</span></span>](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md)  
  
-   [<span data-ttu-id="06e89-152">Proprietà implementate automaticamente</span><span class="sxs-lookup"><span data-stu-id="06e89-152">Auto-Implemented Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="06e89-153">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="06e89-153">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="06e89-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06e89-154">See also</span></span>
 <span data-ttu-id="06e89-155">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="06e89-155">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="06e89-156">[Uso delle proprietà](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="06e89-156">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="06e89-157">[Indicizzatori](../../../csharp/programming-guide/indexers/index.md) </span><span class="sxs-lookup"><span data-stu-id="06e89-157">[Indexers](../../../csharp/programming-guide/indexers/index.md) </span></span>  
 <span data-ttu-id="06e89-158">[Parola chiave get](../../../csharp/language-reference/keywords/get.md)  </span><span class="sxs-lookup"><span data-stu-id="06e89-158">[get keyword](../../../csharp/language-reference/keywords/get.md)  </span></span>  
 [<span data-ttu-id="06e89-159">Parola chiave set</span><span class="sxs-lookup"><span data-stu-id="06e89-159">set keyword</span></span>](../../../csharp/language-reference/keywords/set.md)    

