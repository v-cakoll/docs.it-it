---
title: Valori di variabili oggetto
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], values
- values [Visual Basic], of object variables
- data types [Visual Basic], object variable
- variables [Visual Basic], object
ms.assetid: 31555704-58a3-49f1-9a0a-6421f605664f
ms.openlocfilehash: 8b93063d2d97802b1a7fdbc93e01040ff3337753
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351794"
---
# <a name="object-variable-values-visual-basic"></a><span data-ttu-id="3c805-102">Valori di variabili oggetto (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c805-102">Object Variable Values (Visual Basic)</span></span>
<span data-ttu-id="3c805-103">Una variabile del [tipo di dati Object](../../../../visual-basic/language-reference/data-types/object-data-type.md) può fare riferimento a dati di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="3c805-103">A variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) can refer to data of any type.</span></span> <span data-ttu-id="3c805-104">Il valore archiviato in una variabile di `Object` viene mantenuto in memoria, mentre la variabile stessa mantiene un puntatore ai dati.</span><span class="sxs-lookup"><span data-stu-id="3c805-104">The value you store in an `Object` variable is kept elsewhere in memory, while the variable itself holds a pointer to the data.</span></span>  
  
## <a name="object-classifier-functions"></a><span data-ttu-id="3c805-105">Funzioni di classificazione oggetti</span><span class="sxs-lookup"><span data-stu-id="3c805-105">Object Classifier Functions</span></span>  
 <span data-ttu-id="3c805-106">Visual Basic fornisce funzioni che restituiscono informazioni sul riferimento a una variabile `Object`, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="3c805-106">Visual Basic supplies functions that return information about what an `Object` variable refers to, as shown in the following table.</span></span>  
  
|<span data-ttu-id="3c805-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="3c805-107">Function</span></span>|<span data-ttu-id="3c805-108">Restituisce true se la variabile oggetto fa riferimento a</span><span class="sxs-lookup"><span data-stu-id="3c805-108">Returns True if the Object variable refers to</span></span>|  
|--------------|---------------------------------------------------|  
|<xref:Microsoft.VisualBasic.Information.IsArray%2A>|<span data-ttu-id="3c805-109">Matrice di valori, anziché un singolo valore.</span><span class="sxs-lookup"><span data-stu-id="3c805-109">An array of values, rather than a single value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDate%2A>|<span data-ttu-id="3c805-110">Valore del [tipo di dati date](../../../../visual-basic/language-reference/data-types/date-data-type.md) oppure stringa che può essere interpretata come valore di data e ora</span><span class="sxs-lookup"><span data-stu-id="3c805-110">A [Date Data Type](../../../../visual-basic/language-reference/data-types/date-data-type.md) value, or a string that can be interpreted as a date and time value</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsDBNull%2A>|<span data-ttu-id="3c805-111">Oggetto di tipo <xref:System.DBNull>, che rappresenta dati mancanti o inesistenti</span><span class="sxs-lookup"><span data-stu-id="3c805-111">An object of type <xref:System.DBNull>, which represents missing or nonexistent data</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsError%2A>|<span data-ttu-id="3c805-112">Oggetto eccezione, che deriva da <xref:System.Exception></span><span class="sxs-lookup"><span data-stu-id="3c805-112">An exception object, which derives from <xref:System.Exception></span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNothing%2A>|<span data-ttu-id="3c805-113">[Niente](../../../../visual-basic/language-reference/nothing.md), ovvero nessun oggetto è attualmente assegnato alla variabile</span><span class="sxs-lookup"><span data-stu-id="3c805-113">[Nothing](../../../../visual-basic/language-reference/nothing.md), that is, no object is currently assigned to the variable</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsNumeric%2A>|<span data-ttu-id="3c805-114">Un numero o una stringa che può essere interpretata come numero</span><span class="sxs-lookup"><span data-stu-id="3c805-114">A number, or a string that can be interpreted as a number</span></span>|  
|<xref:Microsoft.VisualBasic.Information.IsReference%2A>|<span data-ttu-id="3c805-115">Un tipo di riferimento (ad esempio una stringa, una matrice, un delegato o un tipo di classe)</span><span class="sxs-lookup"><span data-stu-id="3c805-115">A reference type (such as a string, array, delegate, or class type)</span></span>|  
  
 <span data-ttu-id="3c805-116">È possibile utilizzare queste funzioni per evitare di inviare un valore non valido a un'operazione o a una routine.</span><span class="sxs-lookup"><span data-stu-id="3c805-116">You can use these functions to avoid submitting an invalid value to an operation or a procedure.</span></span>  
  
