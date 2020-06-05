---
title: Facoltativo
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: c46d06dba61158d7362d736731161be306af3f10
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392145"
---
# <a name="optional-visual-basic"></a><span data-ttu-id="b57b8-102">Optional (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b57b8-102">Optional (Visual Basic)</span></span>

<span data-ttu-id="b57b8-103">Specifica che un argomento di routine può essere omesso quando viene chiamata la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="b57b8-103">Specifies that a procedure argument can be omitted when the procedure is called.</span></span>

## <a name="remarks"></a><span data-ttu-id="b57b8-104">Commenti</span><span class="sxs-lookup"><span data-stu-id="b57b8-104">Remarks</span></span>

<span data-ttu-id="b57b8-105">Per ogni parametro facoltativo, è necessario specificare un'espressione costante come valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="b57b8-105">For each optional parameter, you must specify a constant expression as the default value of that parameter.</span></span> <span data-ttu-id="b57b8-106">Se l'espressione restituisce [Nothing](../nothing.md), il valore predefinito del tipo di dati value viene utilizzato come valore predefinito del parametro.</span><span class="sxs-lookup"><span data-stu-id="b57b8-106">If the expression evaluates to [Nothing](../nothing.md), the default value of the value data type is used as the default value of the parameter.</span></span>

<span data-ttu-id="b57b8-107">Se l'elenco di parametri contiene un parametro facoltativo, anche ogni parametro che lo segue deve essere facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b57b8-107">If the parameter list contains an optional parameter, every parameter that follows it must also be optional.</span></span>

<span data-ttu-id="b57b8-108">Il modificatore `Optional` può essere usato nei contesti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b57b8-108">The `Optional` modifier can be used in these contexts:</span></span>

- [<span data-ttu-id="b57b8-109">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="b57b8-109">Declare Statement</span></span>](../statements/declare-statement.md)

- [<span data-ttu-id="b57b8-110">Istruzione Function</span><span class="sxs-lookup"><span data-stu-id="b57b8-110">Function Statement</span></span>](../statements/function-statement.md)

- [<span data-ttu-id="b57b8-111">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b57b8-111">Property Statement</span></span>](../statements/property-statement.md)

- [<span data-ttu-id="b57b8-112">Istruzione Sub</span><span class="sxs-lookup"><span data-stu-id="b57b8-112">Sub Statement</span></span>](../statements/sub-statement.md)

> [!NOTE]
> <span data-ttu-id="b57b8-113">Quando si chiama una routine con o senza parametri facoltativi, è possibile passare gli argomenti in base alla posizione o al nome.</span><span class="sxs-lookup"><span data-stu-id="b57b8-113">When calling a procedure with or without optional parameters, you can pass arguments by position or by name.</span></span> <span data-ttu-id="b57b8-114">Per ulteriori informazioni, vedere [passaggio di argomenti in base alla posizione e al nome](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span><span class="sxs-lookup"><span data-stu-id="b57b8-114">For more information, see [Passing Arguments by Position and by Name](../../programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b57b8-115">È anche possibile definire una routine con parametri facoltativi tramite l'overload.</span><span class="sxs-lookup"><span data-stu-id="b57b8-115">You can also define a procedure with optional parameters by using overloading.</span></span> <span data-ttu-id="b57b8-116">Se si dispone di un parametro facoltativo, è possibile definire due versioni di overload della stored procedure, una che accetta il parametro e l'altra.</span><span class="sxs-lookup"><span data-stu-id="b57b8-116">If you have one optional parameter, you can define two overloaded versions of the procedure, one that accepts the parameter and one that doesn’t.</span></span> <span data-ttu-id="b57b8-117">Per altre informazioni, vedere [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span><span class="sxs-lookup"><span data-stu-id="b57b8-117">For more information, see [Procedure Overloading](../../programming-guide/language-features/procedures/procedure-overloading.md).</span></span>

## <a name="example"></a><span data-ttu-id="b57b8-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="b57b8-118">Example</span></span>

<span data-ttu-id="b57b8-119">Nell'esempio seguente viene definita una routine con un parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b57b8-119">The following example defines a procedure that has an optional parameter.</span></span>

```vb
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

## <a name="example"></a><span data-ttu-id="b57b8-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="b57b8-120">Example</span></span>

<span data-ttu-id="b57b8-121">Nell'esempio seguente viene illustrato come chiamare una stored procedure con argomenti passati in base alla posizione e con argomenti passati in base al nome.</span><span class="sxs-lookup"><span data-stu-id="b57b8-121">The following example demonstrates how to call a procedure with arguments passed by position and with arguments passed by name.</span></span> <span data-ttu-id="b57b8-122">La procedura include due parametri facoltativi.</span><span class="sxs-lookup"><span data-stu-id="b57b8-122">The procedure has two optional parameters.</span></span>

[!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]

## <a name="see-also"></a><span data-ttu-id="b57b8-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b57b8-123">See also</span></span>

- [<span data-ttu-id="b57b8-124">Elenco parametri</span><span class="sxs-lookup"><span data-stu-id="b57b8-124">Parameter List</span></span>](../statements/parameter-list.md)
- [<span data-ttu-id="b57b8-125">Parametri facoltativi</span><span class="sxs-lookup"><span data-stu-id="b57b8-125">Optional Parameters</span></span>](../../programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="b57b8-126">Parole chiave</span><span class="sxs-lookup"><span data-stu-id="b57b8-126">Keywords</span></span>](../keywords/index.md)
