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
ms.openlocfilehash: f88020c7407fb9c91e06bc2ee177773171e344fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599304"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="10a3e-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10a3e-102">Optional (Visual Basic)</span></span>
<span data-ttu-id="10a3e-103">Specifica che un argomento di routine può essere omesso quando viene chiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="10a3e-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10a3e-104">Note</span><span class="sxs-lookup"><span data-stu-id="10a3e-104">Remarks</span></span>  
 <span data-ttu-id="10a3e-105">Per ogni parametro facoltativo, è necessario specificare un'espressione costante come valore predefinito di tale parametro.</span><span class="sxs-lookup"><span data-stu-id="10a3e-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="10a3e-106">Se l'espressione restituisce [nulla](../../../visual-basic/language-reference/nothing.md), il valore predefinito del tipo di dati di valore viene utilizzato come valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="10a3e-106">If the expression evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>  
  
 <span data-ttu-id="10a3e-107">Se l'elenco dei parametri contiene un parametro facoltativo, ogni parametro che segue deve essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="10a3e-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>  
  
 <span data-ttu-id="10a3e-108">Il modificatore `Optional` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="10a3e-108">The `Optional` modifier can be used in these contexts:</span></span>  
  
-   [<span data-ttu-id="10a3e-109">Istruzione Declare</span><span class="sxs-lookup"><span data-stu-id="10a3e-109">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="10a3e-110">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="10a3e-110">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="10a3e-111">Istruzione Property</span><span class="sxs-lookup"><span data-stu-id="10a3e-111">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="10a3e-112">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="10a3e-112">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  <span data-ttu-id="10a3e-113">Quando si chiama una routine con o senza parametri facoltativi, è possibile passare argomenti in base alla posizione o al nome.</span><span class="sxs-lookup"><span data-stu-id="10a3e-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="10a3e-114">Per ulteriori informazioni, vedere [il passaggio di argomenti in base alla posizione e al nome](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="10a3e-114">For more information, see [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10a3e-115">È inoltre possibile definire una routine con parametri facoltativi utilizzando l'overload.</span><span class="sxs-lookup"><span data-stu-id="10a3e-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="10a3e-116">Se si dispone di un parametro facoltativo, è possibile definire due versioni di overload della routine, una che accetta il parametro e uno senza.</span><span class="sxs-lookup"><span data-stu-id="10a3e-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="10a3e-117">Per ulteriori informazioni, vedere [overload di routine](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="10a3e-117">For more information, see [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10a3e-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="10a3e-118">Example</span></span>  
 <span data-ttu-id="10a3e-119">Nell'esempio seguente definisce una routine che ha un parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="10a3e-119">The following example defines a procedure that has an optional parameter.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="10a3e-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="10a3e-120">Example</span></span>  
 <span data-ttu-id="10a3e-121">Nell'esempio seguente viene illustrato come chiamare una routine con gli argomenti passati in base alla posizione e con gli argomenti passati per nome.</span><span class="sxs-lookup"><span data-stu-id="10a3e-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="10a3e-122">La procedura include due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="10a3e-122">The procedure has two optional parameters.</span></span>  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="10a3e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10a3e-123">See Also</span></span>  
 [<span data-ttu-id="10a3e-124">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="10a3e-124">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="10a3e-125">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="10a3e-125">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [<span data-ttu-id="10a3e-126">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="10a3e-126">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
