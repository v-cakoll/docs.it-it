---
title: unchecked (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
dev_langs:
- CSharp
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
caps.latest.revision: 23
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5878a2412e6c85da85b1a3b8c2a8255b51e67137
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="unchecked-c-reference"></a><span data-ttu-id="b3297-102">unchecked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b3297-102">unchecked (C# Reference)</span></span>
<span data-ttu-id="b3297-103">La parola chiave `unchecked` viene usata per eliminare il controllo dell'overflow per le conversioni e le operazioni aritmetiche di tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="b3297-103">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="b3297-104">In un contesto non controllato o di tipo unchecked, se un'espressione produce un valore non compreso nell'intervallo del tipo di destinazione, l'overflow non viene contrassegnato.</span><span class="sxs-lookup"><span data-stu-id="b3297-104">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="b3297-105">Poiché, ad esempio, il calcolo nell'esempio seguente viene eseguito in un'espressione o un blocco di tipo `unchecked`, il fatto che il risultato sia troppo grande per un numero intero viene ignorato e a `int1` viene assegnato il valore -2.147.483.639.</span><span class="sxs-lookup"><span data-stu-id="b3297-105">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>  
  
 <span data-ttu-id="b3297-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b3297-106">[!code-cs[csrefKeywordsChecked#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_1.cs)]</span></span>  
  
 <span data-ttu-id="b3297-107">Se l'ambiente `unchecked` viene rimosso, si verifica un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="b3297-107">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="b3297-108">È possibile rilevare l'overflow in fase di compilazione perché tutti i termini dell'espressione sono costanti.</span><span class="sxs-lookup"><span data-stu-id="b3297-108">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>  
  
 <span data-ttu-id="b3297-109">Per impostazione predefinita, le espressioni che contengono termini non costanti non vengono controllate in fase di compilazione e di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b3297-109">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="b3297-110">Per informazioni sull'abilitazione di un ambiente controllato, o di tipo checked, vedere [checked](../../../csharp/language-reference/keywords/checked.md).</span><span class="sxs-lookup"><span data-stu-id="b3297-110">See [checked](../../../csharp/language-reference/keywords/checked.md) for information about enabling a checked environment.</span></span>  
  
 <span data-ttu-id="b3297-111">Poiché il controllo dell'overflow richiede tempo, l'uso di codice non controllato in situazioni in cui non vi è pericolo di overflow potrebbe consentire un miglioramento delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b3297-111">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="b3297-112">Se tuttavia è possibile che si verifichi un overflow, è necessario usare un ambiente controllato.</span><span class="sxs-lookup"><span data-stu-id="b3297-112">However, if overflow is a possibility, a checked environment should be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3297-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b3297-113">Example</span></span>  
 <span data-ttu-id="b3297-114">In questo esempio viene illustrato come usare la parola chiave `unchecked`.</span><span class="sxs-lookup"><span data-stu-id="b3297-114">This sample shows how to use the `unchecked` keyword.</span></span>  
  
 <span data-ttu-id="b3297-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b3297-115">[!code-cs[csrefKeywordsChecked#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/unchecked_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b3297-116">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b3297-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b3297-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3297-117">See Also</span></span>  
 <span data-ttu-id="b3297-118">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b3297-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b3297-119">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b3297-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b3297-120">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b3297-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b3297-121">[Checked e Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="b3297-121">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="b3297-122">checked</span><span class="sxs-lookup"><span data-stu-id="b3297-122">checked</span></span>](../../../csharp/language-reference/keywords/checked.md)

