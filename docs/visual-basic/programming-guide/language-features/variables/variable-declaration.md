---
title: Dichiarazione di variabili in Visual Basic | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: dac536b99eb4515c75381dc4e28720a92e1001f0
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="cc93c-102">Dichiarazione di variabili in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cc93c-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="cc93c-103">Si dichiara una variabile per specificare il nome e le caratteristiche.</span><span class="sxs-lookup"><span data-stu-id="cc93c-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="cc93c-104">Istruzione di dichiarazione delle variabili è il [Dim (istruzione)](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="cc93c-105">La posizione e il contenuto determinano le caratteristiche della variabile.</span><span class="sxs-lookup"><span data-stu-id="cc93c-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="cc93c-106">Per considerazioni e le regole di denominazione variabili, vedere [nomi di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="cc93c-107">Livelli di dichiarazione</span><span class="sxs-lookup"><span data-stu-id="cc93c-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="cc93c-108">Locale e le variabili membro</span><span class="sxs-lookup"><span data-stu-id="cc93c-108">Local and Member Variables</span></span>  
 <span data-ttu-id="cc93c-109">Oggetto *variabile locale* è una variabile dichiarata all'interno di una routine.</span><span class="sxs-lookup"><span data-stu-id="cc93c-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="cc93c-110">Oggetto *variabile membro* è un membro di un [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] di tipo viene dichiarato a livello di modulo, all'interno di una classe, struttura o un modulo, ma non all'interno di qualsiasi routine interne di tale classe, struttura o un modulo.</span><span class="sxs-lookup"><span data-stu-id="cc93c-110">A *member variable* is a member of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="cc93c-111">Condivisi e le variabili di istanza</span><span class="sxs-lookup"><span data-stu-id="cc93c-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="cc93c-112">In una classe o struttura, la categoria di una variabile membro dipende o meno è condiviso.</span><span class="sxs-lookup"><span data-stu-id="cc93c-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="cc93c-113">Se viene dichiarata con la [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) (parola chiave), è un *variabile condivisa*, ed esiste una sola copia condivisa tra tutte le istanze della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="cc93c-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="cc93c-114">In caso contrario è un *variabile di istanza*, e viene creata una copia separata per ogni istanza della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="cc93c-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="cc93c-115">È disponibile solo per l'istanza della classe o struttura in cui è stata creata una copia specifica di una variabile di istanza.</span><span class="sxs-lookup"><span data-stu-id="cc93c-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="cc93c-116">È indipendente da una copia della variabile di istanza in qualsiasi altra istanza della classe o struttura.</span><span class="sxs-lookup"><span data-stu-id="cc93c-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="cc93c-117">Dichiarazione del tipo di dati</span><span class="sxs-lookup"><span data-stu-id="cc93c-117">Declaring Data Type</span></span>  
 <span data-ttu-id="cc93c-118">Il [come](../../../../visual-basic/language-reference/statements/as-clause.md) clausola nell'istruzione di dichiarazione consente di definire il tipo di dati o un tipo di oggetto della variabile che si sta dichiarando.</span><span class="sxs-lookup"><span data-stu-id="cc93c-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="cc93c-119">È possibile specificare uno dei seguenti tipi per una variabile:</span><span class="sxs-lookup"><span data-stu-id="cc93c-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="cc93c-120">Digitare un dati elementari, ad esempio `Boolean`, `Long`, o`Decimal`</span><span class="sxs-lookup"><span data-stu-id="cc93c-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="cc93c-121">Un tipo di dati composito, come una matrice o una struttura</span><span class="sxs-lookup"><span data-stu-id="cc93c-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="cc93c-122">Un tipo di oggetto o una classe, definita nell'applicazione o in un'altra applicazione</span><span class="sxs-lookup"><span data-stu-id="cc93c-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="cc93c-123">Oggetto [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] classe, ad esempio <xref:System.Windows.Forms.Label>o <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="cc93c-123">A [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="cc93c-124">Tipo di un'interfaccia, ad esempio <xref:System.IComparable>o <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="cc93c-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="cc93c-125">È possibile dichiarare più variabili in un'unica istruzione senza dover ripetere il tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="cc93c-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="cc93c-126">Nelle istruzioni seguenti, le variabili `i`, `j`, e `k` vengono dichiarati come tipo `Integer`, `l` e `m` come `Long`, e `x` e `y` come `Single`:</span><span class="sxs-lookup"><span data-stu-id="cc93c-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="cc93c-127">Per ulteriori informazioni sui tipi di dati, vedere [tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="cc93c-128">Per ulteriori informazioni sugli oggetti, vedere [oggetti e classi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) e [programmazione con i componenti](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span><span class="sxs-lookup"><span data-stu-id="cc93c-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="cc93c-129">Inferenza del tipo di variabile locale</span><span class="sxs-lookup"><span data-stu-id="cc93c-129">Local Type Inference</span></span>  
 <span data-ttu-id="cc93c-130">*Inferenza del tipo* viene utilizzato per determinare i tipi di dati delle variabili locali dichiarate senza un `As` clausola.</span><span class="sxs-lookup"><span data-stu-id="cc93c-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="cc93c-131">Il compilatore deduce il tipo della variabile dal tipo dell'espressione di inizializzazione.</span><span class="sxs-lookup"><span data-stu-id="cc93c-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="cc93c-132">In questo modo è possibile dichiarare variabili senza dichiarare in modo esplicito un tipo.</span><span class="sxs-lookup"><span data-stu-id="cc93c-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="cc93c-133">Nell'esempio seguente, entrambi `num1` e `num2` sono fortemente tipizzati come integer.</span><span class="sxs-lookup"><span data-stu-id="cc93c-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="cc93c-134">[!code-vb[VbVbalrTypeInference n.&1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cc93c-134">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span></span>  
  
 <span data-ttu-id="cc93c-135">Se si desidera utilizzare l'inferenza del tipo locale, `Option Infer` deve essere impostato su `On`.</span><span class="sxs-lookup"><span data-stu-id="cc93c-135">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="cc93c-136">Per ulteriori informazioni, vedere [l'inferenza del tipo locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) e [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="cc93c-137">Caratteristiche delle variabili dichiarate</span><span class="sxs-lookup"><span data-stu-id="cc93c-137">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="cc93c-138">Il *durata* di una variabile è il periodo di tempo durante il quale essa è disponibile per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="cc93c-138">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="cc93c-139">In generale, esiste una variabile, purché l'elemento che lo dichiara (ad esempio, una procedura o una classe) continua a esistere.</span><span class="sxs-lookup"><span data-stu-id="cc93c-139">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="cc93c-140">Se la variabile non è necessario continuare oltre la durata dell'elemento contenitore esistente, non occorre eseguire alcuna azione speciale nella dichiarazione.</span><span class="sxs-lookup"><span data-stu-id="cc93c-140">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="cc93c-141">Se la variabile deve continuare a esistere più rispetto all'elemento contenitore, è possibile includere il `Static` o `Shared` (parola chiave) nel relativo `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="cc93c-141">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="cc93c-142">Per ulteriori informazioni, vedere [durata in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-142">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="cc93c-143">Il *ambito* è il set di tutto il codice che è possibile farvi riferimento senza la qualifica del nome di una variabile.</span><span class="sxs-lookup"><span data-stu-id="cc93c-143">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="cc93c-144">Ambito di una variabile è determinato in cui è dichiarata.</span><span class="sxs-lookup"><span data-stu-id="cc93c-144">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="cc93c-145">Il codice di una determinata area è possibile utilizzare le variabili definite in tale area senza la necessità di qualificare i nomi.</span><span class="sxs-lookup"><span data-stu-id="cc93c-145">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="cc93c-146">Per ulteriori informazioni, vedere [ambito in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-146">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="cc93c-147">Una variabile *livello di accesso* è l'ambito del codice che dispone dell'autorizzazione per accedervi.</span><span class="sxs-lookup"><span data-stu-id="cc93c-147">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="cc93c-148">Ciò è determinato dal modificatore di accesso (ad esempio [pubblica](../../../../visual-basic/language-reference/modifiers/public.md) o [privata](../../../../visual-basic/language-reference/modifiers/private.md)) utilizzato nel `Dim` istruzione.</span><span class="sxs-lookup"><span data-stu-id="cc93c-148">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="cc93c-149">Per ulteriori informazioni, vedere [livelli di accesso in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="cc93c-149">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc93c-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc93c-150">See Also</span></span>  
 <span data-ttu-id="cc93c-151">[Procedura: creare una nuova variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-151">[How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span></span>  
<span data-ttu-id="cc93c-152"> [Procedura: spostare i dati in e da una variabile](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-152"> [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
<span data-ttu-id="cc93c-153"> [Tipi di dati](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-153"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="cc93c-154"> [Protetto](../../../../visual-basic/language-reference/modifiers/protected.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-154"> [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) </span></span>  
<span data-ttu-id="cc93c-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span></span>  
<span data-ttu-id="cc93c-156"> [Statico](../../../../visual-basic/language-reference/modifiers/static.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-156"> [Static](../../../../visual-basic/language-reference/modifiers/static.md) </span></span>  
<span data-ttu-id="cc93c-157"> [Caratteristiche di elementi dichiarati](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-157"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="cc93c-158"> [Inferenza del tipo locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="cc93c-158"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="cc93c-159"> [Istruzione Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="cc93c-159"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>
