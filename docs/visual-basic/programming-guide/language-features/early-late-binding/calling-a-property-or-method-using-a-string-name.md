---
title: "Chiamata di una proprietà o metodo utilizzando un nome di stringa (Visual Basic) | Documenti di Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6de5e655b3d4d42283b81507d7f08e0eb0b9424d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a><span data-ttu-id="e921c-102">Chiamata di una proprietà o di un metodo mediante un nome di stringa (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e921c-102">Calling a Property or Method Using a String Name (Visual Basic)</span></span>
<span data-ttu-id="e921c-103">Nella maggior parte dei casi, è possibile individuare le proprietà e metodi di un oggetto in fase di progettazione e scrivere codice per gestirli.</span><span class="sxs-lookup"><span data-stu-id="e921c-103">In most cases, you can discover the properties and methods of an object at design time, and write code to handle them.</span></span> <span data-ttu-id="e921c-104">Tuttavia, in alcuni casi potrebbe non sapere sulle proprietà e metodi di un oggetto in anticipo o si potrebbe volere la flessibilità di un utente finale di specificare le proprietà o eseguire i metodi in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e921c-104">However, in some cases you may not know about an object's properties and methods in advance, or you may just want the flexibility of enabling an end user to specify properties or execute methods at run time.</span></span>  
  
