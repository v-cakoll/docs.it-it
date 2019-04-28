---
title: Celle di riferimento
description: Informazioni su come F# celle di riferimento sono posizioni di archiviazione che consentono di creare valori modificabili con semantica di riferimento.
ms.date: 05/16/2016
ms.openlocfilehash: e4fcd3cf1abcf5f5e3b4d5439c9215b79ff8dbcd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795401"
---
# <a name="reference-cells"></a><span data-ttu-id="83822-103">Celle di riferimento</span><span class="sxs-lookup"><span data-stu-id="83822-103">Reference Cells</span></span>

<span data-ttu-id="83822-104">*Fare riferimento alle celle* sono posizioni di archiviazione che consentono di creare valori modificabili con semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83822-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="83822-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83822-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="83822-106">Note</span><span class="sxs-lookup"><span data-stu-id="83822-106">Remarks</span></span>

<span data-ttu-id="83822-107">L'operatore `ref` viene utilizzato prima di un valore per creare una nuova cella di riferimento che incapsuli il valore.</span><span class="sxs-lookup"><span data-stu-id="83822-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="83822-108">È quindi possibile modificare il valore sottostante, in quanto è modificabile.</span><span class="sxs-lookup"><span data-stu-id="83822-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="83822-109">Una cella di riferimento contiene un valore effettivo e non solo un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="83822-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="83822-110">Quando si crea una cella di riferimento utilizzando l'operatore `ref`, si crea una copia del valore sottostante come valore modificabile incapsulato.</span><span class="sxs-lookup"><span data-stu-id="83822-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="83822-111">È possibile dereferenziare una cella di riferimento utilizzando l'operatore `!` (punto esclamativo).</span><span class="sxs-lookup"><span data-stu-id="83822-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="83822-112">Nell'esempio di codice seguente vengono illustrati la dichiarazione e l'utilizzo di celle di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83822-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="83822-113">L'output è `50`.</span><span class="sxs-lookup"><span data-stu-id="83822-113">The output is `50`.</span></span>

<span data-ttu-id="83822-114">Le celle di riferimento sono istanze del tipo di record generico `Ref`, dichiarato come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="83822-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="83822-115">Il tipo `'a ref` è sinonimo di `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="83822-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="83822-116">Il primo viene visualizzato dal compilatore e da IntelliSense nell'interfaccia IDE per questo tipo, mentre il secondo rappresenta la definizione sottostante.</span><span class="sxs-lookup"><span data-stu-id="83822-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="83822-117">L'operatore `ref` consente di creare una nuova cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83822-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="83822-118">Il codice seguente rappresenta la dichiarazione dell'operatore `ref`.</span><span class="sxs-lookup"><span data-stu-id="83822-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="83822-119">Nella tabella seguente sono indicate le funzionalità disponibili nella cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83822-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="83822-120">Operatore, membro o campo</span><span class="sxs-lookup"><span data-stu-id="83822-120">Operator, member, or field</span></span>|<span data-ttu-id="83822-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83822-121">Description</span></span>|<span data-ttu-id="83822-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="83822-122">Type</span></span>|<span data-ttu-id="83822-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="83822-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="83822-124">`!` (operatore di dereferenziazione)</span><span class="sxs-lookup"><span data-stu-id="83822-124">`!` (dereference operator)</span></span>|<span data-ttu-id="83822-125">Restituisce il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="83822-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="83822-126">`:=` (operatore di assegnazione)</span><span class="sxs-lookup"><span data-stu-id="83822-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="83822-127">Modifica il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="83822-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="83822-128">`ref` (operatore)</span><span class="sxs-lookup"><span data-stu-id="83822-128">`ref` (operator)</span></span>|<span data-ttu-id="83822-129">Incapsula un valore in una nuova cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83822-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="83822-130">`Value` (proprietà)</span><span class="sxs-lookup"><span data-stu-id="83822-130">`Value` (property)</span></span>|<span data-ttu-id="83822-131">Ottiene o imposta il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="83822-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="83822-132">`contents` (campo del record)</span><span class="sxs-lookup"><span data-stu-id="83822-132">`contents` (record field)</span></span>|<span data-ttu-id="83822-133">Ottiene o imposta il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="83822-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|

<span data-ttu-id="83822-134">È possibile accedere al valore sottostante in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="83822-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="83822-135">Il valore restituito dall'operatore di dereferenziazione (`!`) non è un valore assegnabile.</span><span class="sxs-lookup"><span data-stu-id="83822-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="83822-136">Se pertanto si modifica il valore sottostante, è necessario utilizzare l'operatore di assegnazione (`:=`).</span><span class="sxs-lookup"><span data-stu-id="83822-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="83822-137">Sia la proprietà `Value` che il campo `contents` sono valori assegnabili</span><span class="sxs-lookup"><span data-stu-id="83822-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="83822-138">e possono pertanto essere utilizzati per accedere al valore sottostante o per modificare tale valore, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="83822-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="83822-139">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="83822-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="83822-140">Il campo `contents` viene fornito per garantire compatibilità con altre versioni di ML e comporta la generazione di un avviso durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="83822-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="83822-141">Per disabilitare l'avviso, utilizzare l'opzione del compilatore `--mlcompatibility`.</span><span class="sxs-lookup"><span data-stu-id="83822-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="83822-142">Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="83822-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="83822-143">C#i programmatori devono sapere che `ref` in C# non è la stessa funzione illustrata in `ref` in F#.</span><span class="sxs-lookup"><span data-stu-id="83822-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="83822-144">Costruisce l'equivalente F# vengono [zkratka](byrefs.md), che sono un concetto diverso dalle celle di riferimento.</span><span class="sxs-lookup"><span data-stu-id="83822-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="83822-145">I valori contrassegnati come `mutable`può essere automaticamente promossa a `'a ref` acquisiti da una chiusura dei tag, vedere [valori](values/index.md).</span><span class="sxs-lookup"><span data-stu-id="83822-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="83822-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83822-146">See also</span></span>

- [<span data-ttu-id="83822-147">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="83822-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="83822-148">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="83822-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="83822-149">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="83822-149">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="83822-150">Valori</span><span class="sxs-lookup"><span data-stu-id="83822-150">Values</span></span>](values/index.md)
