---
title: get - Riferimenti per C#
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: d6c0452a7890a6ade480054115c1383199a3f91c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713499"
---
# <a name="get-c-reference"></a><span data-ttu-id="b0b78-102">get (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b0b78-102">get (C# Reference)</span></span>

<span data-ttu-id="b0b78-103">La parola chiave `get` definisce un metodo *funzione di accesso* in una proprietà o indicizzatore che restituisce il valore della proprietà o l'elemento dell'indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="b0b78-103">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="b0b78-104">Per altre informazioni, vedere [Proprietà](../../programming-guide/classes-and-structs/properties.md), [Proprietà implementate automaticamente](../../programming-guide/classes-and-structs/auto-implemented-properties.md) e [Indicizzatori](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b0b78-104">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="b0b78-105">L'esempio seguente definisce le funzioni di accesso `get` e `set` per una proprietà denominata `Seconds`.</span><span class="sxs-lookup"><span data-stu-id="b0b78-105">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="b0b78-106">Usa il campo privato denominato `_seconds` per portare in secondo piano il valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b0b78-106">It uses a private field named `_seconds` to back the property value.</span></span>  
 
 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="b0b78-107">Spesso la funzione di accesso `get` è costituita da una singola istruzione che restituisce un valore, come nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="b0b78-107">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="b0b78-108">A partire da C# 7.0, è possibile implementare la funzione di accesso `get` come membro con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="b0b78-108">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="b0b78-109">L'esempio seguente implementa entrambe le funzioni di accesso `get` e `set` come membri con corpo di espressione.</span><span class="sxs-lookup"><span data-stu-id="b0b78-109">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
 
<span data-ttu-id="b0b78-110">Per i casi semplici in cui le funzioni di accesso `get` e `set` di una proprietà non eseguono operazioni diverse dall'impostazione o recupero di un valore in un campo sottostante, è possibile sfruttare il supporto del compilatore C# per le proprietà implementate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0b78-110">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="b0b78-111">L'esempio seguente implementa `Hours` come una proprietà implementata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0b78-111">The following example implements `Hours` as an auto-implemented property.</span></span> 
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b0b78-112">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b0b78-112">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b0b78-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0b78-113">See also</span></span>

- [<span data-ttu-id="b0b78-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="b0b78-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b0b78-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b0b78-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b0b78-116">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="b0b78-116">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="b0b78-117">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b0b78-117">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
