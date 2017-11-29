---
title: Generic Procedures in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e019ca32277f93f798e99e996a3670c8302ba9b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="cf1ac-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf1ac-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="cf1ac-103">Oggetto *routine generica*, denominati anche un *metodo generico*, non è una procedura definita con almeno un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="cf1ac-104">In questo modo il codice adattare i tipi di dati ai propri requisiti ogni volta che viene chiamata la routine chiamante.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="cf1ac-105">Una stored procedure non è generica semplicemente perché definita all'interno di una classe generica o una struttura generica.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="cf1ac-106">Per essere generico, la routine deve accettare almeno un parametro di tipo, oltre a eventuali parametri normali che possono essere necessarie.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="cf1ac-107">Una classe generica o una struttura può contenere procedure non generiche e una classe, struttura o modulo può contenere routine generiche.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="cf1ac-108">Una routine generica è possibile utilizzare i parametri di tipo nel relativo elenco di parametri normali, il tipo restituito se dispone di codice uno e nella relativa procedura.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="cf1ac-109">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="cf1ac-109">Type Inference</span></span>  
 <span data-ttu-id="cf1ac-110">È possibile chiamare una routine generica senza fornire alcun argomento di tipo affatto.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="cf1ac-111">Se si chiama in questo modo, il compilatore tenta di determinare i tipi di dati appropriato per passare agli argomenti di tipo della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="cf1ac-112">Si tratta di *l'inferenza del tipo*.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-112">This is called *type inference*.</span></span> <span data-ttu-id="cf1ac-113">Il codice seguente viene illustrata una chiamata in cui il compilatore deduce che deve essere passato tipo `String` al parametro di tipo `t`.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 <span data-ttu-id="cf1ac-114">Se il compilatore non è possibile dedurre gli argomenti di tipo dal contesto della chiamata, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="cf1ac-115">Una delle possibili cause di questo errore è una mancata corrispondenza del numero di dimensioni matrice.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="cf1ac-116">Ad esempio, si supponga di che definisce un parametro normale come una matrice di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="cf1ac-117">Se si chiama la routine generica fornendo una matrice di un numero di dimensioni diversa (numero di dimensioni), la mancata corrispondenza causa l'inferenza del tipo esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="cf1ac-118">Il codice seguente viene illustrata una chiamata in una matrice bidimensionale che viene passata a una procedura che prevede una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 <span data-ttu-id="cf1ac-119">È possibile richiamare l'inferenza del tipo solo omettendo tutti gli argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="cf1ac-120">Se si fornisce un argomento di tipo, è necessario fornire tutti.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="cf1ac-121">L'inferenza del tipo è supportato solo per le routine generiche.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="cf1ac-122">Non è possibile richiamare l'inferenza del tipo in delegati, strutture, interfacce o classi generiche.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf1ac-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf1ac-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cf1ac-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cf1ac-124">Description</span></span>  
 <span data-ttu-id="cf1ac-125">L'esempio seguente definisce un oggetto generico `Function` procedura per trovare un particolare elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="cf1ac-126">Definisce un parametro di tipo e viene utilizzato per costruire i due parametri nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cf1ac-127">Codice</span><span class="sxs-lookup"><span data-stu-id="cf1ac-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="cf1ac-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="cf1ac-128">Comments</span></span>  
 <span data-ttu-id="cf1ac-129">L'esempio precedente richiede la possibilità di confrontare `searchValue` rispetto a ogni elemento di `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="cf1ac-130">Per garantire la possibilità, vincola il parametro di tipo `T` per implementare il <xref:System.IComparable%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="cf1ac-131">Il codice Usa il <xref:System.IComparable%601.CompareTo%2A> anziché il `=` (operatore), poiché non c'è garanzia che un argomento di tipo fornito per `T` supporta il `=` operatore.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="cf1ac-132">È possibile testare il `findElement` procedure con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="cf1ac-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 <span data-ttu-id="cf1ac-133">Nelle chiamate precedenti a `MsgBox` visualizzare rispettivamente "0", "1" e "-1".</span><span class="sxs-lookup"><span data-stu-id="cf1ac-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf1ac-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf1ac-134">See Also</span></span>  
 [<span data-ttu-id="cf1ac-135">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cf1ac-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="cf1ac-136">Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi</span><span class="sxs-lookup"><span data-stu-id="cf1ac-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="cf1ac-137">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="cf1ac-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="cf1ac-138">Routine</span><span class="sxs-lookup"><span data-stu-id="cf1ac-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="cf1ac-139">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="cf1ac-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="cf1ac-140">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="cf1ac-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="cf1ac-141">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="cf1ac-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
