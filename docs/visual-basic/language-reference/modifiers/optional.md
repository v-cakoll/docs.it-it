---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: b55252e774e744b7318f480b264aa3f7fae9abfc
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969643"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="96fe1-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96fe1-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="96fe1-103">Specifica che un argomento di routine può essere omessa quando viene chiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="96fe1-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="96fe1-104">Note</span><span class="sxs-lookup"><span data-stu-id="96fe1-104">Remarks</span></span>  
 <span data-ttu-id="96fe1-105">Per ogni parametro facoltativo, è necessario specificare un'espressione costante come valore predefinito di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="96fe1-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="96fe1-106">Se l'espressione viene valutata [Nothing](../../../visual-basic/language-reference/nothing.md), il valore predefinito del tipo di dati di valore viene utilizzato come valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="96fe1-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="96fe1-107">Se l'elenco di parametri contiene un parametro facoltativo, ogni parametro che lo segue deve anche essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="96fe1-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="96fe1-108">Il modificatore `Optional` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="96fe1-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="96fe1-109">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="96fe1-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="96fe1-110">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="96fe1-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="96fe1-111">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="96fe1-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="96fe1-112">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="96fe1-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="96fe1-113">Quando si chiama una routine con o senza parametri facoltativi, è possibile passare argomenti in base alla posizione o al nome.</span><span class="sxs-lookup"><span data-stu-id="96fe1-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="96fe1-114">Per altre informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="96fe1-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96fe1-115">È anche possibile definire una routine con parametri facoltativi usando l'overload.</span><span class="sxs-lookup"><span data-stu-id="96fe1-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="96fe1-116">Se si dispone di un parametro facoltativo, è possibile definire due versioni di overload di routine, uno che accetta il parametro e l'altra che non.</span><span class="sxs-lookup"><span data-stu-id="96fe1-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="96fe1-117">Per altre informazioni, vedere [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="96fe1-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="96fe1-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="96fe1-118">Example</span></span>  
 <span data-ttu-id="96fe1-119">L'esempio seguente definisce una routine che ha un parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="96fe1-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="96fe1-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="96fe1-120">Example</span></span>  
 <span data-ttu-id="96fe1-121">Nell'esempio seguente viene illustrato come chiamare una routine con gli argomenti passati in base alla posizione e con gli argomenti passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="96fe1-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="96fe1-122">La procedura ha due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="96fe1-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="96fe1-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96fe1-123">See also</span></span>
- [<span data-ttu-id="96fe1-124">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="96fe1-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="96fe1-125">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="96fe1-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="96fe1-126">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="96fe1-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
