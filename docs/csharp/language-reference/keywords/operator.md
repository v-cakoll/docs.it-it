---
title: Parola chiave operator (Riferimenti per C#)
description: Informazioni su come eseguire l'overload di un operatore C# predefinito
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 1e11d7767b61becc39b1158fae9cb2abe997e4bd
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480652"
---
# <a name="operator-c-reference"></a><span data-ttu-id="66ad5-103">operator (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="66ad5-103">operator (C# Reference)</span></span>

<span data-ttu-id="66ad5-104">Usare la parola chiave `operator` per eseguire l'overload di un operatore predefinito o specificare una conversione definita dall'utente in una classe o una dichiarazione di struttura.</span><span class="sxs-lookup"><span data-stu-id="66ad5-104">Use the `operator` keyword to overload a built-in operator or to provide a user-defined conversion in a class or struct declaration.</span></span>

<span data-ttu-id="66ad5-105">Per eseguire l'overload di un operatore in una classe o uno struct personalizzati, si crea una dichiarazione dell'operatore nel tipo corrispondente.</span><span class="sxs-lookup"><span data-stu-id="66ad5-105">To overload an operator on a custom class or struct, you create an operator declaration in the corresponding type.</span></span> <span data-ttu-id="66ad5-106">La dichiarazione dell'operatore che esegue l'overload di un operatore C# predefinito deve soddisfare le regole seguenti:</span><span class="sxs-lookup"><span data-stu-id="66ad5-106">The operator declaration that overloads a built-in C# operator must satisfy the following rules:</span></span>

- <span data-ttu-id="66ad5-107">Include sia un modificatore `public` che un modificatore `static`.</span><span class="sxs-lookup"><span data-stu-id="66ad5-107">It includes both a `public` and a `static` modifier.</span></span>
- <span data-ttu-id="66ad5-108">Include `operator X` dove `X` è il nome o il simbolo dell'operatore sottoposto a overload.</span><span class="sxs-lookup"><span data-stu-id="66ad5-108">It includes `operator X` where `X` is the name or symbol of the operator being overloaded.</span></span>
- <span data-ttu-id="66ad5-109">Gli operatori unari hanno un parametro, gli operatori binari invece due parametri.</span><span class="sxs-lookup"><span data-stu-id="66ad5-109">Unary operators have one parameter, and binary operators have two parameters.</span></span> <span data-ttu-id="66ad5-110">In ogni caso, almeno un parametro deve essere dello stesso tipo della classe o struct che dichiara l'operatore.</span><span class="sxs-lookup"><span data-stu-id="66ad5-110">In each case, at least one parameter must be the same type as the class or struct that declares the operator.</span></span>

<span data-ttu-id="66ad5-111">Per informazioni su come definire gli operatori di conversione, vedere gli articoli sulle parole chiave [explicit](explicit.md) e [implicit](implicit.md).</span><span class="sxs-lookup"><span data-stu-id="66ad5-111">For information about how to define conversion operators, see the [explicit](explicit.md) and [implicit](implicit.md) keyword articles.</span></span>

<span data-ttu-id="66ad5-112">Per una panoramica degli operatori C# che possono essere sottoposti a overload, vedere l'articolo [Operatori che supportano l'overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md).</span><span class="sxs-lookup"><span data-stu-id="66ad5-112">For an overview of the C# operators that can be overloaded, see the [Overloadable operators](../../programming-guide/statements-expressions-operators/overloadable-operators.md) article.</span></span>

## <a name="example"></a><span data-ttu-id="66ad5-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="66ad5-113">Example</span></span>

<span data-ttu-id="66ad5-114">L'esempio seguente definisce un tipo `Fraction` che rappresenta i numeri frazionari.</span><span class="sxs-lookup"><span data-stu-id="66ad5-114">The following example defines a `Fraction` type that represents fractional numbers.</span></span> <span data-ttu-id="66ad5-115">La classe esegue l'overload degli operatori `+` e `*` per eseguire addizioni e moltiplicazioni frazionarie e specifica un operatore di conversione che converte un tipo `Fraction` in un tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="66ad5-115">It overloads the `+` and `*` operators to perform fractional addition and multiplication, and also provides a conversion operator that converts a `Fraction` type to a `double` type.</span></span>

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a><span data-ttu-id="66ad5-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="66ad5-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="66ad5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="66ad5-117">See also</span></span>

- [<span data-ttu-id="66ad5-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="66ad5-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="66ad5-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="66ad5-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="66ad5-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="66ad5-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="66ad5-121">implicit</span><span class="sxs-lookup"><span data-stu-id="66ad5-121">implicit</span></span>](implicit.md)
- [<span data-ttu-id="66ad5-122">explicit</span><span class="sxs-lookup"><span data-stu-id="66ad5-122">explicit</span></span>](explicit.md)
- [<span data-ttu-id="66ad5-123">Operatori che supportano l'overload</span><span class="sxs-lookup"><span data-stu-id="66ad5-123">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="66ad5-124">Procedura: Implementare conversioni tra struct definite dall'utente</span><span class="sxs-lookup"><span data-stu-id="66ad5-124">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
