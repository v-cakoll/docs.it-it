---
title: Parametri e argomenti delle routine (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: b0ab186945b456d7fb4dde3f52724b08a99e2827
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652500"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="f34b0-102">Parametri e argomenti delle routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f34b0-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="f34b0-103">Nella maggior parte dei casi, una stored procedure richiede alcune informazioni sulle circostanze in cui è stato chiamato.</span><span class="sxs-lookup"><span data-stu-id="f34b0-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="f34b0-104">Una routine che esegue attività ripetute o condivise utilizza informazioni diverse per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="f34b0-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="f34b0-105">Queste informazioni è costituito da variabili, costanti ed espressioni che viene passato alla routine quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="f34b0-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="f34b0-106">Oggetto *parametro* rappresenta un valore che la procedura prevede di specificare quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="f34b0-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="f34b0-107">La dichiarazione della routine definisce i parametri.</span><span class="sxs-lookup"><span data-stu-id="f34b0-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="f34b0-108">È possibile definire una routine con senza parametri, un parametro di uno o più.</span><span class="sxs-lookup"><span data-stu-id="f34b0-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="f34b0-109">La parte della definizione della routine che specifica i parametri viene chiamata il *elenco parametri*.</span><span class="sxs-lookup"><span data-stu-id="f34b0-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="f34b0-110">Un *argomento* rappresenta il valore fornito per un parametro di routine quando si chiama la routine.</span><span class="sxs-lookup"><span data-stu-id="f34b0-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="f34b0-111">Il codice chiamante fornisce gli argomenti quando viene chiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="f34b0-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="f34b0-112">La parte della chiamata di routine che specifica gli argomenti viene chiamata il *elenco di argomenti*.</span><span class="sxs-lookup"><span data-stu-id="f34b0-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="f34b0-113">La figura seguente illustra la procedura di chiamata del codice `safeSquareRoot` da due posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="f34b0-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="f34b0-114">La prima chiamata passa il valore della variabile `x` (4.0) per il parametro `number`e il valore restituito in `root` (2.0) viene assegnato alla variabile `y`.</span><span class="sxs-lookup"><span data-stu-id="f34b0-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="f34b0-115">La seconda chiamata passa il valore letterale 9.0 per `number`e assegna il valore restituito (3.0) variabile `z`.</span><span class="sxs-lookup"><span data-stu-id="f34b0-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 <span data-ttu-id="f34b0-116">![Diagramma grafico del passaggio argomento al parametro](./media/parametersargue.gif "ParametersArgue")</span><span class="sxs-lookup"><span data-stu-id="f34b0-116">![Graphic diagram of passing argument to parameter](./media/parametersargue.gif "ParametersArgue")</span></span>  
<span data-ttu-id="f34b0-117">Passa un argomento a un parametro</span><span class="sxs-lookup"><span data-stu-id="f34b0-117">Passing an argument to a parameter</span></span>  
  
 <span data-ttu-id="f34b0-118">Per ulteriori informazioni, vedere [le differenze tra parametri e argomenti](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="f34b0-118">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="f34b0-119">Tipo di dati di parametro</span><span class="sxs-lookup"><span data-stu-id="f34b0-119">Parameter Data Type</span></span>  
 <span data-ttu-id="f34b0-120">Si definisce un tipo di dati per un parametro utilizzando il `As` clausola nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="f34b0-120">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="f34b0-121">Ad esempio, la funzione seguente accetta una stringa e un numero intero.</span><span class="sxs-lookup"><span data-stu-id="f34b0-121">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 <span data-ttu-id="f34b0-122">Se il controllo dei tipi passa ([istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) è `Off,` il `As` clausola è facoltativa, ad eccezione del fatto che un qualsiasi parametro utilizzata da tutti i parametri devono essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="f34b0-122">If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="f34b0-123">Il controllo di tipo `On`, `As` clausola è obbligatoria per tutti i parametri di stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f34b0-123">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="f34b0-124">Se il codice chiamante prevede di fornire un argomento con un tipo di dati diverso da quello del parametro corrispondente, come `Byte` per un `String` parametro, è necessario eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f34b0-124">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
-   <span data-ttu-id="f34b0-125">Specificare solo gli argomenti con i tipi di dati che vengono ampliati al tipo di dati del parametro.</span><span class="sxs-lookup"><span data-stu-id="f34b0-125">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
-   <span data-ttu-id="f34b0-126">Impostare `Option Strict Off` per consentire conversioni implicite verso un; o</span><span class="sxs-lookup"><span data-stu-id="f34b0-126">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
-   <span data-ttu-id="f34b0-127">Utilizzare una parola chiave di conversione per convertire esplicitamente il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="f34b0-127">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="f34b0-128">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="f34b0-128">Type Parameters</span></span>  
 <span data-ttu-id="f34b0-129">Oggetto *routine generica* definisce anche una o più *parametri di tipo* oltre ai normali parametri.</span><span class="sxs-lookup"><span data-stu-id="f34b0-129">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="f34b0-130">Una routine generica consente al codice chiamante passare i tipi di dati diversi ogni volta che viene chiamata la routine, in modo che la possibilità di personalizzare i tipi di dati per i requisiti di ogni singola chiamata.</span><span class="sxs-lookup"><span data-stu-id="f34b0-130">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="f34b0-131">Vedere [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="f34b0-131">See [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f34b0-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f34b0-132">See Also</span></span>  
 [<span data-ttu-id="f34b0-133">Routine</span><span class="sxs-lookup"><span data-stu-id="f34b0-133">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="f34b0-134">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="f34b0-134">Sub Procedures</span></span>](./sub-procedures.md)  
 [<span data-ttu-id="f34b0-135">Routine Function</span><span class="sxs-lookup"><span data-stu-id="f34b0-135">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="f34b0-136">Routine Property</span><span class="sxs-lookup"><span data-stu-id="f34b0-136">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="f34b0-137">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="f34b0-137">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="f34b0-138">Procedura: Definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="f34b0-138">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)  
 [<span data-ttu-id="f34b0-139">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="f34b0-139">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="f34b0-140">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="f34b0-140">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="f34b0-141">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="f34b0-141">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="f34b0-142">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f34b0-142">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