## <a name="callbyname-function"></a><span data-ttu-id="e921c-105">CallByName (funzione)</span><span class="sxs-lookup"><span data-stu-id="e921c-105">CallByName Function</span></span>  
 <span data-ttu-id="e921c-106">Si consideri, ad esempio, un'applicazione client che valuta espressioni immesse dall'utente mediante il passaggio di un operatore a un componente COM.</span><span class="sxs-lookup"><span data-stu-id="e921c-106">Consider, for example, a client application that evaluates expressions entered by the user by passing an operator to a COM component.</span></span> <span data-ttu-id="e921c-107">Si supponga che si siano aggiungendo nuove funzioni costantemente il componente che richiedono nuovi operatori.</span><span class="sxs-lookup"><span data-stu-id="e921c-107">Suppose you are constantly adding new functions to the component that require new operators.</span></span> <span data-ttu-id="e921c-108">Quando si utilizzano tecniche di accesso agli oggetti standard, è necessario ricompilare e ridistribuire l'applicazione client prima di utilizzare i nuovi operatori.</span><span class="sxs-lookup"><span data-stu-id="e921c-108">When you use standard object access techniques, you must recompile and redistribute the client application before it could use the new operators.</span></span> <span data-ttu-id="e921c-109">Per evitare questo problema, è possibile utilizzare il `CallByName` funzione per passare i nuovi operatori come stringhe, senza modificare l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e921c-109">To avoid this, you can use the `CallByName` function to pass the new operators as strings, without changing the application.</span></span>  
  
 <span data-ttu-id="e921c-110">Il `CallByName` funzione consente di utilizzare una stringa per specificare una proprietà o metodo in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e921c-110">The `CallByName` function lets you use a string to specify a property or method at run time.</span></span> <span data-ttu-id="e921c-111">La firma per il `CallByName` funzione è simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="e921c-111">The signature for the `CallByName` function looks like this:</span></span>  
  
 <span data-ttu-id="e921c-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span><span class="sxs-lookup"><span data-stu-id="e921c-112">*Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())</span></span>  
  
 <span data-ttu-id="e921c-113">Il primo argomento, *oggetto*, accetta il nome dell'oggetto di cui si desidera agire.</span><span class="sxs-lookup"><span data-stu-id="e921c-113">The first argument, *Object*, takes the name of the object you want to act upon.</span></span> <span data-ttu-id="e921c-114">Il *NomeProcedura* argomento accetta una stringa che contiene il nome del metodo o proprietà della routine da richiamare.</span><span class="sxs-lookup"><span data-stu-id="e921c-114">The *ProcedureName* argument takes a string that contains the name of the method or property procedure to be invoked.</span></span> <span data-ttu-id="e921c-115">Il *CallType* argomento accetta una costante che rappresenta il tipo di routine da richiamare: un metodo (`Microsoft.VisualBasic.CallType.Method`), una proprietà di lettura (`Microsoft.VisualBasic.CallType.Get`), o un insieme di proprietà (`Microsoft.VisualBasic.CallType.Set`).</span><span class="sxs-lookup"><span data-stu-id="e921c-115">The *CallType* argument takes a constant that represents the type of procedure to invoke: a method (`Microsoft.VisualBasic.CallType.Method`), a property read (`Microsoft.VisualBasic.CallType.Get`), or a property set (`Microsoft.VisualBasic.CallType.Set`).</span></span> <span data-ttu-id="e921c-116">Il *argomenti* argomento è facoltativo, prende una matrice di tipo `Object` che contiene gli argomenti per la procedura.</span><span class="sxs-lookup"><span data-stu-id="e921c-116">The *Arguments* argument, which is optional, takes an array of type `Object` that contains any arguments to the procedure.</span></span>  
  
 <span data-ttu-id="e921c-117">È possibile utilizzare `CallByName` con le classi nella soluzione corrente, ma che vengono spesso utilizzati per accedere agli oggetti COM o oggetti da [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] assembly.</span><span class="sxs-lookup"><span data-stu-id="e921c-117">You can use `CallByName` with classes in your current solution, but it is most often used to access COM objects or objects from [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] assemblies.</span></span>  
  
 <span data-ttu-id="e921c-118">Si supponga di aggiunta un riferimento a un assembly che contiene una classe denominata `MathClass`, che dispone di una nuova funzione denominata `SquareRoot`, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="e921c-118">Suppose you add a reference to an assembly that contains a class named `MathClass`, which has a new function named `SquareRoot`, as shown in the following code:</span></span>  
  
 <span data-ttu-id="e921c-119">[!code-vb[VbVbalrOOP&#53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e921c-119">[!code-vb[VbVbalrOOP#53](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]</span></span>  
  
 <span data-ttu-id="e921c-120">L'applicazione è possibile utilizzare le caselle di testo al controllo verrà chiamato il metodo e i relativi argomenti.</span><span class="sxs-lookup"><span data-stu-id="e921c-120">Your application could use text box controls to control which method will be called and its arguments.</span></span> <span data-ttu-id="e921c-121">Ad esempio, se `TextBox1` contiene l'espressione da valutare e `TextBox2` viene utilizzata per immettere il nome della funzione, è possibile utilizzare il codice seguente per richiamare il `SquareRoot` funzione nell'espressione nel `TextBox1`:</span><span class="sxs-lookup"><span data-stu-id="e921c-121">For example, if `TextBox1` contains the expression to be evaluated, and `TextBox2` is used to enter the name of the function, you can use the following code to invoke the `SquareRoot` function on the expression in `TextBox1`:</span></span>  
  
 <span data-ttu-id="e921c-122">[!code-vb[&#54; VbVbalrOOP](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="e921c-122">[!code-vb[VbVbalrOOP#54](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]</span></span>  
  
 <span data-ttu-id="e921c-123">Se si immette "64" in `TextBox1`, "SquareRoot" in `TextBox2`e quindi chiamare il `CallMath` procedura, la radice quadrata del numero in `TextBox1` viene valutato.</span><span class="sxs-lookup"><span data-stu-id="e921c-123">If you enter "64" in `TextBox1`, "SquareRoot" in `TextBox2`, and then call the `CallMath` procedure, the square root of the number in `TextBox1` is evaluated.</span></span> <span data-ttu-id="e921c-124">Il codice di esempio richiama il `SquareRoot` funzione (che accetta una stringa che contiene l'espressione da valutare come un argomento obbligatorio) e restituisce "8" `TextBox1` (la radice quadrata di 64).</span><span class="sxs-lookup"><span data-stu-id="e921c-124">The code in the example invokes the `SquareRoot` function (which takes a string that contains the expression to be evaluated as a required argument) and returns "8" in `TextBox1` (the square root of 64).</span></span> <span data-ttu-id="e921c-125">Naturalmente, se l'utente immette una stringa non valida in `TextBox2`, se la stringa contiene il nome di una proprietà anziché un metodo oppure se il metodo richiede un ulteriore argomento, si verifica un errore di run-time.</span><span class="sxs-lookup"><span data-stu-id="e921c-125">Of course, if the user enters an invalid string in `TextBox2`, if the string contains the name of a property instead of a method, or if the method had an additional required argument, a run-time error occurs.</span></span> <span data-ttu-id="e921c-126">È necessario aggiungere codice di gestione degli errori affidabile quando si utilizza `CallByName` per prevenire questo o altri errori.</span><span class="sxs-lookup"><span data-stu-id="e921c-126">You have to add robust error-handling code when you use `CallByName` to anticipate these or any other errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e921c-127">Mentre il `CallByName` funzione potrebbe essere utile in alcuni casi, è necessario valutare dell'utilità, anche le implicazioni sulle prestazioni, utilizzando `CallByName` per richiamare una routine risulta leggermente più lento rispetto a una chiamata ad associazione tardiva.</span><span class="sxs-lookup"><span data-stu-id="e921c-127">While the `CallByName` function may be useful in some cases, you must weigh its usefulness against the performance implications — using `CallByName` to invoke a procedure is slightly slower than a late-bound call.</span></span> <span data-ttu-id="e921c-128">Se si richiamano una funzione che viene poi chiamata più volte, ad esempio all'interno di un ciclo, `CallByName` può avere un impatto notevole sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e921c-128">If you are invoking a function that is called repeatedly, such as inside a loop, `CallByName` can have a severe effect on performance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e921c-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e921c-129">See Also</span></span>  
 <span data-ttu-id="e921c-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span><span class="sxs-lookup"><span data-stu-id="e921c-130"><xref:Microsoft.VisualBasic.Interaction.CallByName%2A></span></span>   
<span data-ttu-id="e921c-131"> [Determinazione del tipo di un oggetto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span><span class="sxs-lookup"><span data-stu-id="e921c-131"> [Determining Object Type](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)</span></span>
