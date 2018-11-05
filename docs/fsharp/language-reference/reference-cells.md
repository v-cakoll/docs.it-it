---
title: Celle di riferimento (F#)
description: 'Informazioni su come le celle di riferimento di F # sono posizioni di archiviazione che consentono di creare valori modificabili con semantica di riferimento.'
ms.date: 05/16/2016
ms.openlocfilehash: e2e1a91c62fd76e4992bc5ae11bb672766850718
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "44192265"
---
# <a name="reference-cells"></a><span data-ttu-id="524f0-103">Celle di riferimento</span><span class="sxs-lookup"><span data-stu-id="524f0-103">Reference Cells</span></span>

<span data-ttu-id="524f0-104">*Fare riferimento alle celle* sono posizioni di archiviazione che consentono di creare valori modificabili con semantica di riferimento.</span><span class="sxs-lookup"><span data-stu-id="524f0-104">*Reference cells* are storage locations that enable you to create mutable values with reference semantics.</span></span>

## <a name="syntax"></a><span data-ttu-id="524f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="524f0-105">Syntax</span></span>

```fsharp
ref expression
```

## <a name="remarks"></a><span data-ttu-id="524f0-106">Note</span><span class="sxs-lookup"><span data-stu-id="524f0-106">Remarks</span></span>

<span data-ttu-id="524f0-107">L'operatore `ref` viene utilizzato prima di un valore per creare una nuova cella di riferimento che incapsuli il valore.</span><span class="sxs-lookup"><span data-stu-id="524f0-107">You use the `ref` operator before a value to create a new reference cell that encapsulates the value.</span></span> <span data-ttu-id="524f0-108">È quindi possibile modificare il valore sottostante, in quanto è modificabile.</span><span class="sxs-lookup"><span data-stu-id="524f0-108">You can then change the underlying value because it is mutable.</span></span>

<span data-ttu-id="524f0-109">Una cella di riferimento contiene un valore effettivo e non solo un indirizzo.</span><span class="sxs-lookup"><span data-stu-id="524f0-109">A reference cell holds an actual value; it is not just an address.</span></span> <span data-ttu-id="524f0-110">Quando si crea una cella di riferimento utilizzando l'operatore `ref`, si crea una copia del valore sottostante come valore modificabile incapsulato.</span><span class="sxs-lookup"><span data-stu-id="524f0-110">When you create a reference cell by using the `ref` operator, you create a copy of the underlying value as an encapsulated mutable value.</span></span>

<span data-ttu-id="524f0-111">È possibile dereferenziare una cella di riferimento utilizzando l'operatore `!` (punto esclamativo).</span><span class="sxs-lookup"><span data-stu-id="524f0-111">You can dereference a reference cell by using the `!` (bang) operator.</span></span>

<span data-ttu-id="524f0-112">Nell'esempio di codice seguente vengono illustrati la dichiarazione e l'utilizzo di celle di riferimento.</span><span class="sxs-lookup"><span data-stu-id="524f0-112">The following code example illustrates the declaration and use of reference cells.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2201.fs)]

<span data-ttu-id="524f0-113">L'output è `50`.</span><span class="sxs-lookup"><span data-stu-id="524f0-113">The output is `50`.</span></span>

<span data-ttu-id="524f0-114">Le celle di riferimento sono istanze del tipo di record generico `Ref`, dichiarato come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="524f0-114">Reference cells are instances of the `Ref` generic record type, which is declared as follows.</span></span>

```fsharp
type Ref<'a> =
{ mutable contents: 'a }
```

<span data-ttu-id="524f0-115">Il tipo `'a ref` è sinonimo di `Ref<'a>`.</span><span class="sxs-lookup"><span data-stu-id="524f0-115">The type `'a ref` is a synonym for `Ref<'a>`.</span></span> <span data-ttu-id="524f0-116">Il primo viene visualizzato dal compilatore e da IntelliSense nell'interfaccia IDE per questo tipo, mentre il secondo rappresenta la definizione sottostante.</span><span class="sxs-lookup"><span data-stu-id="524f0-116">The compiler and IntelliSense in the IDE display the former for this type, but the underlying definition is the latter.</span></span>

<span data-ttu-id="524f0-117">L'operatore `ref` consente di creare una nuova cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="524f0-117">The `ref` operator creates a new reference cell.</span></span> <span data-ttu-id="524f0-118">Il codice seguente rappresenta la dichiarazione dell'operatore `ref`.</span><span class="sxs-lookup"><span data-stu-id="524f0-118">The following code is the declaration of the `ref` operator.</span></span>

```fsharp
let ref x = { contents = x }
```

<span data-ttu-id="524f0-119">Nella tabella seguente sono indicate le funzionalità disponibili nella cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="524f0-119">The following table shows the features that are available on the reference cell.</span></span>

