---
title: Associazioni let nelle classi (F#)
description: Informazioni su come definire i campi privati e funzioni private per le classi di F# tramite associazioni 'let' nella definizione della classe.
ms.date: 05/16/2016
ms.openlocfilehash: 237eb98a57571a21c9187abf31f05160374cf4fc
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2018
ms.locfileid: "48033220"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="feb65-103">Associazioni let nelle classi</span><span class="sxs-lookup"><span data-stu-id="feb65-103">let Bindings in Classes</span></span>

<span data-ttu-id="feb65-104">È possibile definire i campi privati e funzioni private per le classi di F# tramite `let` associazioni nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="feb65-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="feb65-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="feb65-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="feb65-106">Note</span><span class="sxs-lookup"><span data-stu-id="feb65-106">Remarks</span></span>

<span data-ttu-id="feb65-107">La sintassi precedente viene visualizzata dopo le dichiarazioni di intestazione e l'ereditarietà di classe ma prima di qualsiasi definizione del membro.</span><span class="sxs-lookup"><span data-stu-id="feb65-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="feb65-108">La sintassi è simile a quella di `let` associazioni di fuori di classi, ma i nomi definiti in una classe hanno un ambito è limitato alla classe.</span><span class="sxs-lookup"><span data-stu-id="feb65-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="feb65-109">Oggetto `let` binding crea un campo privato o una funzione; per esporre i dati o le funzioni pubblicamente, dichiarare una proprietà o un metodo del membro.</span><span class="sxs-lookup"><span data-stu-id="feb65-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="feb65-110">Oggetto `let` che l'associazione non è statico viene chiamato un'istanza `let` associazione.</span><span class="sxs-lookup"><span data-stu-id="feb65-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="feb65-111">Istanza `let` associazioni eseguite quando vengono creati gli oggetti.</span><span class="sxs-lookup"><span data-stu-id="feb65-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="feb65-112">Statico `let` associazioni fanno parte dell'inizializzatore statico per la classe che viene sempre eseguito prima che il tipo viene usato prima di tutto.</span><span class="sxs-lookup"><span data-stu-id="feb65-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="feb65-113">Il codice all'interno di istanza `let` associazioni è possono usare i parametri del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="feb65-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="feb65-114">Gli attributi e i modificatori di accessibilità non sono consentiti sui `let` associazioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="feb65-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="feb65-115">Gli esempi di codice seguenti illustrano diversi tipi di `let` associazioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="feb65-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="feb65-116">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="feb65-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="feb65-117">Modalità alternative di creazione di campi</span><span class="sxs-lookup"><span data-stu-id="feb65-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="feb65-118">È anche possibile usare il `val` (parola chiave) per creare un campo privato.</span><span class="sxs-lookup"><span data-stu-id="feb65-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="feb65-119">Quando si usa il `val` (parola chiave), il campo non ha un valore quando l'oggetto viene creato, ma invece viene inizializzata con un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="feb65-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="feb65-120">Per altre informazioni, vedere [i campi espliciti: val (parola chiave)](explicit-fields-the-val-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="feb65-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="feb65-121">È anche possibile definire i campi privati in una classe usando una definizione di membro e aggiungendo la parola chiave `private` alla definizione.</span><span class="sxs-lookup"><span data-stu-id="feb65-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="feb65-122">Ciò può essere utile se si prevede di modificare l'accessibilità di un membro senza riscrivere il codice.</span><span class="sxs-lookup"><span data-stu-id="feb65-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="feb65-123">Per altre informazioni, vedere [Controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="feb65-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="feb65-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="feb65-124">See also</span></span>

- [<span data-ttu-id="feb65-125">Membri</span><span class="sxs-lookup"><span data-stu-id="feb65-125">Members</span></span>](index.md)
- [<span data-ttu-id="feb65-126">Associazioni `do` nelle classi</span><span class="sxs-lookup"><span data-stu-id="feb65-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="feb65-127">`let` associazioni</span><span class="sxs-lookup"><span data-stu-id="feb65-127">`let` Bindings</span></span>](../functions/let-bindings.md)
