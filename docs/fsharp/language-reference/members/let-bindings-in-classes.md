---
title: Associazioni let nelle classi (F#)
description: 'Informazioni su come definire i campi privati e funzioni private per le classi F # con binding ''let'' nella definizione della classe.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9d3710f5-68b1-4e4c-b02b-27fe018f20e8
ms.openlocfilehash: 1337cc0794e366e8c39745f5c45065362c9c38c9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="ca75f-104">Associazioni let nelle classi</span><span class="sxs-lookup"><span data-stu-id="ca75f-104">let Bindings in Classes</span></span>

<span data-ttu-id="ca75f-105">È possibile definire campi privati e funzioni private per le classi F # utilizzando `let` associazioni nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="ca75f-105">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>


## <a name="syntax"></a><span data-ttu-id="ca75f-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca75f-106">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="ca75f-107">Note</span><span class="sxs-lookup"><span data-stu-id="ca75f-107">Remarks</span></span>
<span data-ttu-id="ca75f-108">La sintassi precedente viene visualizzato dopo le dichiarazioni di intestazione e l'ereditarietà di classe ma prima di qualsiasi definizione del membro.</span><span class="sxs-lookup"><span data-stu-id="ca75f-108">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="ca75f-109">La sintassi è simile a quella di `let` associazioni di fuori di classi, ma i nomi definiti in una classe hanno un ambito è limitato alla classe.</span><span class="sxs-lookup"><span data-stu-id="ca75f-109">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="ca75f-110">Oggetto `let` associazione crea una funzione; per esporre i dati o un campo privato o le funzioni pubblicamente, dichiarare una proprietà o un metodo di membro.</span><span class="sxs-lookup"><span data-stu-id="ca75f-110">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="ca75f-111">Oggetto `let` che l'associazione non è statico viene chiamato un'istanza `let` associazione.</span><span class="sxs-lookup"><span data-stu-id="ca75f-111">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="ca75f-112">Istanza `let` associazioni eseguire quando vengono creati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="ca75f-112">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="ca75f-113">Statico `let` associazioni fanno parte dell'inizializzatore statico per la classe, che viene sempre eseguito prima che il tipo viene utilizzato prima.</span><span class="sxs-lookup"><span data-stu-id="ca75f-113">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="ca75f-114">Il codice all'interno di istanza `let` associazioni possono utilizzare i parametri del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="ca75f-114">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="ca75f-115">Gli attributi e modificatori di accessibilità non consentiti in `let` associazioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="ca75f-115">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="ca75f-116">Gli esempi di codice seguenti illustrano diversi tipi di `let` associazioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="ca75f-116">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="ca75f-117">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="ca75f-117">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="ca75f-118">Modalità alternative di creazione di campi</span><span class="sxs-lookup"><span data-stu-id="ca75f-118">Alternative Ways to Create Fields</span></span>
<span data-ttu-id="ca75f-119">È inoltre possibile utilizzare il `val` (parola chiave) per creare un campo privato.</span><span class="sxs-lookup"><span data-stu-id="ca75f-119">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="ca75f-120">Quando si utilizza il `val` (parola chiave), il campo non ha un valore quando l'oggetto viene creato, ma invece viene inizializzata con un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="ca75f-120">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="ca75f-121">Per ulteriori informazioni, vedere [campi espliciti: val (parola chiave)](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="ca75f-121">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="ca75f-122">È inoltre possibile definire campi privati in una classe usando una definizione di membro e aggiungendo la parola chiave `private` alla definizione.</span><span class="sxs-lookup"><span data-stu-id="ca75f-122">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="ca75f-123">Questo può essere utile se si prevede di modificare l'accessibilità di un membro senza riscrivere il codice.</span><span class="sxs-lookup"><span data-stu-id="ca75f-123">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="ca75f-124">Per altre informazioni, vedere [Controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="ca75f-124">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ca75f-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca75f-125">See Also</span></span>
[<span data-ttu-id="ca75f-126">Membri</span><span class="sxs-lookup"><span data-stu-id="ca75f-126">Members</span></span>](index.md)

[<span data-ttu-id="ca75f-127">Associazioni `do` nelle classi</span><span class="sxs-lookup"><span data-stu-id="ca75f-127">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)

[<span data-ttu-id="ca75f-128">`let`Associazioni</span><span class="sxs-lookup"><span data-stu-id="ca75f-128">`let` Bindings</span></span>](../functions/let-bindings.md)