|<span data-ttu-id="524f0-120">Operatore, membro o campo</span><span class="sxs-lookup"><span data-stu-id="524f0-120">Operator, member, or field</span></span>|<span data-ttu-id="524f0-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="524f0-121">Description</span></span>|<span data-ttu-id="524f0-122">Tipo</span><span class="sxs-lookup"><span data-stu-id="524f0-122">Type</span></span>|<span data-ttu-id="524f0-123">Definizione</span><span class="sxs-lookup"><span data-stu-id="524f0-123">Definition</span></span>|
|--------------------------|-----------|----|----------|
|<span data-ttu-id="524f0-124">`!` (operatore di dereferenziazione)</span><span class="sxs-lookup"><span data-stu-id="524f0-124">`!` (dereference operator)</span></span>|<span data-ttu-id="524f0-125">Restituisce il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="524f0-125">Returns the underlying value.</span></span>|`'a ref -> 'a`|`let (!) r = r.contents`|
|<span data-ttu-id="524f0-126">`:=` (operatore di assegnazione)</span><span class="sxs-lookup"><span data-stu-id="524f0-126">`:=` (assignment operator)</span></span>|<span data-ttu-id="524f0-127">Modifica il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="524f0-127">Changes the underlying value.</span></span>|`'a ref -> 'a -> unit`|`let (:=) r x = r.contents <- x`|
|<span data-ttu-id="524f0-128">`ref` (operatore)</span><span class="sxs-lookup"><span data-stu-id="524f0-128">`ref` (operator)</span></span>|<span data-ttu-id="524f0-129">Incapsula un valore in una nuova cella di riferimento.</span><span class="sxs-lookup"><span data-stu-id="524f0-129">Encapsulates a value into a new reference cell.</span></span>|`'a -> 'a ref`|`let ref x = { contents = x }`|
|<span data-ttu-id="524f0-130">`Value` (proprietà)</span><span class="sxs-lookup"><span data-stu-id="524f0-130">`Value` (property)</span></span>|<span data-ttu-id="524f0-131">Ottiene o imposta il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="524f0-131">Gets or sets the underlying value.</span></span>|`unit -> 'a`|`member x.Value = x.contents`|
|<span data-ttu-id="524f0-132">`contents` (campo del record)</span><span class="sxs-lookup"><span data-stu-id="524f0-132">`contents` (record field)</span></span>|<span data-ttu-id="524f0-133">Ottiene o imposta il valore sottostante.</span><span class="sxs-lookup"><span data-stu-id="524f0-133">Gets or sets the underlying value.</span></span>|`'a`|`let ref x = { contents = x }`|
<span data-ttu-id="524f0-134">È possibile accedere al valore sottostante in diversi modi.</span><span class="sxs-lookup"><span data-stu-id="524f0-134">There are several ways to access the underlying value.</span></span> <span data-ttu-id="524f0-135">Il valore restituito dall'operatore di dereferenziazione (`!`) non è un valore assegnabile.</span><span class="sxs-lookup"><span data-stu-id="524f0-135">The value returned by the dereference operator (`!`) is not an assignable value.</span></span> <span data-ttu-id="524f0-136">Se pertanto si modifica il valore sottostante, è necessario utilizzare l'operatore di assegnazione (`:=`).</span><span class="sxs-lookup"><span data-stu-id="524f0-136">Therefore, if you are modifying the underlying value, you must use the assignment operator (`:=`) instead.</span></span>

<span data-ttu-id="524f0-137">Sia la proprietà `Value` che il campo `contents` sono valori assegnabili</span><span class="sxs-lookup"><span data-stu-id="524f0-137">Both the `Value` property and the `contents` field are assignable values.</span></span> <span data-ttu-id="524f0-138">e possono pertanto essere utilizzati per accedere al valore sottostante o per modificare tale valore, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="524f0-138">Therefore, you can use these to either access or change the underlying value, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2203.fs)]

<span data-ttu-id="524f0-139">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="524f0-139">The output is as follows.</span></span>

```
10
10
11
12
```

<span data-ttu-id="524f0-140">Il campo `contents` viene fornito per garantire compatibilità con altre versioni di ML e comporta la generazione di un avviso durante la compilazione.</span><span class="sxs-lookup"><span data-stu-id="524f0-140">The field `contents` is provided for compatibility with other versions of ML and will produce a warning during compilation.</span></span> <span data-ttu-id="524f0-141">Per disabilitare l'avviso, utilizzare l'opzione del compilatore `--mlcompatibility`.</span><span class="sxs-lookup"><span data-stu-id="524f0-141">To disable the warning, use the `--mlcompatibility` compiler option.</span></span> <span data-ttu-id="524f0-142">Per altre informazioni, vedere [Opzioni del compilatore](compiler-options.md).</span><span class="sxs-lookup"><span data-stu-id="524f0-142">For more information, see [Compiler Options](compiler-options.md).</span></span>

<span data-ttu-id="524f0-143">I programmatori c# devono sapere che `ref` in c# non è la stessa operazione come `ref` in F #.</span><span class="sxs-lookup"><span data-stu-id="524f0-143">C# programmers should know that `ref` in C# is not the same thing as `ref` in F#.</span></span> <span data-ttu-id="524f0-144">I costrutti equivalenti in F # sono [zkratka](byrefs.md), che sono un concetto diverso dalle celle di riferimento.</span><span class="sxs-lookup"><span data-stu-id="524f0-144">The equivalent constructs in F# are [byrefs](byrefs.md), which are a different concept from reference cells.</span></span>

<span data-ttu-id="524f0-145">I valori contrassegnati come `mutable`può essere automaticamente promossa a `'a ref` acquisiti da una chiusura dei tag, vedere [valori](values/index.md).</span><span class="sxs-lookup"><span data-stu-id="524f0-145">Values marked as `mutable`may be automatically promoted to `'a ref` if captured by a closure; see [Values](values/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="524f0-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="524f0-146">See also</span></span>

- [<span data-ttu-id="524f0-147">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="524f0-147">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="524f0-148">Parametri e argomenti</span><span class="sxs-lookup"><span data-stu-id="524f0-148">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="524f0-149">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="524f0-149">Symbol and Operator Reference</span></span>](symbol-and-operator-reference/index.md)
- [<span data-ttu-id="524f0-150">Valori</span><span class="sxs-lookup"><span data-stu-id="524f0-150">Values</span></span>](values/index.md)
