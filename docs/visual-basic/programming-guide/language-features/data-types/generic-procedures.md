---
title: Generic Procedures in Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: 9a88a979a6b46f897e5f04f4481d4a23e245b165
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2018
ms.locfileid: "44509501"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="61df6-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61df6-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="61df6-103">Oggetto *routine generica*, definita anche come una *metodo generico*, è una routine definita con almeno un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="61df6-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="61df6-104">In questo modo il codice chiamante personalizzare i tipi di dati ai propri requisiti ogni volta che viene chiamata la routine.</span><span class="sxs-lookup"><span data-stu-id="61df6-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="61df6-105">Una procedura non è generica semplicemente perché definita all'interno di una classe generica o una struttura generica.</span><span class="sxs-lookup"><span data-stu-id="61df6-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="61df6-106">Per essere generico, la routine deve accettare almeno un parametro di tipo, oltre a eventuali parametri normali che potrebbero essere necessari.</span><span class="sxs-lookup"><span data-stu-id="61df6-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="61df6-107">Una classe generica o una struttura può contenere procedure non generiche e una classe, struttura, o modulo può contenere routine generiche.</span><span class="sxs-lookup"><span data-stu-id="61df6-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="61df6-108">Una routine generica è possibile usare i parametri di tipo nell'elenco dei parametri normali, il tipo restituito se include il codice di uno e nella relativa procedura.</span><span class="sxs-lookup"><span data-stu-id="61df6-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="61df6-109">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="61df6-109">Type Inference</span></span>  
 <span data-ttu-id="61df6-110">È possibile chiamare una routine generica senza fornire alcun argomento di tipo affatto.</span><span class="sxs-lookup"><span data-stu-id="61df6-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="61df6-111">Se viene chiamata in questo modo, il compilatore prova a determinare i tipi di dati appropriato per passare agli argomenti di tipo della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="61df6-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="61df6-112">Questa operazione viene definita *inferenza del tipo*.</span><span class="sxs-lookup"><span data-stu-id="61df6-112">This is called *type inference*.</span></span> <span data-ttu-id="61df6-113">Il codice seguente viene illustrata una chiamata in cui il compilatore deduce che il tipo deve passato `String` al parametro di tipo `t`.</span><span class="sxs-lookup"><span data-stu-id="61df6-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 <span data-ttu-id="61df6-114">Se il compilatore non è possibile dedurre gli argomenti tipo dal contesto della chiamata, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="61df6-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="61df6-115">Una delle possibili cause di questo errore è una mancata corrispondenza del numero di dimensioni matrice.</span><span class="sxs-lookup"><span data-stu-id="61df6-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="61df6-116">Ad esempio, si supponga di che definisce un parametro normale come una matrice di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="61df6-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="61df6-117">Se si chiama la routine generica fornendo una matrice di una dimensione differente (numero di dimensioni), la mancata corrispondenza causa l'inferenza del tipo esito negativo.</span><span class="sxs-lookup"><span data-stu-id="61df6-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="61df6-118">Il codice seguente viene illustrata una chiamata in una matrice bidimensionale che viene passata a una procedura che prevede una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="61df6-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="61df6-119">È possibile richiamare l'inferenza del tipo solo tramite l'omissione di tutti gli argomenti tipo.</span><span class="sxs-lookup"><span data-stu-id="61df6-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="61df6-120">Se si specifica un argomento di tipo, è necessario fornire tutti.</span><span class="sxs-lookup"><span data-stu-id="61df6-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="61df6-121">L'inferenza del tipo è supportato solo per routine generiche.</span><span class="sxs-lookup"><span data-stu-id="61df6-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="61df6-122">Non è possibile richiamare l'inferenza del tipo in classi generiche, strutture, interfacce o delegati.</span><span class="sxs-lookup"><span data-stu-id="61df6-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61df6-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="61df6-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="61df6-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61df6-124">Description</span></span>  
 <span data-ttu-id="61df6-125">L'esempio seguente definisce un oggetto generico `Function` procedura per trovare un particolare elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="61df6-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="61df6-126">Definisce un parametro di tipo e lo usa per costruire i due parametri nell'elenco dei parametri.</span><span class="sxs-lookup"><span data-stu-id="61df6-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="61df6-127">Codice</span><span class="sxs-lookup"><span data-stu-id="61df6-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a><span data-ttu-id="61df6-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="61df6-128">Comments</span></span>  
 <span data-ttu-id="61df6-129">Nell'esempio precedente richiede la possibilità di confrontare `searchValue` rispetto a ogni elemento di `searchArray`.</span><span class="sxs-lookup"><span data-stu-id="61df6-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="61df6-130">Per garantire questa operazione, vincola il parametro di tipo `T` per implementare il <xref:System.IComparable%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="61df6-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="61df6-131">Il codice Usa il <xref:System.IComparable%601.CompareTo%2A> invece del metodo di `=` operatore, poiché non c'è garanzia che un argomento tipo fornito per `T` supporta la `=` operatore.</span><span class="sxs-lookup"><span data-stu-id="61df6-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="61df6-132">È possibile testare il `findElement` procedure con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="61df6-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 <span data-ttu-id="61df6-133">Nelle chiamate precedenti a `MsgBox` visualizzare rispettivamente "0", "1" e "-1".</span><span class="sxs-lookup"><span data-stu-id="61df6-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61df6-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61df6-134">See Also</span></span>  
 [<span data-ttu-id="61df6-135">Tipi generici in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="61df6-135">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [<span data-ttu-id="61df6-136">Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi</span><span class="sxs-lookup"><span data-stu-id="61df6-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [<span data-ttu-id="61df6-137">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="61df6-137">How to: Use a Generic Class</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [<span data-ttu-id="61df6-138">Routine</span><span class="sxs-lookup"><span data-stu-id="61df6-138">Procedures</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="61df6-139">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="61df6-139">Procedure Parameters and Arguments</span></span>](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="61df6-140">Elenco dei tipi</span><span class="sxs-lookup"><span data-stu-id="61df6-140">Type List</span></span>](../../../../visual-basic/language-reference/statements/type-list.md)  
 [<span data-ttu-id="61df6-141">Elenco dei parametri</span><span class="sxs-lookup"><span data-stu-id="61df6-141">Parameter List</span></span>](../../../../visual-basic/language-reference/statements/parameter-list.md)
