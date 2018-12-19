---
title: as - Riferimenti per C#
ms.custom: seodec18
ms.date: 10/11/2018
f1_keywords:
- as_CSharpKeyword
- as
helpviewer_keywords:
- type conversion [C#], as keyword
- as keyword [C#]
ms.assetid: a9be126b-cbf4-4990-a70d-d0e1983cad0e
ms.openlocfilehash: 7559c24151a3c9acc79c0554112c923a23a88564
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244349"
---
# <a name="as-c-reference"></a><span data-ttu-id="02b19-102">as (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="02b19-102">as (C# Reference)</span></span>
<span data-ttu-id="02b19-103">È possibile usare l'operatore `as` per eseguire determinati tipi di conversioni tra tipi di riferimenti compatibili o [tipi nullable](../../../csharp/programming-guide/nullable-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="02b19-103">You can use the `as` operator to perform certain types of conversions between compatible reference types or [nullable types](../../../csharp/programming-guide/nullable-types/index.md).</span></span> <span data-ttu-id="02b19-104">Il codice seguente illustra un esempio.</span><span class="sxs-lookup"><span data-stu-id="02b19-104">The following code shows an example.</span></span>  
  
[!code-csharp[csrefKeywordsOperator#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#1)]

<span data-ttu-id="02b19-105">Come mostrato nell'esempio, è necessario confrontare il risultato dell'espressione `as` con `null` per verificare se la conversione riesce.</span><span class="sxs-lookup"><span data-stu-id="02b19-105">As the example shows, you need to compare the result of the `as` expression with `null` to check if a conversion is successful.</span></span> <span data-ttu-id="02b19-106">A partire da C# 7.0, è possibile usare l'espressione [is](is.md) per testare la corretta esecuzione di una conversione e assegnare in modo condizionale una variabile quando la conversione riesce.</span><span class="sxs-lookup"><span data-stu-id="02b19-106">Beginning with C# 7.0, you can use the [is](is.md) expression both to test that a conversion succeeds and conditionally assign a variable when the conversion succeeds.</span></span> <span data-ttu-id="02b19-107">In molti scenari è più efficace dell'uso dell'operatore `as`.</span><span class="sxs-lookup"><span data-stu-id="02b19-107">In many scenarios, it's more concise than using the `as` operator.</span></span> <span data-ttu-id="02b19-108">Per altre informazioni, vedere la sezione[Criterio del tipo](is.md#type) dell'articolo [Operatore `is`](is.md).</span><span class="sxs-lookup"><span data-stu-id="02b19-108">For more information, see the [Type pattern](is.md#type) section of the [`is` operator](is.md) article.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="02b19-109">Note</span><span class="sxs-lookup"><span data-stu-id="02b19-109">Remarks</span></span>  
 <span data-ttu-id="02b19-110">L'operatore `as` è simile a un'operazione cast.</span><span class="sxs-lookup"><span data-stu-id="02b19-110">The `as` operator is like a cast operation.</span></span> <span data-ttu-id="02b19-111">Tuttavia, se la conversione non è possibile, `as` restituisce `null` anziché generare un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="02b19-111">However, if the conversion isn't possible, `as` returns `null` instead of raising an exception.</span></span> <span data-ttu-id="02b19-112">Si consideri l'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="02b19-112">Consider the following example:</span></span>  
  
```csharp  
expression as type  
```  
  
 <span data-ttu-id="02b19-113">Il codice è equivalente all'espressione seguente, ad eccezione della variabile `expression` che viene restituita una sola volta.</span><span class="sxs-lookup"><span data-stu-id="02b19-113">The code is equivalent to the following expression except that the `expression` variable is evaluated only one time.</span></span>  
  
```csharp  
expression is type ? (type)expression : (type)null  
```  
  
 <span data-ttu-id="02b19-114">Si noti che l'operatore `as` esegue solo conversioni di riferimenti, conversioni nullable e conversioni boxing.</span><span class="sxs-lookup"><span data-stu-id="02b19-114">Note that the `as` operator performs only reference conversions, nullable conversions, and boxing conversions.</span></span> <span data-ttu-id="02b19-115">L'operatore `as` non può eseguire altre conversioni, ad esempio conversioni definite dall'utente, le quali devono invece essere eseguite tramite le espressioni cast.</span><span class="sxs-lookup"><span data-stu-id="02b19-115">The `as` operator can't perform other conversions, such as user-defined conversions, which should instead be performed by using cast expressions.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02b19-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="02b19-116">Example</span></span>  

[!code-csharp[csrefKeywordsOperator#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#2)]
  
## <a name="c-language-specification"></a><span data-ttu-id="02b19-117">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="02b19-117">C# Language Specification</span></span>  

<span data-ttu-id="02b19-118">Per altre informazioni, vedere [Operatore as](~/_csharplang/spec/expressions.md#the-as-operator) in [Specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="02b19-118">For more information, see [The as operator](~/_csharplang/spec/expressions.md#the-as-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="02b19-119">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="02b19-119">The language specification is the definitive source for C# syntax and usage.</span></span>
 
## <a name="see-also"></a><span data-ttu-id="02b19-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="02b19-120">See Also</span></span>  
- [<span data-ttu-id="02b19-121">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="02b19-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="02b19-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="02b19-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="02b19-123">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="02b19-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="02b19-124">is</span><span class="sxs-lookup"><span data-stu-id="02b19-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)  
- [<span data-ttu-id="02b19-125">?: (operatore)</span><span class="sxs-lookup"><span data-stu-id="02b19-125">?: Operator</span></span>](../../../csharp/language-reference/operators/conditional-operator.md)  
- [<span data-ttu-id="02b19-126">Parole chiave per gli operatori</span><span class="sxs-lookup"><span data-stu-id="02b19-126">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)
