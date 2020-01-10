---
title: Boxing e unboxing - Guida per programmatori C#
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 4c17ba1917589dfd534b53ee3fb3efe67ddd02d7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75698794"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a><span data-ttu-id="aaddf-102">Boxing e unboxing (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="aaddf-102">Boxing and Unboxing (C# Programming Guide)</span></span>
<span data-ttu-id="aaddf-103">Il boxing è il processo di conversione di un [tipo di valore](../../language-reference/keywords/value-types.md) nel tipo `object` o in qualsiasi tipo di interfaccia implementato dal tipo valore.</span><span class="sxs-lookup"><span data-stu-id="aaddf-103">Boxing is the process of converting a [value type](../../language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="aaddf-104">Quando il CLR esegue il boxing di un tipo di valore, incapsula il valore in un'istanza <xref:System.Object?displayProperty=nameWithType> e lo archivia nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="aaddf-104">When the CLR boxes a value type, it wraps the value inside a <xref:System.Object?displayProperty=nameWithType> instance and stores it on the managed heap.</span></span> <span data-ttu-id="aaddf-105">Mediante la conversione unboxing, invece, il tipo valore viene estratto dall'oggetto.</span><span class="sxs-lookup"><span data-stu-id="aaddf-105">Unboxing extracts the value type from the object.</span></span> <span data-ttu-id="aaddf-106">La conversione boxing è implicita; quella unboxing è esplicita.</span><span class="sxs-lookup"><span data-stu-id="aaddf-106">Boxing is implicit; unboxing is explicit.</span></span> <span data-ttu-id="aaddf-107">Il concetto di conversione boxing e unboxing è alla base della visione unificata del sistema dei tipi in C#, in base alla quale un valore di qualsiasi tipo può essere considerato come un oggetto.</span><span class="sxs-lookup"><span data-stu-id="aaddf-107">The concept of boxing and unboxing underlies the C# unified view of the type system in which a value of any type can be treated as an object.</span></span>  
  
 <span data-ttu-id="aaddf-108">Nell'esempio seguente viene eseguita la conversione *boxing* della variabile intera `i` e la sua assegnazione all'oggetto `o`.</span><span class="sxs-lookup"><span data-stu-id="aaddf-108">In the following example, the integer variable `i` is *boxed* and assigned to object `o`.</span></span>  
  
 [!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]  
  
 <span data-ttu-id="aaddf-109">È quindi possibile eseguire l'unboxing dell'oggetto `o` e la sua assegnazione alla variabile intera `i`:</span><span class="sxs-lookup"><span data-stu-id="aaddf-109">The object `o` can then be unboxed and assigned to integer variable `i`:</span></span>  
  
 [!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]  
  
 <span data-ttu-id="aaddf-110">Nell'esempio seguente viene illustrato l'utilizzo della conversione boxing in C#.</span><span class="sxs-lookup"><span data-stu-id="aaddf-110">The following examples illustrate how boxing is used in C#.</span></span>  
  
 [!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]  
  
## <a name="performance"></a><span data-ttu-id="aaddf-111">Prestazioni</span><span class="sxs-lookup"><span data-stu-id="aaddf-111">Performance</span></span>  
 <span data-ttu-id="aaddf-112">Rispetto alle semplici assegnazioni, le conversioni boxing e unboxing sono processi onerosi dal punto di vista del calcolo.</span><span class="sxs-lookup"><span data-stu-id="aaddf-112">In relation to simple assignments, boxing and unboxing are computationally expensive processes.</span></span> <span data-ttu-id="aaddf-113">La conversione boxing di un tipo valore comporta infatti l'allocazione e la costruzione di un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="aaddf-113">When a value type is boxed, a new object must be allocated and constructed.</span></span> <span data-ttu-id="aaddf-114">A un livello inferiore, anche il cast richiesto per la conversione unboxing è oneroso dal punto di vista del calcolo.</span><span class="sxs-lookup"><span data-stu-id="aaddf-114">To a lesser degree, the cast required for unboxing is also expensive computationally.</span></span> <span data-ttu-id="aaddf-115">Per altre informazioni, vedere [Prestazioni](../../../framework/performance/performance-tips.md).</span><span class="sxs-lookup"><span data-stu-id="aaddf-115">For more information, see [Performance](../../../framework/performance/performance-tips.md).</span></span>  
  
## <a name="boxing"></a><span data-ttu-id="aaddf-116">Boxing</span><span class="sxs-lookup"><span data-stu-id="aaddf-116">Boxing</span></span>  
 <span data-ttu-id="aaddf-117">La conversione boxing viene utilizzata per archiviare tipi valore nell'heap sottoposto a Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="aaddf-117">Boxing is used to store value types in the garbage-collected heap.</span></span> <span data-ttu-id="aaddf-118">Il boxing è una conversione implicita di un [tipo di valore](../../language-reference/keywords/value-types.md) al tipo `object` o a qualsiasi tipo di interfaccia implementato da questo tipo di valore.</span><span class="sxs-lookup"><span data-stu-id="aaddf-118">Boxing is an implicit conversion of a [value type](../../language-reference/keywords/value-types.md) to the type `object` or to any interface type implemented by this value type.</span></span> <span data-ttu-id="aaddf-119">La conversione boxing di un tipo valore prevede l'allocazione di un'istanza dell'oggetto nell'heap e la copia del valore nel nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="aaddf-119">Boxing a value type allocates an object instance on the heap and copies the value into the new object.</span></span>  
  
 <span data-ttu-id="aaddf-120">Si consideri la seguente dichiarazione di una variabile di tipo valore:</span><span class="sxs-lookup"><span data-stu-id="aaddf-120">Consider the following declaration of a value-type variable:</span></span>  
  
 [!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]  
  
 <span data-ttu-id="aaddf-121">L'istruzione seguente applica implicitamente l'operazione di conversione boxing alla variabile `i`:</span><span class="sxs-lookup"><span data-stu-id="aaddf-121">The following statement implicitly applies the boxing operation on the variable `i`:</span></span>  
  
 [!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]  
  
 <span data-ttu-id="aaddf-122">Il risultato di questa istruzione è la creazione, sullo stack, di un riferimento all'oggetto `o` che fa riferimento a un valore di tipo `int` nell'heap.</span><span class="sxs-lookup"><span data-stu-id="aaddf-122">The result of this statement is creating an object reference `o`, on the stack, that references a value of the type `int`, on the heap.</span></span> <span data-ttu-id="aaddf-123">Questo valore è una copia di quello di tipo valore assegnato alla variabile `i`.</span><span class="sxs-lookup"><span data-stu-id="aaddf-123">This value is a copy of the value-type value assigned to the variable `i`.</span></span> <span data-ttu-id="aaddf-124">La differenza tra le due variabili `i` e `o` è illustrata nella figura seguente della conversione boxing:</span><span class="sxs-lookup"><span data-stu-id="aaddf-124">The difference between the two variables, `i` and `o`, is illustrated in the following image of boxing conversion:</span></span>  
  
 ![Figura che mostra la differenza tra le variabili i e o.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)    
  
 <span data-ttu-id="aaddf-126">È inoltre possibile, anche se non obbligatorio, eseguire la conversione boxing in modo esplicito, come nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="aaddf-126">It is also possible to perform the boxing explicitly as in the following example, but explicit boxing is never required:</span></span>  
  
 [!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]  
  
## <a name="description"></a><span data-ttu-id="aaddf-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="aaddf-127">Description</span></span>  
 <span data-ttu-id="aaddf-128">In questo esempio viene eseguita la conversione boxing della variabile intera `i` in un oggetto `o`.</span><span class="sxs-lookup"><span data-stu-id="aaddf-128">This example converts an integer variable `i` to an object `o` by using boxing.</span></span> <span data-ttu-id="aaddf-129">Il valore archiviato nella variabile `i` viene quindi modificato da `123` a `456`.</span><span class="sxs-lookup"><span data-stu-id="aaddf-129">Then, the value stored in the variable `i` is changed from `123` to `456`.</span></span> <span data-ttu-id="aaddf-130">Nell'esempio il tipo valore originale e l'oggetto sottoposto a conversione boxing utilizzano posizioni di memoria separate, pertanto possono archiviare valori diversi.</span><span class="sxs-lookup"><span data-stu-id="aaddf-130">The example shows that the original value type and the boxed object use separate memory locations, and therefore can store different values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaddf-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="aaddf-131">Example</span></span>  
 [!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]  
  
## <a name="unboxing"></a><span data-ttu-id="aaddf-132">Conversione unboxing</span><span class="sxs-lookup"><span data-stu-id="aaddf-132">Unboxing</span></span>  
 <span data-ttu-id="aaddf-133">L'unboxing è una conversione esplicita dal tipo `object` a un [tipo di valore](../../language-reference/keywords/value-types.md) o da un tipo di interfaccia a un tipo di valore che implementa l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="aaddf-133">Unboxing is an explicit conversion from the type `object` to a [value type](../../language-reference/keywords/value-types.md) or from an interface type to a value type that implements the interface.</span></span> <span data-ttu-id="aaddf-134">Un'operazione unboxing prevede le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="aaddf-134">An unboxing operation consists of:</span></span>  
  
- <span data-ttu-id="aaddf-135">Controllo dell'istanza di oggetto per verificare che si tratti di un valore sottoposto a conversione boxing del tipo valore specificato.</span><span class="sxs-lookup"><span data-stu-id="aaddf-135">Checking the object instance to make sure that it is a boxed value of the given value type.</span></span>  
  
- <span data-ttu-id="aaddf-136">Copia del valore dall'istanza alla variabile di tipo valore.</span><span class="sxs-lookup"><span data-stu-id="aaddf-136">Copying the value from the instance into the value-type variable.</span></span>  
  
 <span data-ttu-id="aaddf-137">Le istruzioni seguenti illustrano operazioni di conversione boxing e unboxing:</span><span class="sxs-lookup"><span data-stu-id="aaddf-137">The following statements demonstrate both boxing and unboxing operations:</span></span>  
  
 [!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]  
  
 <span data-ttu-id="aaddf-138">La figura seguente mostra il risultato delle istruzioni precedenti:</span><span class="sxs-lookup"><span data-stu-id="aaddf-138">The following figure demonstrates the result of the previous statements:</span></span> 
  
 ![Figura che illustra una conversione unboxing.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)
  
 <span data-ttu-id="aaddf-140">Per eseguire correttamente la conversione unboxing di tipi valore in fase di esecuzione, è necessario che l'elemento sottoposto a conversione unboxing faccia riferimento a un oggetto creato in precedenza tramite la conversione boxing di un'istanza di tale tipo valore.</span><span class="sxs-lookup"><span data-stu-id="aaddf-140">For the unboxing of value types to succeed at run time, the item being unboxed must be a reference to an object that was previously created by boxing an instance of that value type.</span></span> <span data-ttu-id="aaddf-141">Il tentativo di eseguire la conversione unboxing di un valore `null` genera <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="aaddf-141">Attempting to unbox `null` causes a <xref:System.NullReferenceException>.</span></span> <span data-ttu-id="aaddf-142">Il tentativo di eseguire la conversione unboxing di un riferimento a un tipo valore incompatibile genera <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="aaddf-142">Attempting to unbox a reference to an incompatible value type causes an <xref:System.InvalidCastException>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aaddf-143">Esempio</span><span class="sxs-lookup"><span data-stu-id="aaddf-143">Example</span></span>  
 <span data-ttu-id="aaddf-144">Nell'esempio riportato di seguito viene illustrato un caso di unboxing non valido, nonché l'elemento `InvalidCastException` risultante.</span><span class="sxs-lookup"><span data-stu-id="aaddf-144">The following example demonstrates a case of invalid unboxing and the resulting `InvalidCastException`.</span></span> <span data-ttu-id="aaddf-145">Se si utilizza `try` e `catch`, quando si verifica l'errore viene visualizzato un messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="aaddf-145">Using `try` and `catch`, an error message is displayed when the error occurs.</span></span>  
  
 [!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]  
  
 <span data-ttu-id="aaddf-146">Questo programma restituisce:</span><span class="sxs-lookup"><span data-stu-id="aaddf-146">This program outputs:</span></span>  
  
 `Specified cast is not valid. Error: Incorrect unboxing.`  
  
 <span data-ttu-id="aaddf-147">Se si modifica l'istruzione:</span><span class="sxs-lookup"><span data-stu-id="aaddf-147">If you change the statement:</span></span>  
  
```csharp
int j = (short) o;  
```  
  
 <span data-ttu-id="aaddf-148">in:</span><span class="sxs-lookup"><span data-stu-id="aaddf-148">to:</span></span>  
  
```csharp
int j = (int) o;  
```  
  
 <span data-ttu-id="aaddf-149">la conversione verrà eseguita e si otterrà l'output:</span><span class="sxs-lookup"><span data-stu-id="aaddf-149">the conversion will be performed, and you will get the output:</span></span>  
  
 `Unboxing OK.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="aaddf-150">Specifica del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="aaddf-150">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="related-sections"></a><span data-ttu-id="aaddf-151">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="aaddf-151">Related Sections</span></span>  
 <span data-ttu-id="aaddf-152">Per ulteriori informazioni:</span><span class="sxs-lookup"><span data-stu-id="aaddf-152">For more information:</span></span>  
  
- [<span data-ttu-id="aaddf-153">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="aaddf-153">Reference Types</span></span>](../../language-reference/keywords/reference-types.md)  
  
- [<span data-ttu-id="aaddf-154">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="aaddf-154">Value Types</span></span>](../../language-reference/keywords/value-types.md)  
  
## <a name="see-also"></a><span data-ttu-id="aaddf-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aaddf-155">See also</span></span>

- [<span data-ttu-id="aaddf-156">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="aaddf-156">C# Programming Guide</span></span>](../index.md)
