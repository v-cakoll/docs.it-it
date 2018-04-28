---
title: Celle di riferimento (F#)
description: 'Informazioni su come le celle di riferimento di F # sono percorsi di archiviazione che consentono di creare valori modificabili con semantica di riferimento.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: e017adb2a031dff996892e2bb6585fc95f644ff9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="reference-cells"></a><span data-ttu-id="328f4-103">Celle di riferimento</span><span class="sxs-lookup"><span data-stu-id="328f4-103">Reference Cells</span></span>

<span data-ttu-id="328f4-104">*Celle di riferimento* sono percorsi di archiviazione che consentono di creare valori modificabili con semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="328f4-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="328f4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="328f4-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="328f4-106">Note</span><span class="sxs-lookup"><span data-stu-id="328f4-106">Remarks</span></span>
<span data-ttu-id="328f4-107">L'operatore `ref` viene utilizzato prima di un valore per creare una nuova cella di riferimento che incapsuli il valore.</span><span class="sxs-lookup"><span data-stu-id="328f4-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="328f4-108">È quindi possibile modificare il valore sottostante, in quanto è modificabile.</span><span class="sxs-lookup"><span data-stu-id="328f4-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="328f4-109">Una cella di riferimento contiene un valore effettivo e non solo un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="328f4-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="328f4-110">Quando si crea una cella di riferimento utilizzando l'operatore `ref`, si crea una copia del valore sottostante come valore modificabile incapsulato.</span><span class="sxs-lookup"><span data-stu-id="328f4-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="328f4-111">È possibile dereferenziare una cella di riferimento utilizzando l'operatore `!` (punto esclamativo).</span><span class="sxs-lookup"><span data-stu-id="328f4-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="328f4-112">Nell'esempio di codice seguente vengono illustrati la dichiarazione e l'utilizzo di celle di riferimento.</span><span class="sxs-lookup"><span data-stu-id="328f4-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="328f4-113">L'output è `50`.</span><span class="sxs-lookup"><span data-stu-id="328f4-113">The output is `50`.</span></span>

<span data-ttu-id="328f4-114">Le celle di riferimento sono istanze del tipo di record generico `Ref`, dichiarato come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="328f4-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="328f4-115">Il tipo `'a ref` è sinonimo di `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="328f4-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="328f4-116">Il primo viene visualizzato dal compilatore e da IntelliSense nell'interfaccia IDE per questo tipo, mentre il secondo rappresenta la definizione sottostante.</span><span class="sxs-lookup"><span data-stu-id="328f4-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="328f4-117">L'operatore `ref` consente di creare una nuova cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="328f4-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="328f4-118">Il codice seguente rappresenta la dichiarazione dell'operatore `ref`.</span><span class="sxs-lookup"><span data-stu-id="328f4-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="328f4-119">Nella tabella seguente sono indicate le funzionalità disponibili nella cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="328f4-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="328f4-120">Operatore, membro o campo</span><span class="sxs-lookup"><span data-stu-id="328f4-120">Operator, member, or field</span></span>|<span data-ttu-id="328f4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="328f4-121">Description</span></span>|<span data-ttu-id="328f4-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="328f4-122">Type</span></span>|<span data-ttu-id="328f4-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="328f4-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="328f4-124">`!` (operatore di dereferenziazione)</span><span class="sxs-lookup"><span data-stu-id="328f4-124">`!` (dereference operator)</span></span>|<span data-ttu-id="328f4-125">Restituisce il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="328f4-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="328f4-126">`:=` (operatore di assegnazione)</span><span class="sxs-lookup"><span data-stu-id="328f4-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="328f4-127">Modifica il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="328f4-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="328f4-128">`ref` (operatore)</span><span class="sxs-lookup"><span data-stu-id="328f4-128">`ref` (operator)</span></span>|<span data-ttu-id="328f4-129">Incapsula un valore in una nuova cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="328f4-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="328f4-130">`Value` (proprietà)</span><span class="sxs-lookup"><span data-stu-id="328f4-130">`Value` (property)</span></span>|<span data-ttu-id="328f4-131">Ottiene o imposta il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="328f4-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="328f4-132">`contents` (campo del record)</span><span class="sxs-lookup"><span data-stu-id="328f4-132">`contents` (record field)</span></span>|<span data-ttu-id="328f4-133">Ottiene o imposta il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="328f4-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="328f4-134">È possibile accedere al valore sottostante in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="328f4-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="328f4-135">Il valore restituito dall'operatore di dereferenziazione (`!`) non è un valore assegnabile.</span><span class="sxs-lookup"><span data-stu-id="328f4-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="328f4-136">Se pertanto si modifica il valore sottostante, è necessario utilizzare l'operatore di assegnazione (`:=`).</span><span class="sxs-lookup"><span data-stu-id="328f4-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="328f4-137">Sia la proprietà `Value` che il campo `contents` sono valori assegnabili</span><span class="sxs-lookup"><span data-stu-id="328f4-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="328f4-138">e possono pertanto essere utilizzati per accedere al valore sottostante o per modificare tale valore, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="328f4-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="328f4-139">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="328f4-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="328f4-140">Il campo `contents` viene fornito per garantire compatibilità con altre versioni di ML e comporta la generazione di un avviso durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="328f4-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="328f4-141">Per disabilitare l'avviso, utilizzare l'opzione del compilatore `--mlcompatibility`.</span><span class="sxs-lookup"><span data-stu-id="328f4-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="328f4-142">Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="328f4-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="328f4-143">Nell'esempio di codice seguente viene illustrato l'utilizzo di celle di riferimento nel passaggio dei parametri.</span><span class="sxs-lookup"><span data-stu-id="328f4-143">The following code illustrates the use of reference cells in parameter passing.</span></span> <span data-ttu-id="328f4-144">Il tipo di Incrementatore ha un metodo Increment che accetta un parametro che include il tipo di parametro byref.</span><span class="sxs-lookup"><span data-stu-id="328f4-144">The Incrementor type has a method Increment that takes a parameter that includes byref in the parameter type.</span></span> <span data-ttu-id="328f4-145">Byref nel tipo di parametro indica che i chiamanti devono passare una cella di riferimento o l'indirizzo di una variabile tipica del tipo specificato, in questo caso int Il codice restante viene illustrato come chiamare Increment con entrambi i tipi di argomenti e viene illustrato come utilizzare l'operatore di riferimento in una variabile per creare una cella di riferimento (ref myDelta1).</span><span class="sxs-lookup"><span data-stu-id="328f4-145">The byref in the parameter type indicates that callers must pass a reference cell or the address of a typical variable of the specified type, in this case int. The remaining code illustrates how to call Increment with both of these types of arguments, and shows the use of the ref operator on a variable to create a reference cell (ref myDelta1).</span></span> <span data-ttu-id="328f4-146">Viene quindi illustrato l'utilizzo dell'operatore address-of (&amp;) per generare un argomento appropriato.</span><span class="sxs-lookup"><span data-stu-id="328f4-146">It then shows the use of the address-of operator (&amp;) to generate an appropriate argument.</span></span> <span data-ttu-id="328f4-147">Infine, l'incremento viene chiamato nuovamente utilizzando una cella di riferimento viene dichiarata utilizzando un binding let.</span><span class="sxs-lookup"><span data-stu-id="328f4-147">Finally, the Increment method is called again by using a reference cell that is declared by using a let binding.</span></span> <span data-ttu-id="328f4-148">L'ultima riga del codice viene illustrato come utilizzare il!</span><span class="sxs-lookup"><span data-stu-id="328f4-148">The final line of code demonstrates the use of the !</span></span> <span data-ttu-id="328f4-149">operatore per dereferenziare la cella di riferimento per la stampa.</span><span class="sxs-lookup"><span data-stu-id="328f4-149">operator to dereference the reference cell for printing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2204.fs)]

<span data-ttu-id="328f4-150">Per ulteriori informazioni su come passare per riferimento, vedere [parametri e argomenti](parameters-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="328f4-150">For more information about how to pass by reference, see [Parameters and Arguments](parameters-and-arguments.md).</span></span>

>[!NOTE]
<span data-ttu-id="328f4-151">I programmatori c# devono sapere che ref funziona in modo diverso in F # rispetto a quello usato in c#.</span><span class="sxs-lookup"><span data-stu-id="328f4-151">C# programmers should know that ref works differently in F# than it does in C#.</span></span> <span data-ttu-id="328f4-152">Ad esempio, l'utilizzo di riferimento quando si passa un argomento non hanno lo stesso effetto in F # a quanto accade in c#.</span><span class="sxs-lookup"><span data-stu-id="328f4-152">For example, the use of ref when you pass an argument does not have the same effect in F# as it does in C#.</span></span>

## <a name="consuming-c-ref-returns"></a><span data-ttu-id="328f4-153">Utilizzo in c# `ref` restituisce</span><span class="sxs-lookup"><span data-stu-id="328f4-153">Consuming C# `ref` returns</span></span>

<span data-ttu-id="328f4-154">A partire da F # 4.1, è possibile utilizzare `ref` restituisce generato in c#.</span><span class="sxs-lookup"><span data-stu-id="328f4-154">Starting with F# 4.1, you can consume `ref` returns generated in C#.</span></span>  <span data-ttu-id="328f4-155">Il risultato della chiamata di questo tipo è un `byref<_>` puntatore.</span><span class="sxs-lookup"><span data-stu-id="328f4-155">The result of such a call is a `byref<_>` pointer.</span></span>

<span data-ttu-id="328f4-156">Il seguente metodo c#:</span><span class="sxs-lookup"><span data-stu-id="328f4-156">The following C# method:</span></span>

```csharp
namespace RefReturns
{
    public static class RefClass
    {
        public static ref int Find(int val, int[] vals)
        {
            for (int i = 0; i < vals.Length; i++)
            {
                if (vals[i] == val)
                {
                    return ref numbers[i]; // Returns the location, not the value
                }
            }

            throw new IndexOutOfRangeException($"{nameof(number)} not found");
        }
    }
}
```

<span data-ttu-id="328f4-157">Può essere trasparente chiamato da F # con alcuna sintassi particolare:</span><span class="sxs-lookup"><span data-stu-id="328f4-157">Can be transparently called by F# with no special syntax:</span></span>

```fsharp
open RefReturns

let consumeRefReturn() =
    let result = RefClass.Find(3, [| 1; 2; 3; 4; 5 |]) // 'result' is of type 'byref<int>'.
    ()
```

<span data-ttu-id="328f4-158">È inoltre possibile dichiarare funzioni che richiedono un `ref` restituire come input, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="328f4-158">You can also declare functions which could take a `ref` return as input, for example:</span></span>

```fsharp
let f (x: byref<int>) = &x
```

<span data-ttu-id="328f4-159">Non è attualmente possibile generare un `ref` restituito in F # che poteva essere usata in c#.</span><span class="sxs-lookup"><span data-stu-id="328f4-159">There is currently no way to generate a `ref` return in F# which could be consumed in C#.</span></span>

## <a name="see-also"></a><span data-ttu-id="328f4-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="328f4-160">See Also</span></span>
[<span data-ttu-id="328f4-161">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="328f4-161">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="328f4-162">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="328f4-162">Parameters and Arguments</span></span>](parameters-and-arguments.md)

[<span data-ttu-id="328f4-163">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="328f4-163">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
