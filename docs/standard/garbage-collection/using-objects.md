---
title: Uso di oggetti che implementano IDisposable
description: Informazioni su come usare gli oggetti che implementano l'interfaccia IDisposable in .NET. I tipi che usano risorse non gestite implementano IDisposable per consentire il rimborso delle risorse.
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 7d5d4080f22aab6870a230d495b4a4b9ebcb3b96
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599854"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="7b166-104">Uso di oggetti che implementano IDisposable</span><span class="sxs-lookup"><span data-stu-id="7b166-104">Using objects that implement IDisposable</span></span>

<span data-ttu-id="7b166-105">Il Garbage Collector di Common Language Runtime recupera la memoria usata dagli oggetti gestiti, ma i tipi che usano risorse non gestite implementano l' <xref:System.IDisposable> interfaccia per consentire il rimborso delle risorse necessarie per queste risorse non gestite.</span><span class="sxs-lookup"><span data-stu-id="7b166-105">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the resources needed by these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="7b166-106">Dopo avere utilizzato un oggetto che implementa <xref:System.IDisposable>, è necessario chiamare l'implementazione <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> dell'oggetto.</span><span class="sxs-lookup"><span data-stu-id="7b166-106">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="7b166-107">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="7b166-107">You can do this in one of two ways:</span></span>

- <span data-ttu-id="7b166-108">Con l' `using` istruzione C# ( `Using` in Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="7b166-108">With the C# `using` statement (`Using` in Visual Basic).</span></span>
- <span data-ttu-id="7b166-109">Implementando un `try/finally` blocco e chiamando l'oggetto <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in `finally` .</span><span class="sxs-lookup"><span data-stu-id="7b166-109">By implementing a `try/finally` block, and calling the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in the `finally`.</span></span>

## <a name="the-using-statement"></a><span data-ttu-id="7b166-110">Istruzione using</span><span class="sxs-lookup"><span data-stu-id="7b166-110">The using statement</span></span>

