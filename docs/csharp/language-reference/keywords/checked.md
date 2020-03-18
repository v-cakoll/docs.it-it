---
title: Parola chiave checked - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- checked_CSharpKeyword
- checked
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
ms.openlocfilehash: 5963bb85ef4b61c1dc478667fb0e2e5438f3e4ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713698"
---
# <a name="checked-c-reference"></a><span data-ttu-id="7007a-102">checked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7007a-102">checked (C# Reference)</span></span>

<span data-ttu-id="7007a-103">La parola chiave `checked` viene usata per abilitare in modo esplicito il controllo dell'overflow per le conversioni e le operazioni aritmetiche di tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="7007a-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="7007a-104">Per impostazione predefinita, un'espressione che contiene solo valori costanti provoca un errore di compilazione se l'espressione produce un valore che non è incluso nell'intervallo del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="7007a-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="7007a-105">Se l'espressione contiene uno o più valori non costanti, il compilatore non rileva l'overflow.</span><span class="sxs-lookup"><span data-stu-id="7007a-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="7007a-106">La valutazione dell'espressione assegnata a `i2` nell'esempio seguente non genera un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="7007a-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>

[!code-csharp[csrefKeywordsChecked#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#3)]

<span data-ttu-id="7007a-107">Per impostazione predefinita, in queste espressioni non costanti non viene verificato l'overflow in fase di esecuzione e non vengono generate eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="7007a-107">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="7007a-108">Nell'esempio precedente viene visualizzato il valore -2,147,483,639 come somma di due numeri interi positivi.</span><span class="sxs-lookup"><span data-stu-id="7007a-108">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>

<span data-ttu-id="7007a-109">Il controllo dell'overflow può essere abilitato tramite le opzioni del compilatore, la configurazione dell'ambiente o l'uso della parola chiave `checked`.</span><span class="sxs-lookup"><span data-stu-id="7007a-109">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="7007a-110">Gli esempi seguenti illustrano come usare un'espressione `checked` o un blocco `checked` per rilevare l'overflow generato dalla somma precedente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7007a-110">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="7007a-111">Entrambi gli esempi generano un'eccezione di overflow.</span><span class="sxs-lookup"><span data-stu-id="7007a-111">Both examples raise an overflow exception.</span></span>

[!code-csharp[csrefKeywordsChecked#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#4)]

<span data-ttu-id="7007a-112">La parola chiave [unchecked](./unchecked.md) può essere usata per impedire il controllo dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="7007a-112">The [unchecked](./unchecked.md) keyword can be used to prevent overflow checking.</span></span>

## <a name="example"></a><span data-ttu-id="7007a-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="7007a-113">Example</span></span>

<span data-ttu-id="7007a-114">Questo esempio illustra come usare `checked` per abilitare il controllo dell'overflow in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7007a-114">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>

[!code-csharp[csrefKeywordsChecked#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#1)]

## <a name="c-language-specification"></a><span data-ttu-id="7007a-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="7007a-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7007a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7007a-116">See also</span></span>

- [<span data-ttu-id="7007a-117">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="7007a-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="7007a-118">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="7007a-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="7007a-119">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="7007a-119">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="7007a-120">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="7007a-120">Checked and Unchecked</span></span>](./checked-and-unchecked.md)
- [<span data-ttu-id="7007a-121">non selezionata</span><span class="sxs-lookup"><span data-stu-id="7007a-121">unchecked</span></span>](./unchecked.md)
