---
title: Valori di variabili oggetto (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28307cc477f661c3046e125f297c1519485ad797
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="49832-102">Valori di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49832-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="49832-103">Una variabile del [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) può fare riferimento a qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="49832-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="49832-104">Il valore memorizzato in un `Object` variabile viene mantenuta in un' posizione in memoria, mentre la variabile contiene un puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="49832-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="49832-105">Funzioni di classificazione di oggetto</span><span class="sxs-lookup"><span data-stu-id="49832-105">Object Classifier Functions</span></span>  
 <span data-ttu-id="49832-106">Visual Basic fornisce le funzioni che restituiscono informazioni su cosa un `Object` variabile fa riferimento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="49832-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="49832-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="49832-107">Function</span></span>|<span data-ttu-id="49832-108">Restituisce True se la variabile oggetto fa riferimento a</span><span class="sxs-lookup"><span data-stu-id="49832-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="49832-109">Matrice di valori, anziché un singolo valore</span><span class="sxs-lookup"><span data-stu-id="49832-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="49832-110">Oggetto [tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) valore o una stringa che può essere interpretata come un valore di data e ora</span><span class="sxs-lookup"><span data-stu-id="49832-110">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="49832-111">Un oggetto di tipo <xref:System.DBNull>, che rappresenta i dati mancanti o non esistenti</span><span class="sxs-lookup"><span data-stu-id="49832-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="49832-112">Un oggetto eccezione che deriva da <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="49832-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="49832-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), vale a dire, nessun oggetto è attualmente assegnato alla variabile</span><span class="sxs-lookup"><span data-stu-id="49832-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="49832-114">Un numero o una stringa che può essere interpretata come un numero</span><span class="sxs-lookup"><span data-stu-id="49832-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="49832-115">Un tipo riferimento (ad esempio una stringa, matrice, delegato o tipo di classe)</span><span class="sxs-lookup"><span data-stu-id="49832-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="49832-116">Per evitare l'invio di un valore non valido a un'operazione o una stored procedure, è possibile utilizzare queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="49832-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="49832-117">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="49832-117">TypeOf Operator</span></span>  
 <span data-ttu-id="49832-118">È inoltre possibile utilizzare il [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se una variabile oggetto fa attualmente riferimento a un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="49832-118">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="49832-119">Il `TypeOf`... `Is` espressione viene valutata `True` se il tipo in fase di esecuzione dell'operando è derivato da o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="49832-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="49832-120">L'esempio seguente usa `TypeOf` su variabili di oggetto che fa riferimento a tipi di riferimento e valore.</span><span class="sxs-lookup"><span data-stu-id="49832-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```  
' The following statement puts a value type (Integer) in an Object variable.  
Dim num As Object = 10  
' The following statement puts a reference type (Form) in an Object variable.  
Dim frm As Object = New Form()  
If TypeOf num Is Long Then Debug.WriteLine("num is Long")  
If TypeOf num Is Integer Then Debug.WriteLine("num is Integer")  
If TypeOf num Is Short Then Debug.WriteLine("num is Short")  
If TypeOf num Is Object Then Debug.WriteLine("num is Object")  
If TypeOf frm Is Form Then Debug.WriteLine("frm is Form")  
If TypeOf frm Is Label Then Debug.WriteLine("frm is Label")  
If TypeOf frm Is Object Then Debug.WriteLine("frm is Object")  
```  
  
 <span data-ttu-id="49832-121">Nell'esempio precedente scrive le righe seguenti per il **Debug** finestra:</span><span class="sxs-lookup"><span data-stu-id="49832-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="49832-122">La variabile oggetto `num` fa riferimento a dati di tipo `Integer`, e `frm` fa riferimento a un oggetto della classe <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="49832-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="49832-123">Matrici di oggetti</span><span class="sxs-lookup"><span data-stu-id="49832-123">Object Arrays</span></span>  
 <span data-ttu-id="49832-124">È possibile dichiarare e utilizzare una matrice di `Object` variabili.</span><span class="sxs-lookup"><span data-stu-id="49832-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="49832-125">Ciò è utile quando è necessario gestire un'ampia gamma di tipi di dati e le classi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="49832-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="49832-126">Tutti gli elementi in una matrice devono avere gli stessi dati dichiarati di tipo.</span><span class="sxs-lookup"><span data-stu-id="49832-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="49832-127">Dichiarazione di questo tipo di dati come `Object` consente di archiviare oggetti e le istanze insieme ad altri tipi di dati nella matrice di classe.</span><span class="sxs-lookup"><span data-stu-id="49832-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49832-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49832-128">See Also</span></span>  
 [<span data-ttu-id="49832-129">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="49832-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [<span data-ttu-id="49832-130">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="49832-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [<span data-ttu-id="49832-131">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="49832-131">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="49832-132">Procedura: fare riferimento all'istanza corrente di un oggetto</span><span class="sxs-lookup"><span data-stu-id="49832-132">How to: Refer to the Current Instance of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)  
 [<span data-ttu-id="49832-133">Procedura: determinare a quale tipo fa riferimento una variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="49832-133">How to: Determine What Type an Object Variable Refers To</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)  
 [<span data-ttu-id="49832-134">Procedura: determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="49832-134">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [<span data-ttu-id="49832-135">Procedura: determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="49832-135">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)  
 [<span data-ttu-id="49832-136">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="49832-136">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
