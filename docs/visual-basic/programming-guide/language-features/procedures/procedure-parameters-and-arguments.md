---
title: Parametri e argomenti delle routine
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
ms.openlocfilehash: 178206ca2ee103bbdb5a4ac03bca0df903c8c5d8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406716"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a><span data-ttu-id="9619e-102">Parametri e argomenti delle routine (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9619e-102">Procedure Parameters and Arguments (Visual Basic)</span></span>
<span data-ttu-id="9619e-103">Nella maggior parte dei casi, una procedura richiede alcune informazioni sulle circostanze in cui è stata chiamata.</span><span class="sxs-lookup"><span data-stu-id="9619e-103">In most cases, a procedure needs some information about the circumstances in which it has been called.</span></span> <span data-ttu-id="9619e-104">Una procedura che esegue attività ripetute o condivise USA informazioni diverse per ogni chiamata.</span><span class="sxs-lookup"><span data-stu-id="9619e-104">A procedure that performs repeated or shared tasks uses different information for each call.</span></span> <span data-ttu-id="9619e-105">Queste informazioni sono costituite da variabili, costanti ed espressioni passate alla procedura quando viene chiamata.</span><span class="sxs-lookup"><span data-stu-id="9619e-105">This information consists of variables, constants, and expressions that you pass to the procedure when you call it.</span></span>  
  
 <span data-ttu-id="9619e-106">Un *parametro* rappresenta un valore che la routine prevede di fornire quando viene chiamato.</span><span class="sxs-lookup"><span data-stu-id="9619e-106">A *parameter* represents a value that the procedure expects you to supply when you call it.</span></span> <span data-ttu-id="9619e-107">La dichiarazione della stored procedure definisce i relativi parametri.</span><span class="sxs-lookup"><span data-stu-id="9619e-107">The procedure's declaration defines its parameters.</span></span>  
  
 <span data-ttu-id="9619e-108">È possibile definire una routine senza parametri, un parametro o più di uno.</span><span class="sxs-lookup"><span data-stu-id="9619e-108">You can define a procedure with no parameters, one parameter, or more than one.</span></span> <span data-ttu-id="9619e-109">La parte della definizione della routine che specifica i parametri è denominata *elenco di parametri*.</span><span class="sxs-lookup"><span data-stu-id="9619e-109">The part of the procedure definition that specifies the parameters is called the *parameter list*.</span></span>  
  
 <span data-ttu-id="9619e-110">Un *argomento* rappresenta il valore fornito a un parametro di routine quando si chiama la stored procedure.</span><span class="sxs-lookup"><span data-stu-id="9619e-110">An *argument* represents the value you supply to a procedure parameter when you call the procedure.</span></span> <span data-ttu-id="9619e-111">Il codice chiamante fornisce gli argomenti quando chiama la routine.</span><span class="sxs-lookup"><span data-stu-id="9619e-111">The calling code supplies the arguments when it calls the procedure.</span></span> <span data-ttu-id="9619e-112">La parte della chiamata di procedura che specifica gli argomenti è denominata *elenco di argomenti*.</span><span class="sxs-lookup"><span data-stu-id="9619e-112">The part of the procedure call that specifies the arguments is called the *argument list*.</span></span>  
  
 <span data-ttu-id="9619e-113">Nella figura seguente viene illustrato il codice che chiama la procedura `safeSquareRoot` da due posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="9619e-113">The following illustration shows code calling the procedure `safeSquareRoot` from two different places.</span></span> <span data-ttu-id="9619e-114">La prima chiamata passa il valore della variabile `x` (4,0) al parametro `number` e il valore restituito in `root` (2,0) viene assegnato alla variabile `y` .</span><span class="sxs-lookup"><span data-stu-id="9619e-114">The first call passes the value of the variable `x` (4.0) to the parameter `number`, and the return value in `root` (2.0) is assigned to the variable `y`.</span></span> <span data-ttu-id="9619e-115">La seconda chiamata passa il valore letterale 9,0 a `number` e assegna il valore restituito (3,0) alla variabile `z` .</span><span class="sxs-lookup"><span data-stu-id="9619e-115">The second call passes the literal value 9.0 to `number`, and assigns the return value (3.0) to variable `z`.</span></span>  
  
 ![Diagramma che mostra il passaggio di un argomento a un parametro](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 <span data-ttu-id="9619e-117">Per ulteriori informazioni, vedere [differenze tra parametri e argomenti](./differences-between-parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="9619e-117">For more information, see [Differences Between Parameters and Arguments](./differences-between-parameters-and-arguments.md).</span></span>  
  
## <a name="parameter-data-type"></a><span data-ttu-id="9619e-118">Tipo di dati del parametro</span><span class="sxs-lookup"><span data-stu-id="9619e-118">Parameter Data Type</span></span>  
 <span data-ttu-id="9619e-119">Per definire un tipo di dati per un parametro, usare la `As` clausola nella relativa dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="9619e-119">You define a data type for a parameter by using the `As` clause in its declaration.</span></span> <span data-ttu-id="9619e-120">La funzione seguente, ad esempio, accetta una stringa e un numero intero.</span><span class="sxs-lookup"><span data-stu-id="9619e-120">For example, the following function accepts a string and an integer.</span></span>  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 <span data-ttu-id="9619e-121">Se l'opzione di controllo del tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) è `Off,` la `As` clausola è facoltativa, ad eccezione del fatto che se un parametro lo usa, tutti i parametri devono utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="9619e-121">If the type checking switch ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) is `Off,` the `As` clause is optional, except that if any one parameter uses it, all parameters must use it.</span></span> <span data-ttu-id="9619e-122">Se il controllo del tipo è `On` , la `As` clausola è obbligatoria per tutti i parametri di routine.</span><span class="sxs-lookup"><span data-stu-id="9619e-122">If type checking is `On`, the `As` clause is required for all procedure parameters.</span></span>  
  
 <span data-ttu-id="9619e-123">Se il codice chiamante prevede di fornire un argomento con un tipo di dati diverso da quello del parametro corrispondente, ad esempio `Byte` un `String` parametro, deve eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9619e-123">If the calling code expects to supply an argument with a data type different from that of its corresponding parameter, such as `Byte` to a `String` parameter, it must do one of the following:</span></span>  
  
- <span data-ttu-id="9619e-124">Fornire solo argomenti con tipi di dati che si ampliano al tipo di dati del parametro;</span><span class="sxs-lookup"><span data-stu-id="9619e-124">Supply only arguments with data types that widen to the parameter data type;</span></span>  
  
- <span data-ttu-id="9619e-125">Impostare `Option Strict Off` per consentire le conversioni implicite verso un tipo di caratteri più piccolo oppure</span><span class="sxs-lookup"><span data-stu-id="9619e-125">Set `Option Strict Off` to allow implicit narrowing conversions; or</span></span>  
  
- <span data-ttu-id="9619e-126">Usare una parola chiave di conversione per convertire in modo esplicito il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="9619e-126">Use a conversion keyword to explicitly convert the data type.</span></span>  
  
### <a name="type-parameters"></a><span data-ttu-id="9619e-127">Parametri di tipo</span><span class="sxs-lookup"><span data-stu-id="9619e-127">Type Parameters</span></span>  
 <span data-ttu-id="9619e-128">Una *routine generica* definisce anche uno o più *parametri di tipo* oltre ai parametri normali.</span><span class="sxs-lookup"><span data-stu-id="9619e-128">A *generic procedure* also defines one or more *type parameters* in addition to its normal parameters.</span></span> <span data-ttu-id="9619e-129">Una routine generica consente al codice chiamante di passare tipi di dati diversi ogni volta che viene chiamata la procedura, in modo da poter adattare i tipi di dati ai requisiti di ogni singola chiamata.</span><span class="sxs-lookup"><span data-stu-id="9619e-129">A generic procedure allows the calling code to pass different data types each time it calls the procedure, so it can tailor the data types to the requirements of each individual call.</span></span> <span data-ttu-id="9619e-130">Vedere [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="9619e-130">See [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9619e-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9619e-131">See also</span></span>

- [<span data-ttu-id="9619e-132">Procedure</span><span class="sxs-lookup"><span data-stu-id="9619e-132">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9619e-133">Routine Sub</span><span class="sxs-lookup"><span data-stu-id="9619e-133">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="9619e-134">Routine Function</span><span class="sxs-lookup"><span data-stu-id="9619e-134">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="9619e-135">Routine Property</span><span class="sxs-lookup"><span data-stu-id="9619e-135">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="9619e-136">Routine di operatore</span><span class="sxs-lookup"><span data-stu-id="9619e-136">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="9619e-137">Procedura: definire un parametro per una routine</span><span class="sxs-lookup"><span data-stu-id="9619e-137">How to: Define a Parameter for a Procedure</span></span>](./how-to-define-a-parameter-for-a-procedure.md)
- [<span data-ttu-id="9619e-138">Procedura: passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="9619e-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="9619e-139">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="9619e-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9619e-140">Overload della routine</span><span class="sxs-lookup"><span data-stu-id="9619e-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="9619e-141">Conversioni di tipi in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9619e-141">Type Conversions in Visual Basic</span></span>](../data-types/type-conversions.md)
