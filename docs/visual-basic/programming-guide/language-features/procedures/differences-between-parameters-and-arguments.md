---
title: Differenze tra parametri e argomenti
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- parameters [Visual Basic], and arguments
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], and parameters
- procedure parameters
- parameters [Visual Basic], definition
ms.assetid: c237c056-74f4-4749-9f2c-15864f139a31
ms.openlocfilehash: c4249dbf86bd1bfa7ef08e94059d2880333e9a92
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74341368"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="4878f-102">Differenze tra parametri e argomenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4878f-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="4878f-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span><span class="sxs-lookup"><span data-stu-id="4878f-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="4878f-104">A procedure that performs repeated or shared tasks uses different information for each call.</span><span class="sxs-lookup"><span data-stu-id="4878f-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="4878f-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span><span class="sxs-lookup"><span data-stu-id="4878f-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="4878f-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span><span class="sxs-lookup"><span data-stu-id="4878f-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="4878f-107">You can think of the parameter as a parking space and the argument as an automobile.</span><span class="sxs-lookup"><span data-stu-id="4878f-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="4878f-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span><span class="sxs-lookup"><span data-stu-id="4878f-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="4878f-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="4878f-109">Parameters</span></span>  
 <span data-ttu-id="4878f-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span><span class="sxs-lookup"><span data-stu-id="4878f-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="4878f-111">The procedure's declaration defines its parameters.</span><span class="sxs-lookup"><span data-stu-id="4878f-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="4878f-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span><span class="sxs-lookup"><span data-stu-id="4878f-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="4878f-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="4878f-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="4878f-114">You can also indicate that a parameter is optional.</span><span class="sxs-lookup"><span data-stu-id="4878f-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="4878f-115">This means that the calling code does not have to pass a value for it.</span><span class="sxs-lookup"><span data-stu-id="4878f-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="4878f-116">The name of each parameter serves as a *local variable* in the procedure.</span><span class="sxs-lookup"><span data-stu-id="4878f-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="4878f-117">You use the parameter name the same way you use any other variable.</span><span class="sxs-lookup"><span data-stu-id="4878f-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="4878f-118">argomenti</span><span class="sxs-lookup"><span data-stu-id="4878f-118">Arguments</span></span>  
 <span data-ttu-id="4878f-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span><span class="sxs-lookup"><span data-stu-id="4878f-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="4878f-120">The calling code supplies the arguments when it calls the procedure.</span><span class="sxs-lookup"><span data-stu-id="4878f-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="4878f-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span><span class="sxs-lookup"><span data-stu-id="4878f-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="4878f-122">Each argument corresponds to the parameter in the same position in the list.</span><span class="sxs-lookup"><span data-stu-id="4878f-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="4878f-123">In contrast to parameter definition, arguments do not have names.</span><span class="sxs-lookup"><span data-stu-id="4878f-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="4878f-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span><span class="sxs-lookup"><span data-stu-id="4878f-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="4878f-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span><span class="sxs-lookup"><span data-stu-id="4878f-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4878f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4878f-126">See also</span></span>

- [<span data-ttu-id="4878f-127">Routine</span><span class="sxs-lookup"><span data-stu-id="4878f-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="4878f-128">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="4878f-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="4878f-129">Routine Function</span><span class="sxs-lookup"><span data-stu-id="4878f-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="4878f-130">Routine Property</span><span class="sxs-lookup"><span data-stu-id="4878f-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="4878f-131">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="4878f-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="4878f-132">Procedura: Definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="4878f-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="4878f-133">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="4878f-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="4878f-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="4878f-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="4878f-135">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="4878f-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="4878f-136">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="4878f-136">Procedure Overloading</span></span>](./procedure-overloading.md)
