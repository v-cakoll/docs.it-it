---
title: Parola chiave const - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- const_CSharpKeyword
- const
helpviewer_keywords:
- const keyword [C#]
ms.assetid: 79eb447c-117b-4418-933f-97c50aa472db
ms.openlocfilehash: 812aeb331b6dd333075d19076a896246ecc5b374
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713683"
---
# <a name="const-c-reference"></a><span data-ttu-id="4c651-102">const (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="4c651-102">const (C# Reference)</span></span>

<span data-ttu-id="4c651-103">Si usa la parola chiave `const` per dichiarare un campo costante o una variabile locale costante.</span><span class="sxs-lookup"><span data-stu-id="4c651-103">You use the `const` keyword to declare a constant field or a constant local.</span></span> <span data-ttu-id="4c651-104">I campi e le variabili locali costanti non sono variabili e non sono quindi modificabili.</span><span class="sxs-lookup"><span data-stu-id="4c651-104">Constant fields and locals aren't variables and may not be modified.</span></span> <span data-ttu-id="4c651-105">Gli elementi costanti possono essere numeri, valori booleani, stringhe o un riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="4c651-105">Constants can be numbers, Boolean values, strings, or a null reference.</span></span> <span data-ttu-id="4c651-106">Non creare una costante per rappresentare informazioni di cui si prevede la modifica in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="4c651-106">Don’t create a constant to represent information that you expect to change at any time.</span></span> <span data-ttu-id="4c651-107">Un campo costante, ad esempio, non deve essere usato per archiviare il prezzo di un servizio, il numero di versione di un prodotto o il nome dell'organizzazione di una società.</span><span class="sxs-lookup"><span data-stu-id="4c651-107">For example, don’t use a constant field to store the price of a service, a product version number, or the brand name of a company.</span></span> <span data-ttu-id="4c651-108">Tali valori potrebbero cambiare nel tempo e, poiché i compilatori propagano le costanti, eventuale altro codice compilato con quelle librerie dovrebbe essere ricompilato per riflettere le modifiche.</span><span class="sxs-lookup"><span data-stu-id="4c651-108">These values can change over time, and because compilers propagate constants, other code compiled with your libraries will have to be recompiled to see the changes.</span></span> <span data-ttu-id="4c651-109">Vedere anche la parola chiave [readonly](./readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4c651-109">See also the [readonly](./readonly.md) keyword.</span></span> <span data-ttu-id="4c651-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c651-110">For example:</span></span>

```csharp
const int X = 0;
public const double GravitationalConstant = 6.673e-11;
private const string ProductName = "Visual C#";
```

## <a name="remarks"></a><span data-ttu-id="4c651-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4c651-111">Remarks</span></span>

<span data-ttu-id="4c651-112">Il tipo di una dichiarazione di costante specifica il tipo di membri introdotti dalla dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="4c651-112">The type of a constant declaration specifies the type of the members that the declaration introduces.</span></span> <span data-ttu-id="4c651-113">L'inizializzatore di una variabile locale costante o di un campo costante deve essere un'espressione costante che possa essere convertita in modo implicito nel tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4c651-113">The initializer of a constant local or a constant field must be a constant expression that can be implicitly converted to the target type.</span></span>

<span data-ttu-id="4c651-114">Un'espressione di costanti è un'espressione che può essere valutata interamente in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="4c651-114">A constant expression is an expression that can be fully evaluated at compile time.</span></span> <span data-ttu-id="4c651-115">Di conseguenza, gli unici valori possibili per le costanti dei tipi di riferimento sono `string` e il riferimento Null.</span><span class="sxs-lookup"><span data-stu-id="4c651-115">Therefore, the only possible values for constants of reference types are `string` and a null reference.</span></span>

<span data-ttu-id="4c651-116">La dichiarazione di costante può includere più costanti, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c651-116">The constant declaration can declare multiple constants, such as:</span></span>

```csharp
public const double X = 1.0, Y = 2.0, Z = 3.0;
```

<span data-ttu-id="4c651-117">Il modificatore `static` non è consentito in una dichiarazione di costante.</span><span class="sxs-lookup"><span data-stu-id="4c651-117">The `static` modifier is not allowed in a constant declaration.</span></span>

<span data-ttu-id="4c651-118">Una costante può far parte di un'espressione costante, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="4c651-118">A constant can participate in a constant expression, as follows:</span></span>

```csharp
public const int C1 = 5;
public const int C2 = C1 + 100;
```

> [!NOTE]
> <span data-ttu-id="4c651-119">La parola chiave [readonly](./readonly.md) è diversa dalla parola chiave `const`.</span><span class="sxs-lookup"><span data-stu-id="4c651-119">The [readonly](./readonly.md) keyword differs from the `const` keyword.</span></span> <span data-ttu-id="4c651-120">Un campo `const` può essere inizializzato solo nella dichiarazione del campo.</span><span class="sxs-lookup"><span data-stu-id="4c651-120">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="4c651-121">Un campo `readonly` può essere inizializzato nella dichiarazione o in un costruttore.</span><span class="sxs-lookup"><span data-stu-id="4c651-121">A `readonly` field can be initialized either at the declaration or in a constructor.</span></span> <span data-ttu-id="4c651-122">I campi `readonly` possono quindi presentare valori diversi a seconda del costruttore usato.</span><span class="sxs-lookup"><span data-stu-id="4c651-122">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="4c651-123">Inoltre, mentre un campo `const` rappresenta una costante in fase di compilazione, il campo `readonly` può essere usato per le costanti in fase di esecuzione, come nella riga seguente: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span><span class="sxs-lookup"><span data-stu-id="4c651-123">Also, although a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants, as in this line: `public static readonly uint l1 = (uint)DateTime.Now.Ticks;`</span></span>

## <a name="example"></a><span data-ttu-id="4c651-124">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c651-124">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#5)]

## <a name="example"></a><span data-ttu-id="4c651-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="4c651-125">Example</span></span>

<span data-ttu-id="4c651-126">In questo esempio viene illustrato come usare le costanti come variabili locali.</span><span class="sxs-lookup"><span data-stu-id="4c651-126">This example demonstrates how to use constants as local variables.</span></span>

[!code-csharp[csrefKeywordsModifiers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="4c651-127">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="4c651-127">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4c651-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c651-128">See also</span></span>

- [<span data-ttu-id="4c651-129">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="4c651-129">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4c651-130">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="4c651-130">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4c651-131">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="4c651-131">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="4c651-132">Modificatori</span><span class="sxs-lookup"><span data-stu-id="4c651-132">Modifiers</span></span>](index.md)
- [<span data-ttu-id="4c651-133">Readonly</span><span class="sxs-lookup"><span data-stu-id="4c651-133">readonly</span></span>](./readonly.md)
