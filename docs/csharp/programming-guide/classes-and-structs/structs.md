---
title: Struct - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 945d4b060dd9d08f6f16013b27980f66e804ad45
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73739237"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="bbd86-102">Struct (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="bbd86-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="bbd86-103">Per la definizione degli struct viene usata la parola chiave [struct](../../language-reference/keywords/struct.md), ad esempio:</span><span class="sxs-lookup"><span data-stu-id="bbd86-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="bbd86-104">Gli struct condividono la maggior parte della sintassi come classi.</span><span class="sxs-lookup"><span data-stu-id="bbd86-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="bbd86-105">Il nome della struct deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.</span><span class="sxs-lookup"><span data-stu-id="bbd86-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="bbd86-106">Gli struct sono più limitati rispetto alle classi nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbd86-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="bbd86-107">All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.</span><span class="sxs-lookup"><span data-stu-id="bbd86-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="bbd86-108">Uno struct non può dichiarare un costruttore senza parametri o un finalizzatore.</span><span class="sxs-lookup"><span data-stu-id="bbd86-108">A struct cannot declare a parameterless constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="bbd86-109">Gli struct vengono copiati su assegnazione.</span><span class="sxs-lookup"><span data-stu-id="bbd86-109">Structs are copied on assignment.</span></span> <span data-ttu-id="bbd86-110">Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale.</span><span class="sxs-lookup"><span data-stu-id="bbd86-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="bbd86-111">È importante ricordare questo aspetto quando si usano raccolte di tipi valore come `Dictionary<string, myStruct>`.</span><span class="sxs-lookup"><span data-stu-id="bbd86-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="bbd86-112">Gli struct sono tipi valore che, a differenza delle classi, sono tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="bbd86-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="bbd86-113">A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="bbd86-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="bbd86-114">Gli struct possono dichiarare costruttori con parametri.</span><span class="sxs-lookup"><span data-stu-id="bbd86-114">Structs can declare constructors that have parameters.</span></span>
- <span data-ttu-id="bbd86-115">Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe.</span><span class="sxs-lookup"><span data-stu-id="bbd86-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="bbd86-116">Tutti gli struct ereditano direttamente da <xref:System.ValueType>, che eredita da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="bbd86-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="bbd86-117">Uno struct può implementare le interfacce.</span><span class="sxs-lookup"><span data-stu-id="bbd86-117">A struct can implement interfaces.</span></span>
- <span data-ttu-id="bbd86-118">Uno struct non può essere `null`e non è possibile assegnare una variabile struct `null` a meno che la variabile non sia dichiarata come tipo di valore Nullable.</span><span class="sxs-lookup"><span data-stu-id="bbd86-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable value type.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bbd86-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbd86-119">See also</span></span>

- [<span data-ttu-id="bbd86-120">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="bbd86-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="bbd86-121">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="bbd86-121">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="bbd86-122">Classi</span><span class="sxs-lookup"><span data-stu-id="bbd86-122">Classes</span></span>](classes.md)
- [<span data-ttu-id="bbd86-123">Tipi valore nullable</span><span class="sxs-lookup"><span data-stu-id="bbd86-123">Nullable value types</span></span>](../../language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="bbd86-124">Nomi di identificatore</span><span class="sxs-lookup"><span data-stu-id="bbd86-124">Identifier names</span></span>](../inside-a-program/identifier-names.md)
- [<span data-ttu-id="bbd86-125">Uso di struct</span><span class="sxs-lookup"><span data-stu-id="bbd86-125">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="bbd86-126">Procedura: Differenza tra il passaggio di uno struct e il passaggio del riferimento a una classe a un metodo</span><span class="sxs-lookup"><span data-stu-id="bbd86-126">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
