---
title: Valori della variabile (Visual Basic) | Documenti di Microsoft
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
- object variables, values
- values, of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
caps.latest.revision: 18
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
ms.openlocfilehash: 5f42706a79212ae523b08ee336fdcacb3f761af6
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="1bdca-102">Valori di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1bdca-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="1bdca-103">Una variabile di [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) può fare riferimento a qualsiasi tipo di dati.</span><span class="sxs-lookup"><span data-stu-id="1bdca-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="1bdca-104">Il valore memorizzato in un `Object` variabile viene mantenuta in un' posizione in memoria, mentre la variabile contiene un puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="1bdca-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="1bdca-105">Funzioni di classificazione di oggetto</span><span class="sxs-lookup"><span data-stu-id="1bdca-105">Object Classifier Functions</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1bdca-106">fornisce funzioni che restituiscono informazioni su un `Object` variabile fa riferimento, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1bdca-106"> supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="1bdca-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="1bdca-107">Function</span></span>|<span data-ttu-id="1bdca-108">Restituisce True se la variabile oggetto fa riferimento a</span><span class="sxs-lookup"><span data-stu-id="1bdca-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<span data-ttu-id="1bdca-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></xref:Microsoft.VisualBasic.Information.IsArray%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-109"><xref:Microsoft.VisualBasic.Information.IsArray%2A></span></span>|<span data-ttu-id="1bdca-110">Matrice di valori, anziché un singolo valore</span><span class="sxs-lookup"><span data-stu-id="1bdca-110">An array of values, rather than a single value</span></span>|  
|<span data-ttu-id="1bdca-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></xref:Microsoft.VisualBasic.Information.IsDate%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-111"><xref:Microsoft.VisualBasic.Information.IsDate%2A></span></span>|<span data-ttu-id="1bdca-112">Oggetto [tipo di dati Date](../../../../visual-basic/language-reference/data-types/date-data-type.md) valore o una stringa che può essere interpretata come valore di data e ora</span><span class="sxs-lookup"><span data-stu-id="1bdca-112">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<span data-ttu-id="1bdca-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-113"><xref:Microsoft.VisualBasic.Information.IsDBNull%2A></span></span>|<span data-ttu-id="1bdca-114">Un oggetto di tipo <xref:System.DBNull>che rappresenta dati mancanti o inesistenti</xref:System.DBNull></span><span class="sxs-lookup"><span data-stu-id="1bdca-114">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<span data-ttu-id="1bdca-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></xref:Microsoft.VisualBasic.Information.IsError%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-115"><xref:Microsoft.VisualBasic.Information.IsError%2A></span></span>|<span data-ttu-id="1bdca-116">Un oggetto eccezione che deriva da<xref:System.Exception></xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="1bdca-116">An exception object, which derives from <xref:System.Exception></span></span>|  
|<span data-ttu-id="1bdca-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></xref:Microsoft.VisualBasic.Information.IsNothing%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-117"><xref:Microsoft.VisualBasic.Information.IsNothing%2A></span></span>|<span data-ttu-id="1bdca-118">[Nothing](../../../../visual-basic/language-reference/nothing.md), vale a dire, nessun oggetto è attualmente assegnato alla variabile</span><span class="sxs-lookup"><span data-stu-id="1bdca-118">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<span data-ttu-id="1bdca-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-119"><xref:Microsoft.VisualBasic.Information.IsNumeric%2A></span></span>|<span data-ttu-id="1bdca-120">Un numero o una stringa che può essere interpretata come un numero</span><span class="sxs-lookup"><span data-stu-id="1bdca-120">A number, or a string that can be interpreted as a number</span></span>|  
|<span data-ttu-id="1bdca-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></xref:Microsoft.VisualBasic.Information.IsReference%2A></span><span class="sxs-lookup"><span data-stu-id="1bdca-121"><xref:Microsoft.VisualBasic.Information.IsReference%2A></span></span>|<span data-ttu-id="1bdca-122">Un tipo di riferimento (ad esempio una stringa, matrice, delegato o tipo di classe)</span><span class="sxs-lookup"><span data-stu-id="1bdca-122">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="1bdca-123">È possibile utilizzare queste funzioni per evitare l'invio di un valore non valido a un'operazione o una routine.</span><span class="sxs-lookup"><span data-stu-id="1bdca-123">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="1bdca-124">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="1bdca-124">TypeOf Operator</span></span>  
 <span data-ttu-id="1bdca-125">È inoltre possibile utilizzare il [operatore TypeOf](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se una variabile oggetto fa attualmente riferimento a un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="1bdca-125">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="1bdca-126">The `TypeOf`... `Is` espressione viene valutata `True` se il tipo in fase di esecuzione dell'operando è derivato da o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="1bdca-126">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="1bdca-127">Nell'esempio seguente viene utilizzato `TypeOf` su variabili oggetto che fa riferimento ai tipi di riferimento e valore.</span><span class="sxs-lookup"><span data-stu-id="1bdca-127">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
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
  
 <span data-ttu-id="1bdca-128">Nell'esempio precedente scrive le righe seguenti per il **Debug** finestra:</span><span class="sxs-lookup"><span data-stu-id="1bdca-128">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="1bdca-129">La variabile oggetto `num` fa riferimento a dati di tipo `Integer`, e `frm` fa riferimento a un oggetto della classe <xref:System.Windows.Forms.Form>.</xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="1bdca-129">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="1bdca-130">Matrici di oggetti</span><span class="sxs-lookup"><span data-stu-id="1bdca-130">Object Arrays</span></span>  
 <span data-ttu-id="1bdca-131">È possibile dichiarare e utilizzare una matrice di `Object` variabili.</span><span class="sxs-lookup"><span data-stu-id="1bdca-131">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="1bdca-132">Ciò è utile quando è necessario gestire un'ampia gamma di tipi di dati e le classi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="1bdca-132">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="1bdca-133">Tutti gli elementi in una matrice devono avere gli stessi dati dichiarati di tipo.</span><span class="sxs-lookup"><span data-stu-id="1bdca-133">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="1bdca-134">Dichiarazione di questo tipo di dati come `Object` consente di archiviare oggetti e le istanze insieme ad altri tipi di dati nella matrice di classe.</span><span class="sxs-lookup"><span data-stu-id="1bdca-134">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bdca-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1bdca-135">See Also</span></span>  
 <span data-ttu-id="1bdca-136">[Variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-136">[Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md) </span></span>  
<span data-ttu-id="1bdca-137"> [Dichiarazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-137"> [Object Variable Declaration](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md) </span></span>  
<span data-ttu-id="1bdca-138"> [Assegnazione di variabili oggetto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-138"> [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md) </span></span>  
<span data-ttu-id="1bdca-139"> [Procedura: fare riferimento all'istanza corrente di un oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-139"> [How to: Refer to the Current Instance of an Object](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md) </span></span>  
<span data-ttu-id="1bdca-140"> [Procedura: determinare a quale tipo fa riferimento una variabile oggetto](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-140"> [How to: Determine What Type an Object Variable Refers To](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md) </span></span>  
<span data-ttu-id="1bdca-141"> [Procedura: determinare se due oggetti sono correlati](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-141"> [How to: Determine Whether Two Objects Are Related](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md) </span></span>  
<span data-ttu-id="1bdca-142"> [Procedura: determinare se due oggetti sono identici](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span><span class="sxs-lookup"><span data-stu-id="1bdca-142"> [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md) </span></span>  
<span data-ttu-id="1bdca-143"> [Tipi di dati](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span><span class="sxs-lookup"><span data-stu-id="1bdca-143"> [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md)</span></span>
