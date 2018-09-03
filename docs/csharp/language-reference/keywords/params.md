---
title: params (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 692c2f61ae99f1c1c8e04a5a1bcad08814d286fe
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752093"
---
# <a name="params-c-reference"></a><span data-ttu-id="88c5c-102">params (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="88c5c-102">params (C# Reference)</span></span>
<span data-ttu-id="88c5c-103">Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](../../../csharp/language-reference/keywords/method-parameters.md) che usa un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="88c5c-103">By using the `params` keyword, you can specify a [method parameter](../../../csharp/language-reference/keywords/method-parameters.md) that takes a variable number of arguments.</span></span>  
  
 <span data-ttu-id="88c5c-104">È possibile inviare un elenco di argomenti separato da virgole del tipo specificato nella dichiarazione di parametri o una matrice di argomenti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="88c5c-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="88c5c-105">È anche possibile non inviare alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="88c5c-105">You also can send no arguments.</span></span> <span data-ttu-id="88c5c-106">Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.</span><span class="sxs-lookup"><span data-stu-id="88c5c-106">If you send no arguments, the length of the `params` list is zero.</span></span>  
  
 <span data-ttu-id="88c5c-107">In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.</span><span class="sxs-lookup"><span data-stu-id="88c5c-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>  
 
 <span data-ttu-id="88c5c-108">Il tipo dichiarato del parametro `params` deve essere una matrice unidimensionale, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="88c5c-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="88c5c-109">In caso contrario, si verifica l'errore del compilatore [CS0225](../../../csharp/misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="88c5c-109">Otherwise, a compiler error [CS0225](../../../csharp/misc/cs0225.md) occurs.</span></span>
  
## <a name="example"></a><span data-ttu-id="88c5c-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="88c5c-110">Example</span></span>  
 <span data-ttu-id="88c5c-111">Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.</span><span class="sxs-lookup"><span data-stu-id="88c5c-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>  
  
 [!code-csharp[csrefKeywordsMethodParams#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/params_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="88c5c-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="88c5c-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="88c5c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="88c5c-113">See Also</span></span>  
 [<span data-ttu-id="88c5c-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="88c5c-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="88c5c-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="88c5c-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="88c5c-116">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="88c5c-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="88c5c-117">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="88c5c-117">Method Parameters</span></span>](../../../csharp/language-reference/keywords/method-parameters.md)
