---
title: checked (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- checked_CSharpKeyword
- checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked keyword [C#]
ms.assetid: 718a1194-988d-48a3-b089-d6ee8bd1608d
caps.latest.revision: 24
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
ms.openlocfilehash: abe34772c0f07b0a43f7299088bf5ea9a1d2aa78
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-reference"></a><span data-ttu-id="c5dee-102">checked (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="c5dee-102">checked (C# Reference)</span></span>
<span data-ttu-id="c5dee-103">La parola chiave `checked` viene usata per abilitare in modo esplicito il controllo dell'overflow per le conversioni e le operazioni aritmetiche di tipo integrale.</span><span class="sxs-lookup"><span data-stu-id="c5dee-103">The `checked` keyword is used to explicitly enable overflow checking for integral-type arithmetic operations and conversions.</span></span>  
  
 <span data-ttu-id="c5dee-104">Per impostazione predefinita, un'espressione che contiene solo valori costanti provoca un errore di compilazione se l'espressione produce un valore che non è incluso nell'intervallo del tipo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c5dee-104">By default, an expression that contains only constant values causes a compiler error if the expression produces a value that is outside the range of the destination type.</span></span> <span data-ttu-id="c5dee-105">Se l'espressione contiene uno o più valori non costanti, il compilatore non rileva l'overflow.</span><span class="sxs-lookup"><span data-stu-id="c5dee-105">If the expression contains one or more non-constant values, the compiler does not detect the overflow.</span></span> <span data-ttu-id="c5dee-106">La valutazione dell'espressione assegnata a `i2` nell'esempio seguente non genera un errore di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c5dee-106">Evaluating the expression assigned to `i2` in the following example does not cause a compiler error.</span></span>  
  
 <span data-ttu-id="c5dee-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c5dee-107">[!code-cs[csrefKeywordsChecked#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_1.cs)]</span></span>  
  
 <span data-ttu-id="c5dee-108">Per impostazione predefinita, in queste espressioni non costanti non viene verificato l'overflow in fase di esecuzione e non vengono generate eccezioni di overflow.</span><span class="sxs-lookup"><span data-stu-id="c5dee-108">By default, these non-constant expressions are not checked for overflow at run time either, and they do not raise overflow exceptions.</span></span> <span data-ttu-id="c5dee-109">Nell'esempio precedente viene visualizzato il valore -2,147,483,639 come somma di due numeri interi positivi.</span><span class="sxs-lookup"><span data-stu-id="c5dee-109">The previous example displays -2,147,483,639 as the sum of two positive integers.</span></span>  
  
 <span data-ttu-id="c5dee-110">Il controllo dell'overflow può essere abilitato tramite le opzioni del compilatore, la configurazione dell'ambiente o l'uso della parola chiave `checked`.</span><span class="sxs-lookup"><span data-stu-id="c5dee-110">Overflow checking can be enabled by compiler options, environment configuration, or use of the `checked` keyword.</span></span> <span data-ttu-id="c5dee-111">Gli esempi seguenti illustrano come usare un'espressione `checked` o un blocco `checked` per rilevare l'overflow generato dalla somma precedente in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c5dee-111">The following examples demonstrate how to use a `checked` expression or a `checked` block to detect the overflow that is produced by the previous sum at run time.</span></span> <span data-ttu-id="c5dee-112">Entrambi gli esempi generano un'eccezione di overflow.</span><span class="sxs-lookup"><span data-stu-id="c5dee-112">Both examples raise an overflow exception.</span></span>  
  
 <span data-ttu-id="c5dee-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c5dee-113">[!code-cs[csrefKeywordsChecked#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_2.cs)]</span></span>  
  
 <span data-ttu-id="c5dee-114">La parola chiave [unchecked](../../../csharp/language-reference/keywords/unchecked.md) può essere usata per impedire il controllo dell'overflow.</span><span class="sxs-lookup"><span data-stu-id="c5dee-114">The [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword can be used to prevent overflow checking.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5dee-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="c5dee-115">Example</span></span>  
 <span data-ttu-id="c5dee-116">Questo esempio illustra come usare `checked` per abilitare il controllo dell'overflow in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="c5dee-116">This sample shows how to use `checked` to enable overflow checking at run time.</span></span>  
  
 <span data-ttu-id="c5dee-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c5dee-117">[!code-cs[csrefKeywordsChecked#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/checked_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c5dee-118">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="c5dee-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c5dee-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c5dee-119">See Also</span></span>  
 <span data-ttu-id="c5dee-120">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5dee-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c5dee-121">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5dee-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c5dee-122">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c5dee-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c5dee-123">[Checked e unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span><span class="sxs-lookup"><span data-stu-id="c5dee-123">[Checked and Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) </span></span>  
 [<span data-ttu-id="c5dee-124">unchecked</span><span class="sxs-lookup"><span data-stu-id="c5dee-124">unchecked</span></span>](../../../csharp/language-reference/keywords/unchecked.md)

