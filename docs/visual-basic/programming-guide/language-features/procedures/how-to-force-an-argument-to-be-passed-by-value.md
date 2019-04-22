---
title: 'Procedura: Forzare un argomento può essere passato per valore (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 497ae11b858b7d164ba3b5607ff2109254a154de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842045"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a><span data-ttu-id="68fb3-102">Procedura: Forzare un argomento può essere passato per valore (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68fb3-102">How to: Force an Argument to Be Passed by Value (Visual Basic)</span></span>
<span data-ttu-id="68fb3-103">La dichiarazione di routine determina il meccanismo di passaggio.</span><span class="sxs-lookup"><span data-stu-id="68fb3-103">The procedure declaration determines the passing mechanism.</span></span> <span data-ttu-id="68fb3-104">Se un parametro dichiarato [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic prevede di passare l'argomento corrispondente per riferimento.</span><span class="sxs-lookup"><span data-stu-id="68fb3-104">If a parameter is declared [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic expects to pass the corresponding argument by reference.</span></span> <span data-ttu-id="68fb3-105">In questo modo la procedura modificare il valore dell'elemento di programmazione sottostante all'argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="68fb3-105">This allows the procedure to change the value of the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="68fb3-106">Se si vuole proteggere l'elemento sottostante da tali modifiche, è possibile eseguire l'override di `ByRef` meccanismo di passaggio della procedura chiamata racchiudendo il nome dell'argomento racchiuso tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-106">If you wish to protect the underlying element against such change, you can override the `ByRef` passing mechanism in the procedure call by enclosing the argument name in parentheses.</span></span> <span data-ttu-id="68fb3-107">Tali parentesi vengono aggiunte le parentesi che racchiudono l'elenco di argomenti nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="68fb3-107">These parentheses are in addition to the parentheses enclosing the argument list in the call.</span></span>  
  
 <span data-ttu-id="68fb3-108">Il codice chiamante non è possibile sostituire un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) meccanismo.</span><span class="sxs-lookup"><span data-stu-id="68fb3-108">The calling code cannot override a [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mechanism.</span></span>  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a><span data-ttu-id="68fb3-109">Per forzare un argomento da passare per valore</span><span class="sxs-lookup"><span data-stu-id="68fb3-109">To force an argument to be passed by value</span></span>  
  
-   <span data-ttu-id="68fb3-110">Se viene dichiarato il parametro corrispondente `ByVal` nella procedura, non è necessario eseguire passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-110">If the corresponding parameter is declared `ByVal` in the procedure, you do not need to take any additional steps.</span></span> <span data-ttu-id="68fb3-111">Visual Basic prevede già passare l'argomento per valore.</span><span class="sxs-lookup"><span data-stu-id="68fb3-111">Visual Basic already expects to pass the argument by value.</span></span>  
  
-   <span data-ttu-id="68fb3-112">Se viene dichiarato il parametro corrispondente `ByRef` nella procedura, racchiudere l'argomento racchiuso tra parentesi nella chiamata di procedura.</span><span class="sxs-lookup"><span data-stu-id="68fb3-112">If the corresponding parameter is declared `ByRef` in the procedure, enclose the argument in parentheses in the procedure call.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68fb3-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="68fb3-113">Example</span></span>  
 <span data-ttu-id="68fb3-114">Nell'esempio seguente esegue l'override di un `ByRef` dichiarazione del parametro.</span><span class="sxs-lookup"><span data-stu-id="68fb3-114">The following example overrides a `ByRef` parameter declaration.</span></span> <span data-ttu-id="68fb3-115">Nella chiamata che forza `ByVal`, notare i due livelli di parentesi.</span><span class="sxs-lookup"><span data-stu-id="68fb3-115">In the call that forces `ByVal`, note the two levels of parentheses.</span></span>  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 <span data-ttu-id="68fb3-116">Quando `str` è racchiuso tra parentesi aggiuntive nell'elenco degli argomenti, il `setNewString` procedure non è possibile modificarne il valore nel codice chiamante, e `MsgBox` Visualizza "Non può essere sostituito se viene passato ByVal".</span><span class="sxs-lookup"><span data-stu-id="68fb3-116">When `str` is enclosed in extra parentheses within the argument list, the `setNewString` procedure cannot change its value in the calling code, and `MsgBox` displays "Cannot be replaced if passed ByVal".</span></span> <span data-ttu-id="68fb3-117">Quando `str` non è racchiuso tra parentesi aggiuntive, la routine può modificarlo, e `MsgBox` viene visualizzato "This is a un nuovo valore per l'argomento inString".</span><span class="sxs-lookup"><span data-stu-id="68fb3-117">When `str` is not enclosed in extra parentheses, the procedure can change it, and `MsgBox` displays "This is a new value for the inString argument."</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="68fb3-118">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="68fb3-118">Compiling the Code</span></span>  
 <span data-ttu-id="68fb3-119">Quando si passa una variabile per riferimento, è necessario usare il `ByRef` parola chiave per specificare questo meccanismo.</span><span class="sxs-lookup"><span data-stu-id="68fb3-119">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="68fb3-120">L'impostazione predefinita in Visual Basic consiste nel passare argomenti per valore.</span><span class="sxs-lookup"><span data-stu-id="68fb3-120">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="68fb3-121">Tuttavia, è buona norma includere il [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oppure [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) parola chiave with ogni parametro dichiarato.</span><span class="sxs-lookup"><span data-stu-id="68fb3-121">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="68fb3-122">Questo rende il codice più facile da leggere.</span><span class="sxs-lookup"><span data-stu-id="68fb3-122">This makes your code easier to read.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="68fb3-123">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="68fb3-123">Robust Programming</span></span>  
 <span data-ttu-id="68fb3-124">Se una procedura dichiara un parametro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), l'esecuzione corretta del codice potrebbe dipendere la possibilità di modificare l'elemento sottostante nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="68fb3-124">If a procedure declares a parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), the correct execution of the code might depend on being able to change the underlying element in the calling code.</span></span> <span data-ttu-id="68fb3-125">Se il codice chiamante esegue l'override di questo meccanismo di chiamata racchiudendo l'argomento racchiuso tra parentesi o se passa un argomento non è modificabile, la procedura non è possibile modificare l'elemento sottostante.</span><span class="sxs-lookup"><span data-stu-id="68fb3-125">If the calling code overrides this calling mechanism by enclosing the argument in parentheses, or if it passes a nonmodifiable argument, the procedure cannot change the underlying element.</span></span> <span data-ttu-id="68fb3-126">Ciò potrebbe produrre risultati imprevisti nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="68fb3-126">This might produce unexpected results in the calling code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="68fb3-127">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="68fb3-127">.NET Framework Security</span></span>  
 <span data-ttu-id="68fb3-128">È sempre un potenziale rischio per consentire a una stored procedure per modificare il valore sottostante a un argomento nel codice chiamante.</span><span class="sxs-lookup"><span data-stu-id="68fb3-128">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="68fb3-129">Assicurarsi che si prevede che questo valore per essere modificato e prepararsi a verificare la validità prima di poterla usare.</span><span class="sxs-lookup"><span data-stu-id="68fb3-129">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68fb3-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="68fb3-130">See also</span></span>

- [<span data-ttu-id="68fb3-131">Routine</span><span class="sxs-lookup"><span data-stu-id="68fb3-131">Procedures</span></span>](./index.md)
- [<span data-ttu-id="68fb3-132">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="68fb3-132">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="68fb3-133">Procedura: Passare argomenti a una routine</span><span class="sxs-lookup"><span data-stu-id="68fb3-133">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="68fb3-134">Passaggio di argomenti per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="68fb3-134">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="68fb3-135">Differenze tra argomenti modificabili e non modificabili</span><span class="sxs-lookup"><span data-stu-id="68fb3-135">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="68fb3-136">Differenze tra il passaggio di un argomento per valore e per riferimento</span><span class="sxs-lookup"><span data-stu-id="68fb3-136">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="68fb3-137">Procedura: Modificare il valore di un argomento di routine</span><span class="sxs-lookup"><span data-stu-id="68fb3-137">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="68fb3-138">Procedura: Proteggere un argomento di routine modifica del valore</span><span class="sxs-lookup"><span data-stu-id="68fb3-138">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="68fb3-139">Passaggio di argomenti in base alla posizione e al nome</span><span class="sxs-lookup"><span data-stu-id="68fb3-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="68fb3-140">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="68fb3-140">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
