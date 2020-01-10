---
title: Parola chiave params - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 90d224080f607cbac96514aaf5ac6d67affef9e0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713235"
---
# <a name="params-c-reference"></a><span data-ttu-id="28336-102">params (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="28336-102">params (C# Reference)</span></span>

<span data-ttu-id="28336-103">Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](method-parameters.md) che usa un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="28336-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span>

<span data-ttu-id="28336-104">È possibile inviare un elenco di argomenti separato da virgole del tipo specificato nella dichiarazione di parametri o una matrice di argomenti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="28336-104">You can send a comma-separated list of arguments of the type specified in the parameter declaration or an array of arguments of the specified type.</span></span> <span data-ttu-id="28336-105">È anche possibile non inviare alcun argomento.</span><span class="sxs-lookup"><span data-stu-id="28336-105">You also can send no arguments.</span></span> <span data-ttu-id="28336-106">Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.</span><span class="sxs-lookup"><span data-stu-id="28336-106">If you send no arguments, the length of the `params` list is zero.</span></span>

<span data-ttu-id="28336-107">In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.</span><span class="sxs-lookup"><span data-stu-id="28336-107">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="28336-108">Il tipo dichiarato del parametro `params` deve essere una matrice unidimensionale, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="28336-108">The declared type of the `params` parameter must be a single-dimensional array, as the following example shows.</span></span> <span data-ttu-id="28336-109">In caso contrario, si verifica l'errore del compilatore [CS0225](../../misc/cs0225.md).</span><span class="sxs-lookup"><span data-stu-id="28336-109">Otherwise, a compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

## <a name="example"></a><span data-ttu-id="28336-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="28336-110">Example</span></span>

<span data-ttu-id="28336-111">Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.</span><span class="sxs-lookup"><span data-stu-id="28336-111">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)] 

## <a name="c-language-specification"></a><span data-ttu-id="28336-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="28336-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="28336-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28336-113">See also</span></span>

- [<span data-ttu-id="28336-114">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="28336-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="28336-115">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="28336-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="28336-116">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="28336-116">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="28336-117">Parametri dei metodi</span><span class="sxs-lookup"><span data-stu-id="28336-117">Method Parameters</span></span>](method-parameters.md)