## <a name="typeof-operator"></a><span data-ttu-id="3c805-117">Operatore TypeOf</span><span class="sxs-lookup"><span data-stu-id="3c805-117">TypeOf Operator</span></span>  
 <span data-ttu-id="3c805-118">È anche possibile usare l' [operatore typeof](../../../../visual-basic/language-reference/operators/typeof-operator.md) per determinare se una variabile oggetto si riferisce attualmente a un tipo di dati specifico.</span><span class="sxs-lookup"><span data-stu-id="3c805-118">You can also use the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to determine whether an object variable currently refers to a specific data type.</span></span> <span data-ttu-id="3c805-119">L'espressione `TypeOf`...`Is` restituisce `True` se il tipo in fase di esecuzione dell'operando è derivato da o implementa il tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="3c805-119">The `TypeOf`...`Is` expression evaluates to `True` if the run-time type of the operand is derived from or implements the specified type.</span></span>  
  
 <span data-ttu-id="3c805-120">Nell'esempio seguente viene usato `TypeOf` sulle variabili oggetto che fanno riferimento a tipi di valore e di riferimento.</span><span class="sxs-lookup"><span data-stu-id="3c805-120">The following example uses `TypeOf` on object variables referring to value and reference types.</span></span>  
  
```vb  
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
  
 <span data-ttu-id="3c805-121">Nell'esempio precedente vengono scritte le righe seguenti nella finestra di **debug** :</span><span class="sxs-lookup"><span data-stu-id="3c805-121">The preceding example writes the following lines to the **Debug** window:</span></span>  
  
 `num is Integer`  
  
 `num is Object`  
  
 `frm is Form`  
  
 `frm is Object`  
  
 <span data-ttu-id="3c805-122">La variabile oggetto `num` fa riferimento ai dati di tipo `Integer`e `frm` fa riferimento a un oggetto della classe <xref:System.Windows.Forms.Form>.</span><span class="sxs-lookup"><span data-stu-id="3c805-122">The object variable `num` refers to data of type `Integer`, and `frm` refers to an object of class <xref:System.Windows.Forms.Form>.</span></span>  
  
## <a name="object-arrays"></a><span data-ttu-id="3c805-123">Matrici di oggetti</span><span class="sxs-lookup"><span data-stu-id="3c805-123">Object Arrays</span></span>  
 <span data-ttu-id="3c805-124">È possibile dichiarare e utilizzare una matrice di variabili di `Object`.</span><span class="sxs-lookup"><span data-stu-id="3c805-124">You can declare and use an array of `Object` variables.</span></span> <span data-ttu-id="3c805-125">Questa operazione è utile quando è necessario gestire un'ampia gamma di tipi di dati e classi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="3c805-125">This is useful when you need to handle a variety of data types and object classes.</span></span> <span data-ttu-id="3c805-126">Tutti gli elementi di una matrice devono avere lo stesso tipo di dati dichiarato.</span><span class="sxs-lookup"><span data-stu-id="3c805-126">All the elements in an array must have the same declared data type.</span></span> <span data-ttu-id="3c805-127">Dichiarando questo tipo di dati come `Object`, è possibile archiviare gli oggetti e le istanze di classe insieme ad altri tipi di dati nella matrice.</span><span class="sxs-lookup"><span data-stu-id="3c805-127">Declaring this data type as `Object` allows you to store objects and class instances alongside other data types in the array.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c805-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c805-128">See also</span></span>

- [<span data-ttu-id="3c805-129">Variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3c805-129">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="3c805-130">Dichiarazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3c805-130">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="3c805-131">Assegnazione di variabili oggetto</span><span class="sxs-lookup"><span data-stu-id="3c805-131">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="3c805-132">Procedura: fare riferimento all'istanza corrente di un oggetto</span><span class="sxs-lookup"><span data-stu-id="3c805-132">How to: Refer to the Current Instance of an Object</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="3c805-133">Procedura: determinare a quale tipo fa riferimento una variabile oggetto</span><span class="sxs-lookup"><span data-stu-id="3c805-133">How to: Determine What Type an Object Variable Refers To</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [<span data-ttu-id="3c805-134">Procedura: determinare se due oggetti sono correlati</span><span class="sxs-lookup"><span data-stu-id="3c805-134">How to: Determine Whether Two Objects Are Related</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="3c805-135">Procedura: determinare se due oggetti sono identici</span><span class="sxs-lookup"><span data-stu-id="3c805-135">How to: Determine Whether Two Objects Are Identical</span></span>](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
- [<span data-ttu-id="3c805-136">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="3c805-136">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
