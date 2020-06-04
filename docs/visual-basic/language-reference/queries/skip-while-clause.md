---
title: Clausola Skip While
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkipWhile
helpviewer_keywords:
- Skip While statement [Visual Basic]
- Skip While clause [Visual Basic]
- queries [Visual Basic], Skip While
ms.assetid: 5dee8350-7520-4f1a-b00d-590cacd572d6
ms.openlocfilehash: b357320a92ace1b7a261991737ed653d54d0eeab
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84359645"
---
# <a name="skip-while-clause-visual-basic"></a><span data-ttu-id="01eda-102">Clausola Skip While (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01eda-102">Skip While Clause (Visual Basic)</span></span>
<span data-ttu-id="01eda-103">Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="01eda-103">Bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01eda-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01eda-104">Syntax</span></span>  
  
```vb  
Skip While expression  
```  
  
## <a name="parts"></a><span data-ttu-id="01eda-105">Parti</span><span class="sxs-lookup"><span data-stu-id="01eda-105">Parts</span></span>  
  
|<span data-ttu-id="01eda-106">Termine</span><span class="sxs-lookup"><span data-stu-id="01eda-106">Term</span></span>|<span data-ttu-id="01eda-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="01eda-107">Definition</span></span>|  
|---|---|  
|`expression`|<span data-ttu-id="01eda-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="01eda-108">Required.</span></span> <span data-ttu-id="01eda-109">Espressione che rappresenta una condizione per cui verificare gli elementi.</span><span class="sxs-lookup"><span data-stu-id="01eda-109">An expression that represents a condition to test elements for.</span></span> <span data-ttu-id="01eda-110">L'espressione deve restituire un `Boolean` valore o un equivalente funzionale, ad esempio un oggetto `Integer` da valutare come `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="01eda-110">The expression must return a `Boolean` value or a functional equivalent, such as an `Integer` to be evaluated as a `Boolean`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01eda-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="01eda-111">Remarks</span></span>  
 <span data-ttu-id="01eda-112">La `Skip While` clausola ignora gli elementi dall'inizio di un risultato della query fino a quando l'oggetto specificato `expression` restituisce `false` .</span><span class="sxs-lookup"><span data-stu-id="01eda-112">The `Skip While` clause bypasses elements from the beginning of a query result until the supplied `expression` returns `false`.</span></span> <span data-ttu-id="01eda-113">`expression`Una volta restituito `false` , la query restituisce tutti gli elementi rimanenti.</span><span class="sxs-lookup"><span data-stu-id="01eda-113">After `expression` returns `false`, the query returns all the remaining elements.</span></span> <span data-ttu-id="01eda-114">`expression`Viene ignorato per i risultati rimanenti.</span><span class="sxs-lookup"><span data-stu-id="01eda-114">The `expression` is ignored for the remaining results.</span></span>  
  
 <span data-ttu-id="01eda-115">La clausola è `Skip While` diversa dalla `Where` clausola in quanto la `Where` clausola può essere usata per escludere tutti gli elementi da una query che non soddisfano una determinata condizione.</span><span class="sxs-lookup"><span data-stu-id="01eda-115">The `Skip While` clause differs from the `Where` clause in that the `Where` clause can be used to exclude all elements from a query that do not meet a particular condition.</span></span> <span data-ttu-id="01eda-116">La `Skip While` clausola esclude gli elementi solo fino alla prima volta che la condizione non viene soddisfatta.</span><span class="sxs-lookup"><span data-stu-id="01eda-116">The `Skip While` clause excludes elements only until the first time that the condition is not satisfied.</span></span> <span data-ttu-id="01eda-117">La `Skip While` clausola è particolarmente utile quando si lavora con un risultato di query ordinato.</span><span class="sxs-lookup"><span data-stu-id="01eda-117">The `Skip While` clause is most useful when you are working with an ordered query result.</span></span>  
  
 <span data-ttu-id="01eda-118">È possibile ignorare un numero specifico di risultati dall'inizio di un risultato della query usando la `Skip` clausola.</span><span class="sxs-lookup"><span data-stu-id="01eda-118">You can bypass a specific number of results from the beginning of a query result by using the `Skip` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01eda-119">Esempio</span><span class="sxs-lookup"><span data-stu-id="01eda-119">Example</span></span>  
 <span data-ttu-id="01eda-120">Nell'esempio di codice seguente viene utilizzata la `Skip While` clausola per ignorare i risultati fino a quando non viene trovato il primo cliente del Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="01eda-120">The following code example uses the `Skip While` clause to bypass results until the first customer from the United States is found.</span></span>  
  
 [!code-vb[VbSimpleQuerySamples#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="01eda-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01eda-121">See also</span></span>

- [<span data-ttu-id="01eda-122">Introduzione a LINQ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="01eda-122">Introduction to LINQ in Visual Basic</span></span>](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="01eda-123">Query</span><span class="sxs-lookup"><span data-stu-id="01eda-123">Queries</span></span>](index.md)
- [<span data-ttu-id="01eda-124">Clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="01eda-124">Select Clause</span></span>](select-clause.md)
- [<span data-ttu-id="01eda-125">Clausola from</span><span class="sxs-lookup"><span data-stu-id="01eda-125">From Clause</span></span>](from-clause.md)
- [<span data-ttu-id="01eda-126">Clausola Skip</span><span class="sxs-lookup"><span data-stu-id="01eda-126">Skip Clause</span></span>](skip-clause.md)
- [<span data-ttu-id="01eda-127">Clausola Take While</span><span class="sxs-lookup"><span data-stu-id="01eda-127">Take While Clause</span></span>](take-while-clause.md)
- [<span data-ttu-id="01eda-128">Clausola WHERE</span><span class="sxs-lookup"><span data-stu-id="01eda-128">Where Clause</span></span>](where-clause.md)