<span data-ttu-id="7b166-111">L' [ `using` istruzione](../../csharp/language-reference/keywords/using-statement.md) in C# e l' [ `Using` istruzione](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic semplificano il codice che è necessario scrivere per pulire un oggetto.</span><span class="sxs-lookup"><span data-stu-id="7b166-111">The [`using` statement](../../csharp/language-reference/keywords/using-statement.md) in C# and the [`Using` statement](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic simplify the code that you must write to cleanup an object.</span></span> <span data-ttu-id="7b166-112">L'istruzione `using` ottiene una o più risorse, esegue le istruzioni specificate ed elimina l'oggetto in modo automatico.</span><span class="sxs-lookup"><span data-stu-id="7b166-112">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="7b166-113">L'istruzione `using` è comunque utile solo per gli oggetti usati nell'ambito del metodo in cui vengono costruiti.</span><span class="sxs-lookup"><span data-stu-id="7b166-113">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>

<span data-ttu-id="7b166-114">Nell'esempio seguente viene utilizzata l'istruzione `using` per creare e rilasciare un oggetto <xref:System.IO.StreamReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7b166-114">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

<span data-ttu-id="7b166-115">Sebbene la <xref:System.IO.StreamReader> classe implementi l' <xref:System.IDisposable> interfaccia, che indica che usa una risorsa non gestita, nell'esempio non viene chiamato in modo esplicito il <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> metodo.</span><span class="sxs-lookup"><span data-stu-id="7b166-115">Although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7b166-116">Quando nel compilatore C# o Visual Basic viene rilevata l'istruzione `using`, viene generato il linguaggio intermedio (IL) equivalente al codice seguente, che contiene un blocco `try/finally` in modo esplicito.</span><span class="sxs-lookup"><span data-stu-id="7b166-116">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

<span data-ttu-id="7b166-117">L'istruzione `using` C# è consente anche di acquisire più risorse in un'unica istruzione, che equivale internamente all'uso di più istruzioni `using` annidate.</span><span class="sxs-lookup"><span data-stu-id="7b166-117">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="7b166-118">Nell'esempio seguente viene creata l'istanza di due oggetti <xref:System.IO.StreamReader> per leggere il contenuto di due diversi file.</span><span class="sxs-lookup"><span data-stu-id="7b166-118">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="7b166-119">Blocco try/finally</span><span class="sxs-lookup"><span data-stu-id="7b166-119">Try/finally block</span></span>

<span data-ttu-id="7b166-120">Anziché eseguire il wrapping di un blocco `try/finally` in un'istruzione `using`, è possibile implementare direttamente il blocco `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="7b166-120">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="7b166-121">Potrebbe trattarsi dello stile di codifica personale oppure è possibile eseguire questa operazione per uno dei motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b166-121">It may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>

- <span data-ttu-id="7b166-122">Per includere un `catch` blocco per gestire le eccezioni generate nel `try` blocco.</span><span class="sxs-lookup"><span data-stu-id="7b166-122">To include a `catch` block to handle exceptions thrown in the `try` block.</span></span> <span data-ttu-id="7b166-123">In caso contrario, tutte le eccezioni generate all'interno dell' `using` istruzione non vengono gestite.</span><span class="sxs-lookup"><span data-stu-id="7b166-123">Otherwise, any exceptions thrown within the `using` statement are unhandled.</span></span>

- <span data-ttu-id="7b166-124">Creare un'istanza di un oggetto che implementa <xref:System.IDisposable> il cui ambito non è locale rispetto al blocco in cui viene dichiarato.</span><span class="sxs-lookup"><span data-stu-id="7b166-124">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>

<span data-ttu-id="7b166-125">L'esempio seguente è simile a quello precedente, con la differenza che in questo viene usato un blocco `try/catch/finally` per creare un'istanza di un oggetto <xref:System.IO.StreamReader>, utilizzarla ed eliminarla e per gestire le eccezioni generate dal costruttore <xref:System.IO.StreamReader> e dal relativo metodo <xref:System.IO.StreamReader.ReadToEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b166-125">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="7b166-126">Il codice nel `finally` blocco controlla che l'oggetto che implementa <xref:System.IDisposable> non sia `null` prima di chiamare il <xref:System.IDisposable.Dispose%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="7b166-126">The code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="7b166-127">L'omissione di tale controllo può provocare un'eccezione <xref:System.NullReferenceException> in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7b166-127">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

<span data-ttu-id="7b166-128">È possibile usare questo modello di base se si decide di implementare o è necessario implementare un blocco `try/finally`, poiché il linguaggio di programmazione non supporta un'istruzione `using` ma consente chiamate dirette al metodo <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b166-128">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span>

## <a name="idisposable-instance-members"></a><span data-ttu-id="7b166-129">Membri di istanza IDisposable</span><span class="sxs-lookup"><span data-stu-id="7b166-129">IDisposable instance members</span></span>

<span data-ttu-id="7b166-130">Se una classe include un' <xref:System.IDisposable> implementazione come membro di istanza, ovvero un campo o una proprietà, la classe deve implementare anche <xref:System.IDisposable> .</span><span class="sxs-lookup"><span data-stu-id="7b166-130">If a class holds an <xref:System.IDisposable> implementation as an instance member, either a field or a property, the class should also implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="7b166-131">Per altre informazioni, vedere [implementare un'eliminazione a catena](implementing-dispose.md#cascade-dispose-calls).</span><span class="sxs-lookup"><span data-stu-id="7b166-131">For more information, see [implement a cascade dispose](implementing-dispose.md#cascade-dispose-calls).</span></span>

## <a name="see-also"></a><span data-ttu-id="7b166-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b166-132">See also</span></span>

- [<span data-ttu-id="7b166-133">Pulizia delle risorse non gestite</span><span class="sxs-lookup"><span data-stu-id="7b166-133">Cleaning up unmanaged resources</span></span>](unmanaged.md)
- [<span data-ttu-id="7b166-134">Istruzione using (riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="7b166-134">using Statement (C# Reference)</span></span>](../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="7b166-135">Istruzione using (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b166-135">Using Statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/using-statement.md)
