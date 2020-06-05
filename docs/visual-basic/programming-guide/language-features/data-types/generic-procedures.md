---
title: Routine generiche
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
ms.openlocfilehash: 2efc0410b9d4bb663e1ff19d5a5456d7ff2c99bd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84394065"
---
# <a name="generic-procedures-in-visual-basic"></a><span data-ttu-id="3d021-102">Generic Procedures in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d021-102">Generic Procedures in Visual Basic</span></span>
<span data-ttu-id="3d021-103">Una *routine generica*, detta anche *metodo generico*, è una procedura definita con almeno un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="3d021-103">A *generic procedure*, also called a *generic method*, is a procedure defined with at least one type parameter.</span></span> <span data-ttu-id="3d021-104">Ciò consente al codice chiamante di adattare i tipi di dati ai relativi requisiti ogni volta che viene chiamata la procedura.</span><span class="sxs-lookup"><span data-stu-id="3d021-104">This allows the calling code to tailor the data types to its requirements each time it calls the procedure.</span></span>  
  
 <span data-ttu-id="3d021-105">Una routine non è generica semplicemente in virtù di essere definita all'interno di una classe generica o di una struttura generica.</span><span class="sxs-lookup"><span data-stu-id="3d021-105">A procedure is not generic simply by virtue of being defined inside a generic class or a generic structure.</span></span> <span data-ttu-id="3d021-106">Per essere generico, la routine deve assumere almeno un parametro di tipo, oltre ai parametri normali che potrebbero essere necessari.</span><span class="sxs-lookup"><span data-stu-id="3d021-106">To be generic, the procedure must take at least one type parameter, in addition to any normal parameters it might take.</span></span> <span data-ttu-id="3d021-107">Una classe o una struttura generica può contenere routine non generiche e una classe, una struttura o un modulo non generico può contenere routine generiche.</span><span class="sxs-lookup"><span data-stu-id="3d021-107">A generic class or structure can contain nongeneric procedures, and a nongeneric class, structure, or module can contain generic procedures.</span></span>  
  
 <span data-ttu-id="3d021-108">Una routine generica può usare i parametri di tipo nell'elenco di parametri normali, nel tipo restituito, se presente, e nel codice della procedura.</span><span class="sxs-lookup"><span data-stu-id="3d021-108">A generic procedure can use its type parameters in its normal parameter list, in its return type if it has one, and in its procedure code.</span></span>  
  
## <a name="type-inference"></a><span data-ttu-id="3d021-109">Inferenza di tipi</span><span class="sxs-lookup"><span data-stu-id="3d021-109">Type Inference</span></span>  
 <span data-ttu-id="3d021-110">È possibile chiamare una routine generica senza fornire alcun argomento di tipo.</span><span class="sxs-lookup"><span data-stu-id="3d021-110">You can call a generic procedure without supplying any type arguments at all.</span></span> <span data-ttu-id="3d021-111">Se viene chiamato in questo modo, il compilatore tenta di determinare i tipi di dati appropriati da passare agli argomenti di tipo della stored procedure.</span><span class="sxs-lookup"><span data-stu-id="3d021-111">If you call it this way, the compiler attempts to determine the appropriate data types to pass to the procedure's type arguments.</span></span> <span data-ttu-id="3d021-112">Questa operazione viene definita *inferenza del tipo*.</span><span class="sxs-lookup"><span data-stu-id="3d021-112">This is called *type inference*.</span></span> <span data-ttu-id="3d021-113">Nel codice seguente viene illustrata una chiamata in cui il compilatore deduce che deve passare `String` il tipo al parametro di tipo `t` .</span><span class="sxs-lookup"><span data-stu-id="3d021-113">The following code shows a call in which the compiler infers that it should pass type `String` to the type parameter `t`.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 <span data-ttu-id="3d021-114">Se il compilatore non è in grado di dedurre gli argomenti di tipo dal contesto della chiamata, viene segnalato un errore.</span><span class="sxs-lookup"><span data-stu-id="3d021-114">If the compiler cannot infer the type arguments from the context of your call, it reports an error.</span></span> <span data-ttu-id="3d021-115">Una delle possibili cause di questo errore è la mancata corrispondenza della classificazione della matrice.</span><span class="sxs-lookup"><span data-stu-id="3d021-115">One possible cause of such an error is an array rank mismatch.</span></span> <span data-ttu-id="3d021-116">Si supponga, ad esempio, di definire un parametro normale come matrice di un parametro di tipo.</span><span class="sxs-lookup"><span data-stu-id="3d021-116">For example, suppose you define a normal parameter as an array of a type parameter.</span></span> <span data-ttu-id="3d021-117">Se si chiama la routine generica che fornisce una matrice di un rango diverso (numero di dimensioni), la mancata corrispondenza causa l'inferenza del tipo.</span><span class="sxs-lookup"><span data-stu-id="3d021-117">If you call the generic procedure supplying an array of a different rank (number of dimensions), the mismatch causes type inference to fail.</span></span> <span data-ttu-id="3d021-118">Nel codice seguente viene illustrata una chiamata in cui una matrice bidimensionale viene passata a una routine che prevede una matrice unidimensionale.</span><span class="sxs-lookup"><span data-stu-id="3d021-118">The following code shows a call in which a two-dimensional array is passed to a procedure that expects a one-dimensional array.</span></span>  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 <span data-ttu-id="3d021-119">È possibile richiamare l'inferenza del tipo solo omettendo tutti gli argomenti di tipo.</span><span class="sxs-lookup"><span data-stu-id="3d021-119">You can invoke type inference only by omitting all the type arguments.</span></span> <span data-ttu-id="3d021-120">Se si fornisce un solo argomento di tipo, è necessario fornirli tutti.</span><span class="sxs-lookup"><span data-stu-id="3d021-120">If you supply one type argument, you must supply them all.</span></span>  
  
 <span data-ttu-id="3d021-121">L'inferenza del tipo è supportata solo per le routine generiche.</span><span class="sxs-lookup"><span data-stu-id="3d021-121">Type inference is supported only for generic procedures.</span></span> <span data-ttu-id="3d021-122">Non è possibile richiamare l'inferenza del tipo su classi, strutture, interfacce o delegati generici.</span><span class="sxs-lookup"><span data-stu-id="3d021-122">You cannot invoke type inference on generic classes, structures, interfaces, or delegates.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d021-123">Esempio</span><span class="sxs-lookup"><span data-stu-id="3d021-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3d021-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3d021-124">Description</span></span>  
 <span data-ttu-id="3d021-125">Nell'esempio seguente viene definita una `Function` routine generica per trovare un particolare elemento in una matrice.</span><span class="sxs-lookup"><span data-stu-id="3d021-125">The following example defines a generic `Function` procedure to find a particular element in an array.</span></span> <span data-ttu-id="3d021-126">Definisce un parametro di tipo e lo usa per costruire i due parametri nell'elenco di parametri.</span><span class="sxs-lookup"><span data-stu-id="3d021-126">It defines one type parameter and uses it to construct the two parameters in the parameter list.</span></span>  
  
