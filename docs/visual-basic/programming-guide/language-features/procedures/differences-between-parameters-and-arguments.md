---
title: Differenze tra parametri e argomenti (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6613c64a24ef18239422b69f8b5320eadc95b92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="49338-102">Differenze tra parametri e argomenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49338-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="49338-103">Nella maggior parte dei casi, una routine deve avere alcune informazioni sulle circostanze in cui è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="49338-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="49338-104">Una routine che esegue attività ripetute o condivise utilizza informazioni diverse per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="49338-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="49338-105">Queste informazioni è costituito da variabili, costanti ed espressioni che viene passato alla routine quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="49338-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="49338-106">Per comunicare le informazioni per la procedura, la routine definisce un *parametro*, e il codice chiamante passa una *argomento* a tale parametro.</span><span class="sxs-lookup"><span data-stu-id="49338-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="49338-107">È possibile considerare il parametro come spazio di parcheggio e l'argomento a un'automobile.</span><span class="sxs-lookup"><span data-stu-id="49338-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="49338-108">Così come diverse automobili possono parcheggiare in uno spazio di parcheggio in momenti diversi, il codice chiamante può passare un argomento differente per lo stesso parametro ogni volta che si chiama la routine.</span><span class="sxs-lookup"><span data-stu-id="49338-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="49338-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="49338-109">Parameters</span></span>  
 <span data-ttu-id="49338-110">Oggetto *parametro* rappresenta un valore che la procedura prevede di passare al momento della chiamata.</span><span class="sxs-lookup"><span data-stu-id="49338-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="49338-111">La dichiarazione della routine definisce i parametri.</span><span class="sxs-lookup"><span data-stu-id="49338-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="49338-112">Quando si definisce un `Function` o `Sub` procedura, si specifica un *elenco parametri* tra parentesi immediatamente dopo il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="49338-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="49338-113">Per ogni parametro, specificare un nome, un tipo di dati e un meccanismo di passaggio ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="49338-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="49338-114">È anche possibile indicare che un parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="49338-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="49338-115">Ciò significa che il codice chiamante non dispone di passare un valore per tale.</span><span class="sxs-lookup"><span data-stu-id="49338-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="49338-116">Il nome di ogni parametro viene utilizzato come un *variabile locale* nella procedura.</span><span class="sxs-lookup"><span data-stu-id="49338-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="49338-117">Utilizzare il nome del parametro la stessa modalità di utilizzo di qualsiasi altra variabile.</span><span class="sxs-lookup"><span data-stu-id="49338-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="49338-118">Argomenti</span><span class="sxs-lookup"><span data-stu-id="49338-118">Arguments</span></span>  
 <span data-ttu-id="49338-119">Un *argomento* rappresenta il valore passato a un parametro di procedura quando si chiama la routine.</span><span class="sxs-lookup"><span data-stu-id="49338-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="49338-120">Il codice chiamante fornisce gli argomenti quando viene chiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="49338-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="49338-121">Quando si chiama un `Function` o `Sub` procedura, include un *elenco di argomenti* tra parentesi immediatamente dopo il nome della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="49338-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="49338-122">Ciascun argomento corrisponde al parametro nella stessa posizione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="49338-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="49338-123">A differenza di definizione dei parametri, argomenti non hanno nomi.</span><span class="sxs-lookup"><span data-stu-id="49338-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="49338-124">Ogni argomento è un'espressione che può contenere zero o più variabili, costanti e valori letterali.</span><span class="sxs-lookup"><span data-stu-id="49338-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="49338-125">Il tipo di dati dell'espressione valutata in genere deve corrispondere al tipo di dati definito per il parametro corrispondente, e in ogni caso deve essere convertibile nel tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="49338-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49338-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49338-126">See Also</span></span>  
 [<span data-ttu-id="49338-127">Routine</span><span class="sxs-lookup"><span data-stu-id="49338-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="49338-128">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="49338-128">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="49338-129">Routine Function</span><span class="sxs-lookup"><span data-stu-id="49338-129">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="49338-130">Routine Property</span><span class="sxs-lookup"><span data-stu-id="49338-130">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="49338-131">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="49338-131">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="49338-132">Procedura: Definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="49338-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="49338-133">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="49338-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="49338-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="49338-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="49338-135">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="49338-135">Recursive Procedures</span></span>](./recursive-procedures.md)  
 [<span data-ttu-id="49338-136">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="49338-136">Procedure Overloading</span></span>](./procedure-overloading.md)
