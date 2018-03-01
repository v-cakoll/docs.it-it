---
title: unchecked (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c05e7cb742d8e8f5a7804656a5ec13548d0498b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="050cc-102">unchecked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="050cc-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="050cc-103">La parola chiave `unchecked` viene usata per eliminare il controllo dell'overflow per le conversioni e le operazioni aritmetiche di tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="050cc-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="050cc-104">In un contesto non controllato o di tipo unchecked, se un'espressione produce un valore non compreso nell'intervallo del tipo di destinazione, l'overflow non viene contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="050cc-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="050cc-105">Poiché, ad esempio, il calcolo nell'esempio seguente viene eseguito in un'espressione o un blocco di tipo `unchecked`, il fatto che il risultato sia troppo grande per un numero intero viene ignorato e a `int1` viene assegnato il valore -2.147.483.639.</span><span class="sxs-lookup"><span data-stu-id="050cc-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]  
  
 <span data-ttu-id="050cc-106">Se l'ambiente `unchecked` viene rimosso, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="050cc-106">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="050cc-107">È possibile rilevare l'overflow in fase di compilazione perché tutti i termini dell'espressione sono costanti.</span><span class="sxs-lookup"><span data-stu-id="050cc-107">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="050cc-108">Per impostazione predefinita, le espressioni che contengono termini non costanti non vengono controllate in fase di compilazione e di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="050cc-108">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="050cc-109">Per informazioni sull'abilitazione di un ambiente controllato, o di tipo checked, vedere [checked](../../../csharp/language-reference/keywords/checked.md).</span><span class="sxs-lookup"><span data-stu-id="050cc-109">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="050cc-110">Poiché il controllo dell'overflow richiede tempo, l'uso di codice non controllato in situazioni in cui non vi è pericolo di overflow potrebbe consentire un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="050cc-110">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="050cc-111">Se tuttavia è possibile che si verifichi un overflow, è necessario usare un ambiente controllato.</span><span class="sxs-lookup"><span data-stu-id="050cc-111">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="050cc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="050cc-112">Example</span></span>  
 <span data-ttu-id="050cc-113">In questo esempio viene illustrato come usare la parola chiave `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="050cc-113">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 [!code-csharp[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="050cc-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="050cc-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="050cc-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="050cc-115">See Also</span></span>  
 [<span data-ttu-id="050cc-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="050cc-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="050cc-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="050cc-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="050cc-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="050cc-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="050cc-119">Checked e Unchecked</span><span class="sxs-lookup"><span data-stu-id="050cc-119">Checked and Unchecked</span></span>](../../../csharp/language-reference/keywords/checked-and-unchecked.md)  
 [<span data-ttu-id="050cc-120">checked</span><span class="sxs-lookup"><span data-stu-id="050cc-120">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)
