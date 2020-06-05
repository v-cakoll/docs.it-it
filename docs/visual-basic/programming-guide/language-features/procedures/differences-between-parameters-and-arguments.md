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
ms.openlocfilehash: dd0a62b6567f3e74763b7f2e9b96803c193c7976
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403356"
---
# <a name="differences-between-parameters-and-arguments-visual-basic"></a><span data-ttu-id="790f3-102">Differenze tra parametri e argomenti (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="790f3-102">Differences Between Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="790f3-103">Nella maggior parte dei casi, una routine deve avere alcune informazioni sulle circostanze in cui è stata chiamata.</span><span class="sxs-lookup"><span data-stu-id="790f3-103">In most cases, a procedure must have some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="790f3-104">Una procedura che esegue attività ripetute o condivise USA informazioni diverse per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="790f3-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="790f3-105">Queste informazioni sono costituite da variabili, costanti ed espressioni passate alla procedura quando viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="790f3-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="790f3-106">Per comunicare queste informazioni alla routine, la procedura definisce un *parametro*e il codice chiamante passa un *argomento* a tale parametro.</span><span class="sxs-lookup"><span data-stu-id="790f3-106">To communicate this information to the procedure, the procedure defines a *parameter*, and the calling code passes an *argument* to that parameter.</span></span> <span data-ttu-id="790f3-107">È possibile considerare il parametro come uno spazio di parcheggio e l'argomento come automobile.</span><span class="sxs-lookup"><span data-stu-id="790f3-107">You can think of the parameter as a parking space and the argument as an automobile.</span></span> <span data-ttu-id="790f3-108">Proprio come le diverse automobili possono parcheggiare in uno spazio di parcheggio in momenti diversi, il codice chiamante può passare un argomento diverso allo stesso parametro ogni volta che chiama la procedura.</span><span class="sxs-lookup"><span data-stu-id="790f3-108">Just as different automobiles can park in a parking space at different times, the calling code can pass a different argument to the same parameter every time that it calls the procedure.</span></span>  
  
## <a name="parameters"></a><span data-ttu-id="790f3-109">Parametri</span><span class="sxs-lookup"><span data-stu-id="790f3-109">Parameters</span></span>  
 <span data-ttu-id="790f3-110">Un *parametro* rappresenta un valore che la routine prevede di passare quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="790f3-110">A *parameter* represents a value that the procedure expects you to pass when you call it.</span></span> <span data-ttu-id="790f3-111">La dichiarazione della stored procedure definisce i relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="790f3-111">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="790f3-112">Quando si definisce una `Function` `Sub` routine o, si specifica un *elenco di parametri* racchiusi tra parentesi immediatamente dopo il nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="790f3-112">When you define a `Function` or `Sub` procedure, you specify a *parameter list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="790f3-113">Per ogni parametro, è necessario specificare un nome, un tipo di dati e un meccanismo di passaggio ([ByVal](../../../language-reference/modifiers/byval.md) o [ByRef](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="790f3-113">For each parameter, you specify a name, a data type, and a passing mechanism ([ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md)).</span></span> <span data-ttu-id="790f3-114">È anche possibile indicare che un parametro è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="790f3-114">You can also indicate that a parameter is optional.</span></span> <span data-ttu-id="790f3-115">Questo significa che non è necessario passare un valore al codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="790f3-115">This means that the calling code does not have to pass a value for it.</span></span>  
  
 <span data-ttu-id="790f3-116">Il nome di ogni parametro funge da *variabile locale* nella procedura.</span><span class="sxs-lookup"><span data-stu-id="790f3-116">The name of each parameter serves as a *local variable* in the procedure.</span></span> <span data-ttu-id="790f3-117">Il nome del parametro viene usato allo stesso modo di qualsiasi altra variabile.</span><span class="sxs-lookup"><span data-stu-id="790f3-117">You use the parameter name the same way you use any other variable.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="790f3-118">Arguments</span><span class="sxs-lookup"><span data-stu-id="790f3-118">Arguments</span></span>  
 <span data-ttu-id="790f3-119">Un *argomento* rappresenta il valore passato a un parametro di routine quando si chiama la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="790f3-119">An *argument* represents the value that you pass to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="790f3-120">Il codice chiamante fornisce gli argomenti quando chiama la routine.</span><span class="sxs-lookup"><span data-stu-id="790f3-120">The calling code supplies the arguments when it calls the procedure.</span></span>  
  
 <span data-ttu-id="790f3-121">Quando si chiama una `Function` `Sub` routine o, si include un *elenco di argomenti* tra parentesi immediatamente dopo il nome della procedura.</span><span class="sxs-lookup"><span data-stu-id="790f3-121">When you call a `Function` or `Sub` procedure, you include an *argument list* in parentheses immediately following the procedure name.</span></span> <span data-ttu-id="790f3-122">Ogni argomento corrisponde al parametro nella stessa posizione dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="790f3-122">Each argument corresponds to the parameter in the same position in the list.</span></span>  
  
 <span data-ttu-id="790f3-123">A differenza della definizione del parametro, gli argomenti non hanno nomi.</span><span class="sxs-lookup"><span data-stu-id="790f3-123">In contrast to parameter definition, arguments do not have names.</span></span> <span data-ttu-id="790f3-124">Ogni argomento è un'espressione, che può contenere zero o più variabili, costanti e valori letterali.</span><span class="sxs-lookup"><span data-stu-id="790f3-124">Each argument is an expression, which can contain zero or more variables, constants, and literals.</span></span> <span data-ttu-id="790f3-125">Il tipo di dati dell'espressione valutata deve in genere corrispondere al tipo di dati definito per il parametro corrispondente e, in ogni caso, deve essere convertibile nel tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="790f3-125">The data type of the evaluated expression should typically match the data type defined for the corresponding parameter, and in any case it must be convertible to the parameter type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="790f3-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="790f3-126">See also</span></span>

- [<span data-ttu-id="790f3-127">Procedure</span><span class="sxs-lookup"><span data-stu-id="790f3-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="790f3-128">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="790f3-128">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="790f3-129">Routine Function</span><span class="sxs-lookup"><span data-stu-id="790f3-129">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="790f3-130">Routine Property</span><span class="sxs-lookup"><span data-stu-id="790f3-130">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="790f3-131">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="790f3-131">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="790f3-132">Procedura: definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="790f3-132">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="790f3-133">Procedura: passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="790f3-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="790f3-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="790f3-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="790f3-135">Routine ricorsive</span><span class="sxs-lookup"><span data-stu-id="790f3-135">Recursive Procedures</span></span>](./recursive-procedures.md)
- [<span data-ttu-id="790f3-136">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="790f3-136">Procedure Overloading</span></span>](./procedure-overloading.md)
