---
title: params (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e66cfc8e7b131a4443ee227df5e39c7e3b775324
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="params-c-reference"></a><span data-ttu-id="8c5e1-102">params (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="8c5e1-102">params (C# Reference)</span></span>
<span data-ttu-id="8c5e1-103">Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](../../../csharp/language-reference/keywords/method-parameters.md) che usa un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="8c5e1-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="8c5e1-104">È possibile inviare un elenco di argomenti separato da virgole del tipo specificato nella dichiarazione di parametri o una matrice di argomenti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="8c5e1-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="8c5e1-105">È anche possibile non inviare alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="8c5e1-105">You also can send no arguments.</span></span> <span data-ttu-id="8c5e1-106">Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.</span><span class="sxs-lookup"><span data-stu-id="8c5e1-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="8c5e1-107">In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.</span><span class="sxs-lookup"><span data-stu-id="8c5e1-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c5e1-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="8c5e1-108">Example</span></span>  
 <span data-ttu-id="8c5e1-109">Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.</span><span class="sxs-lookup"><span data-stu-id="8c5e1-109">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8c5e1-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="8c5e1-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c5e1-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c5e1-111">See Also</span></span>  
 [<span data-ttu-id="8c5e1-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="8c5e1-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8c5e1-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="8c5e1-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8c5e1-114">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="8c5e1-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="8c5e1-115">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="8c5e1-115">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
