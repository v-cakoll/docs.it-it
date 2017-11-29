---
title: 'Procedura: eseguire il cast sicuro tramite gli operatori as e is (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.assetid: c1176cea-1426-4a44-8570-3eadafa58863
caps.latest.revision: "10"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 733b67408997feb0e518db327e3eedd42f286a99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-safely-cast-by-using-as-and-is-operators-c-programming-guide"></a><span data-ttu-id="db37b-102">Procedura: eseguire il cast sicuro tramite gli operatori as e is (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="db37b-102">How to: Safely Cast by Using as and is Operators (C# Programming Guide)</span></span>
<span data-ttu-id="db37b-103">Poiché gli oggetti sono polimorfici, è possibile che una variabile di un tipo di classe di base contenga un tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="db37b-103">Because objects are polymorphic, it is possible for a variable of a base class type to hold a derived type.</span></span> <span data-ttu-id="db37b-104">Per accedere al metodo del tipo derivato, è necessario eseguire nuovamente il cast del valore al tipo derivato.</span><span class="sxs-lookup"><span data-stu-id="db37b-104">To access the derived type's method, it is necessary to cast the value back to the derived type.</span></span> <span data-ttu-id="db37b-105">Tentare un cast semplice in questi casi comporta tuttavia il rischio di generare un'eccezione <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="db37b-105">However, to attempt a simple cast in these cases creates the risk of throwing an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="db37b-106">Per questo motivo C# fornisce gli operatori [is](../../../csharp/language-reference/keywords/is.md) e [as](../../../csharp/language-reference/keywords/as.md).</span><span class="sxs-lookup"><span data-stu-id="db37b-106">That is why C# provides the [is](../../../csharp/language-reference/keywords/is.md) and [as](../../../csharp/language-reference/keywords/as.md) operators.</span></span> <span data-ttu-id="db37b-107">È possibile usare questi operatori per verificare se un cast riuscirà senza provocare la generazione di un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="db37b-107">You can use these operators to test whether a cast will succeed without causing an exception to be thrown.</span></span> <span data-ttu-id="db37b-108">In generale, l'operatore `as` è più efficiente perché, se è possibile effettuare il cast, ne restituisce il valore.</span><span class="sxs-lookup"><span data-stu-id="db37b-108">In general, the `as` operator is more efficient because it actually returns the cast value if the cast can be made successfully.</span></span> <span data-ttu-id="db37b-109">L'operatore `is` restituisce solo un valore booleano.</span><span class="sxs-lookup"><span data-stu-id="db37b-109">The `is` operator returns only a Boolean value.</span></span> <span data-ttu-id="db37b-110">Si può quindi usare quando si vuole solo determinare il tipo di un oggetto ma non si deve realmente eseguirne il cast.</span><span class="sxs-lookup"><span data-stu-id="db37b-110">It can therefore be used when you just want to determine an object's type but do not have to actually cast it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db37b-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="db37b-111">Example</span></span>  
 <span data-ttu-id="db37b-112">Gli esempi seguenti mostrano come usare gli operatori `is` e `as` per eseguire il cast da un tipo riferimento a un altro senza il rischio di generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="db37b-112">The following examples show how to use the `is` and `as` operators to cast from one reference type to another without the risk of throwing an exception.</span></span> <span data-ttu-id="db37b-113">L'esempio mostra anche come usare l'operatore `as` con i tipi valore nullable.</span><span class="sxs-lookup"><span data-stu-id="db37b-113">The example also shows how to use the `as` operator with nullable value types.</span></span>  
  
 [!code-csharp[csProgGuideTypes#40](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-safely-cast-by-using-as-and-is-operators_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="db37b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="db37b-114">See Also</span></span>  
 [<span data-ttu-id="db37b-115">Tipi</span><span class="sxs-lookup"><span data-stu-id="db37b-115">Types</span></span>](../../../csharp/programming-guide/types/index.md)  
 [<span data-ttu-id="db37b-116">Cast e conversioni di tipi</span><span class="sxs-lookup"><span data-stu-id="db37b-116">Casting and Type Conversions</span></span>](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
 [<span data-ttu-id="db37b-117">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="db37b-117">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)
