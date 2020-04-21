---
title: params (parola chiave) per le matrici di parametri - Riferimento in C
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738833"
---
# <a name="params-c-reference"></a><span data-ttu-id="6d861-102">params (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6d861-102">params (C# Reference)</span></span>

<span data-ttu-id="6d861-103">Usando la parola chiave `params`, è possibile specificare un [parametro di metodo](method-parameters.md) che usa un numero variabile di argomenti.</span><span class="sxs-lookup"><span data-stu-id="6d861-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="6d861-104">Il tipo di parametro deve essere una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="6d861-104">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="6d861-105">In una dichiarazione di metodo non è possibile aggiungere altri parametri dopo la parola chiave `params` ed è consentito l'uso di una sola parola chiave `params`.</span><span class="sxs-lookup"><span data-stu-id="6d861-105">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="6d861-106">Se il tipo `params` dichiarato del parametro non è una matrice unidimensionale, si verifica l'errore del compilatore [CS0225.](../../misc/cs0225.md)</span><span class="sxs-lookup"><span data-stu-id="6d861-106">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="6d861-107">Quando si chiama un `params` metodo con un parametro, è possibile passare:When you call a method with a parameter, you can pass in:</span><span class="sxs-lookup"><span data-stu-id="6d861-107">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="6d861-108">Elenco delimitato da virgole di argomenti del tipo degli elementi della matrice.</span><span class="sxs-lookup"><span data-stu-id="6d861-108">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="6d861-109">Matrice di argomenti del tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="6d861-109">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="6d861-110">Nessun argomento.</span><span class="sxs-lookup"><span data-stu-id="6d861-110">No arguments.</span></span> <span data-ttu-id="6d861-111">Se non vengono inviati argomenti, la lunghezza dell'elenco `params` è zero.</span><span class="sxs-lookup"><span data-stu-id="6d861-111">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="6d861-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d861-112">Example</span></span>

<span data-ttu-id="6d861-113">Nell'esempio seguente vengono illustrati i vari modi in cui è possibile inviare argomenti al parametro `params`.</span><span class="sxs-lookup"><span data-stu-id="6d861-113">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="6d861-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6d861-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6d861-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d861-115">See also</span></span>

- [<span data-ttu-id="6d861-116">Guida di riferimento a C</span><span class="sxs-lookup"><span data-stu-id="6d861-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6d861-117">Guida alla programmazione in C</span><span class="sxs-lookup"><span data-stu-id="6d861-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6d861-118">Parole chiave di C</span><span class="sxs-lookup"><span data-stu-id="6d861-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="6d861-119">Parametri di metodo</span><span class="sxs-lookup"><span data-stu-id="6d861-119">Method Parameters</span></span>](method-parameters.md)
