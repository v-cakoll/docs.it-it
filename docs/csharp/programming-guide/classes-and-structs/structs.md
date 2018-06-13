---
title: Struct (Guida per programmatori C#)
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: ffb5b8da6c72056620cf890f38af4e7a8116ab3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322988"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="98418-102">Struct (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="98418-102">Structs (C# Programming Guide)</span></span>
<span data-ttu-id="98418-103">Per la definizione degli struct viene usata la parola chiave [struct](../../../csharp/language-reference/keywords/struct.md), ad esempio:</span><span class="sxs-lookup"><span data-stu-id="98418-103">Structs are defined by using the [struct](../../../csharp/language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/structs_1.cs)]  
  
 <span data-ttu-id="98418-104">Gli struct condividono la maggior parte della sintassi delle classi, anche sono più limitati rispetto alle classi:</span><span class="sxs-lookup"><span data-stu-id="98418-104">Structs share most of the same syntax as classes, although structs are more limited than classes:</span></span>  
  
-   <span data-ttu-id="98418-105">All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.</span><span class="sxs-lookup"><span data-stu-id="98418-105">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
  
-   <span data-ttu-id="98418-106">Uno struct non può dichiarare un finalizzatore o un costruttore, ovvero un costruttore senza parametri, predefinito.</span><span class="sxs-lookup"><span data-stu-id="98418-106">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
  
-   <span data-ttu-id="98418-107">Gli struct vengono copiati su assegnazione.</span><span class="sxs-lookup"><span data-stu-id="98418-107">Structs are copied on assignment.</span></span> <span data-ttu-id="98418-108">Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale.</span><span class="sxs-lookup"><span data-stu-id="98418-108">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="98418-109">È importante ricordare questo aspetto quando si lavora con raccolte di tipi valore come Dictionary\<string, myStruct>.</span><span class="sxs-lookup"><span data-stu-id="98418-109">This is important to remember when working with collections of value types such as Dictionary\<string, myStruct>.</span></span>  
  
-   <span data-ttu-id="98418-110">Gli struct sono tipi valore e le classi sono tipi di riferimento.</span><span class="sxs-lookup"><span data-stu-id="98418-110">Structs are value types and classes are reference types.</span></span>  
  
-   <span data-ttu-id="98418-111">A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="98418-111">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
  
-   <span data-ttu-id="98418-112">Gli struct possono dichiarare costruttori con parametri.</span><span class="sxs-lookup"><span data-stu-id="98418-112">Structs can declare constructors that have parameters.</span></span>  
  
-   <span data-ttu-id="98418-113">Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe.</span><span class="sxs-lookup"><span data-stu-id="98418-113">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="98418-114">Tutti gli struct ereditano direttamente da `System.ValueType`, che eredita da `System.Object`.</span><span class="sxs-lookup"><span data-stu-id="98418-114">All structs inherit directly from `System.ValueType`, which inherits from `System.Object`.</span></span>  
  
-   <span data-ttu-id="98418-115">Uno struct può implementare le interfacce.</span><span class="sxs-lookup"><span data-stu-id="98418-115">A struct can implement interfaces.</span></span>  
  
-   <span data-ttu-id="98418-116">Uno struct può essere usato come tipo nullable e può ricevere l'assegnazione di un valore Null.</span><span class="sxs-lookup"><span data-stu-id="98418-116">A struct can be used as a nullable type and can be assigned a null value.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="98418-117">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="98418-117">Related Sections</span></span>  
 <span data-ttu-id="98418-118">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="98418-118">For more information:</span></span>  
  
-   [<span data-ttu-id="98418-119">Uso di struct</span><span class="sxs-lookup"><span data-stu-id="98418-119">Using Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/using-structs.md)  
  
-   [<span data-ttu-id="98418-120">Costruttori</span><span class="sxs-lookup"><span data-stu-id="98418-120">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
  
-   [<span data-ttu-id="98418-121">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="98418-121">Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/index.md)  
  
-   [<span data-ttu-id="98418-122">Procedura: Differenza tra il passaggio di uno struct e il passaggio del riferimento a una classe a un metodo</span><span class="sxs-lookup"><span data-stu-id="98418-122">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)  
  
-   [<span data-ttu-id="98418-123">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="98418-123">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
## <a name="see-also"></a><span data-ttu-id="98418-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="98418-124">See Also</span></span>  
 [<span data-ttu-id="98418-125">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="98418-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="98418-126">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="98418-126">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="98418-127">Classi</span><span class="sxs-lookup"><span data-stu-id="98418-127">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)
