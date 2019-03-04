---
title: Struct - Guida per programmatori C#
ms.custom: seodec18
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, structs
- structs [C#]
ms.assetid: b7cf4ff2-0eb7-4e5c-93d5-b2196b4f5d89
ms.openlocfilehash: 6c260408b7cdbb7bd55477a57ca879d89c3c0144
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977032"
---
# <a name="structs-c-programming-guide"></a><span data-ttu-id="c17b7-102">Struct (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="c17b7-102">Structs (C# Programming Guide)</span></span>

<span data-ttu-id="c17b7-103">Per la definizione degli struct viene usata la parola chiave [struct](../../language-reference/keywords/struct.md), ad esempio:</span><span class="sxs-lookup"><span data-stu-id="c17b7-103">Structs are defined by using the [struct](../../language-reference/keywords/struct.md) keyword, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#39)]  
  
<span data-ttu-id="c17b7-104">Gli struct condividono la maggior parte della sintassi come classi.</span><span class="sxs-lookup"><span data-stu-id="c17b7-104">Structs share most of the same syntax as classes.</span></span> <span data-ttu-id="c17b7-105">Il nome della struct deve essere un [nome di identificatore](../inside-a-program/identifier-names.md) C# valido.</span><span class="sxs-lookup"><span data-stu-id="c17b7-105">The name of the struct must be a valid C# [identifier name](../inside-a-program/identifier-names.md).</span></span> <span data-ttu-id="c17b7-106">Gli struct sono più limitati rispetto alle classi nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c17b7-106">Structs are more limited than classes in the following ways:</span></span>  
  
- <span data-ttu-id="c17b7-107">All'interno di una dichiarazione di struct, è possibile inizializzare i campi solo se sono stati dichiarati come const o static.</span><span class="sxs-lookup"><span data-stu-id="c17b7-107">Within a struct declaration, fields cannot be initialized unless they are declared as const or static.</span></span>  
- <span data-ttu-id="c17b7-108">Uno struct non può dichiarare un finalizzatore o un costruttore, ovvero un costruttore senza parametri, predefinito.</span><span class="sxs-lookup"><span data-stu-id="c17b7-108">A struct cannot declare a default constructor (a constructor without parameters) or a finalizer.</span></span>  
- <span data-ttu-id="c17b7-109">Gli struct vengono copiati su assegnazione.</span><span class="sxs-lookup"><span data-stu-id="c17b7-109">Structs are copied on assignment.</span></span> <span data-ttu-id="c17b7-110">Quando uno struct viene assegnato a una nuova variabile, tutti i dati vengono copiati e qualsiasi modifica alla nuova copia non modifica i dati nella copia originale.</span><span class="sxs-lookup"><span data-stu-id="c17b7-110">When a struct is assigned to a new variable, all the data is copied, and any modification to the new copy does not change the data for the original copy.</span></span> <span data-ttu-id="c17b7-111">È importante ricordare questo aspetto quando si usano raccolte di tipi valore come `Dictionary<string, myStruct>`.</span><span class="sxs-lookup"><span data-stu-id="c17b7-111">This is important to remember when working with collections of value types such as `Dictionary<string, myStruct>`.</span></span>  
- <span data-ttu-id="c17b7-112">Gli struct sono tipi valore che, a differenza delle classi, sono tipi riferimento.</span><span class="sxs-lookup"><span data-stu-id="c17b7-112">Structs are value types, unlike classes, which are reference types.</span></span>  
- <span data-ttu-id="c17b7-113">A differenza delle classi, è possibile creare istanze di struct senza usare un operatore `new`.</span><span class="sxs-lookup"><span data-stu-id="c17b7-113">Unlike classes, structs can be instantiated without using a `new` operator.</span></span>  
- <span data-ttu-id="c17b7-114">Gli struct possono dichiarare costruttori con parametri.</span><span class="sxs-lookup"><span data-stu-id="c17b7-114">Structs can declare constructors that have parameters.</span></span> 
- <span data-ttu-id="c17b7-115">Uno struct non può ereditare da un altro struct o da una classe e non può essere la base di una classe.</span><span class="sxs-lookup"><span data-stu-id="c17b7-115">A struct cannot inherit from another struct or class, and it cannot be the base of a class.</span></span> <span data-ttu-id="c17b7-116">Tutti gli struct ereditano direttamente da <xref:System.ValueType>, che eredita da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c17b7-116">All structs inherit directly from <xref:System.ValueType>, which inherits from <xref:System.Object>.</span></span>  
- <span data-ttu-id="c17b7-117">Uno struct può implementare le interfacce.</span><span class="sxs-lookup"><span data-stu-id="c17b7-117">A struct can implement interfaces.</span></span> 
- <span data-ttu-id="c17b7-118">Uno struct non può essere `null` e non è possibile assegnare `null` a una variabile struct, a meno che la variabile non sia dichiarata come tipo nullable.</span><span class="sxs-lookup"><span data-stu-id="c17b7-118">A struct cannot be `null`, and a struct variable cannot be assigned `null` unless the variable is declared as a nullable type.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="c17b7-119">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="c17b7-119">Related sections</span></span>  

<span data-ttu-id="c17b7-120">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="c17b7-120">For more information:</span></span>  
  
- [<span data-ttu-id="c17b7-121">Uso di struct</span><span class="sxs-lookup"><span data-stu-id="c17b7-121">Using Structs</span></span>](using-structs.md)
- [<span data-ttu-id="c17b7-122">Costruttori</span><span class="sxs-lookup"><span data-stu-id="c17b7-122">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="c17b7-123">Tipi nullable</span><span class="sxs-lookup"><span data-stu-id="c17b7-123">Nullable Types</span></span>](../nullable-types/index.md)
- [<span data-ttu-id="c17b7-124">Procedura: Differenza tra il passaggio di uno struct e il passaggio del riferimento a una classe a un metodo</span><span class="sxs-lookup"><span data-stu-id="c17b7-124">How to: Know the Difference Between Passing a Struct and Passing a Class Reference to a Method</span></span>](how-to-know-the-difference-passing-a-struct-and-passing-a-class-to-a-method.md)
- [<span data-ttu-id="c17b7-125">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="c17b7-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)

## <a name="see-also"></a><span data-ttu-id="c17b7-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c17b7-126">See also</span></span>

- [<span data-ttu-id="c17b7-127">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c17b7-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c17b7-128">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="c17b7-128">Classes and Structs</span></span>](index.md)
- [<span data-ttu-id="c17b7-129">Classi</span><span class="sxs-lookup"><span data-stu-id="c17b7-129">Classes</span></span>](classes.md)
- [<span data-ttu-id="c17b7-130">Nomi di identificatore</span><span class="sxs-lookup"><span data-stu-id="c17b7-130">Identifier names</span></span>](../inside-a-program/identifier-names.md)
