---
title: params (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
dev_langs:
- CSharp
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5999911b96d17c710096e74c8f3da65223e778fc
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="params-c-reference"></a><span data-ttu-id="07f01-102">params (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="07f01-102">params (C# Reference)</span></span>
<span data-ttu-id="07f01-103">Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](../../../csharp/language-reference/keywords/method-parameters.md) che usa un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="07f01-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="07f01-104">È possibile inviare un elenco di argomenti separato da virgole del tipo specificato nella dichiarazione di parametri o una matrice di argomenti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="07f01-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="07f01-105">È anche possibile non inviare alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="07f01-105">You also can send no arguments.</span></span> <span data-ttu-id="07f01-106">Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.</span><span class="sxs-lookup"><span data-stu-id="07f01-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="07f01-107">In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.</span><span class="sxs-lookup"><span data-stu-id="07f01-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07f01-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="07f01-108">Example</span></span>  
 <span data-ttu-id="07f01-109">Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.</span><span class="sxs-lookup"><span data-stu-id="07f01-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 <span data-ttu-id="07f01-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="07f01-110">[!code-cs[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="07f01-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="07f01-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="07f01-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07f01-112">See Also</span></span>  
 <span data-ttu-id="07f01-113">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="07f01-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="07f01-114">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="07f01-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="07f01-115">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="07f01-115">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 [<span data-ttu-id="07f01-116">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="07f01-116">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)

