---
title: Parola chiave unchecked - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: 6dad0dfd508fb390dd0a52d1b48d70b4c5725513
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713001"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="c20ac-102">unchecked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c20ac-102">unchecked (C# Reference)</span></span>

<span data-ttu-id="c20ac-103">La parola chiave `unchecked` viene usata per eliminare il controllo dell'overflow per le conversioni e le operazioni aritmetiche di tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="c20ac-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="c20ac-104">In un contesto non controllato o di tipo unchecked, se un'espressione produce un valore non compreso nell'intervallo del tipo di destinazione, l'overflow non viene contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="c20ac-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="c20ac-105">Poiché, ad esempio, il calcolo nell'esempio seguente viene eseguito in un'espressione o un blocco di tipo `unchecked`, il fatto che il risultato sia troppo grande per un numero intero viene ignorato e a `int1` viene assegnato il valore -2.147.483.639.</span><span class="sxs-lookup"><span data-stu-id="c20ac-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="c20ac-106">Se l'ambiente `unchecked` viene rimosso, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c20ac-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="c20ac-107">È possibile rilevare l'overflow in fase di compilazione perché tutti i termini dell'espressione sono costanti.</span><span class="sxs-lookup"><span data-stu-id="c20ac-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="c20ac-108">Per impostazione predefinita, le espressioni che contengono termini non costanti non vengono controllate in fase di compilazione e di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c20ac-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="c20ac-109">Per informazioni sull'abilitazione di un ambiente controllato, o di tipo checked, vedere [checked](checked.md).</span><span class="sxs-lookup"><span data-stu-id="c20ac-109">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="c20ac-110">Poiché il controllo dell'overflow richiede tempo, l'uso di codice non controllato in situazioni in cui non vi è pericolo di overflow potrebbe consentire un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c20ac-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="c20ac-111">Se tuttavia è possibile che si verifichi un overflow, è necessario usare un ambiente controllato.</span><span class="sxs-lookup"><span data-stu-id="c20ac-111">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="c20ac-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c20ac-112">Example</span></span>

<span data-ttu-id="c20ac-113">In questo esempio viene illustrato come usare la parola chiave `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="c20ac-113">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="c20ac-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c20ac-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c20ac-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c20ac-115">See also</span></span>

- [<span data-ttu-id="c20ac-116">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="c20ac-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c20ac-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="c20ac-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c20ac-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="c20ac-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c20ac-119">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="c20ac-119">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="c20ac-120">selezionata</span><span class="sxs-lookup"><span data-stu-id="c20ac-120">checked</span></span>](checked.md)