### <a name="code"></a><span data-ttu-id="3d021-127">Codice</span><span class="sxs-lookup"><span data-stu-id="3d021-127">Code</span></span>  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a><span data-ttu-id="3d021-128">Commenti</span><span class="sxs-lookup"><span data-stu-id="3d021-128">Comments</span></span>  
 <span data-ttu-id="3d021-129">Nell'esempio precedente è richiesta la possibilità di eseguire il confronto `searchValue` con ogni elemento di `searchArray` .</span><span class="sxs-lookup"><span data-stu-id="3d021-129">The preceding example requires the ability to compare `searchValue` against each element of `searchArray`.</span></span> <span data-ttu-id="3d021-130">Per garantire questa possibilità, vincola il parametro `T` di tipo per implementare l' <xref:System.IComparable%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3d021-130">To guarantee this ability, it constrains the type parameter `T` to implement the <xref:System.IComparable%601> interface.</span></span> <span data-ttu-id="3d021-131">Il codice usa il <xref:System.IComparable%601.CompareTo%2A> metodo anziché l' `=` operatore, perché non esiste alcuna garanzia che un argomento di tipo fornito per `T` supporti l' `=` operatore.</span><span class="sxs-lookup"><span data-stu-id="3d021-131">The code uses the <xref:System.IComparable%601.CompareTo%2A> method instead of the `=` operator, because there is no guarantee that a type argument supplied for `T` supports the `=` operator.</span></span>  
  
 <span data-ttu-id="3d021-132">È possibile testare la `findElement` procedura con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="3d021-132">You can test the `findElement` procedure with the following code.</span></span>  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 <span data-ttu-id="3d021-133">Le chiamate precedenti a `MsgBox` visualizzano rispettivamente "0", "1" e "-1".</span><span class="sxs-lookup"><span data-stu-id="3d021-133">The preceding calls to `MsgBox` display "0", "1", and "-1" respectively.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d021-134">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3d021-134">See also</span></span>

- [<span data-ttu-id="3d021-135">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3d021-135">Generic Types in Visual Basic</span></span>](generic-types.md)
- [<span data-ttu-id="3d021-136">Procedura: Definire una classe in grado di fornire funzionalità identiche con tipi di dati diversi</span><span class="sxs-lookup"><span data-stu-id="3d021-136">How to: Define a Class That Can Provide Identical Functionality on Different Data Types</span></span>](how-to-define-a-class-that-can-provide-identical-functionality.md)
- [<span data-ttu-id="3d021-137">Procedura: Usare una classe generica</span><span class="sxs-lookup"><span data-stu-id="3d021-137">How to: Use a Generic Class</span></span>](how-to-use-a-generic-class.md)
- [<span data-ttu-id="3d021-138">Procedure</span><span class="sxs-lookup"><span data-stu-id="3d021-138">Procedures</span></span>](../procedures/index.md)
- [<span data-ttu-id="3d021-139">Parametri e argomenti delle routine</span><span class="sxs-lookup"><span data-stu-id="3d021-139">Procedure Parameters and Arguments</span></span>](../procedures/procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3d021-140">Type List</span><span class="sxs-lookup"><span data-stu-id="3d021-140">Type List</span></span>](../../../language-reference/statements/type-list.md)
- [<span data-ttu-id="3d021-141">Elenco parametri</span><span class="sxs-lookup"><span data-stu-id="3d021-141">Parameter List</span></span>](../../../language-reference/statements/parameter-list.md)
