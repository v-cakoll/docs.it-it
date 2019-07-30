---
title: Associazioni let nelle classi
description: Informazioni su come definire campi privati e funzioni private per F# le classi usando associazioni ' Let ' nella definizione della classe.
ms.date: 05/16/2016
ms.openlocfilehash: 0086d3a91f85395c2bd0555f978c5d951c363357
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627479"
---
# <a name="let-bindings-in-classes"></a><span data-ttu-id="dcb59-103">Associazioni let nelle classi</span><span class="sxs-lookup"><span data-stu-id="dcb59-103">let Bindings in Classes</span></span>

<span data-ttu-id="dcb59-104">È possibile definire campi privati e funzioni private per F# le classi `let` utilizzando binding nella definizione della classe.</span><span class="sxs-lookup"><span data-stu-id="dcb59-104">You can define private fields and private functions for F# classes by using `let` bindings in the class definition.</span></span>

## <a name="syntax"></a><span data-ttu-id="dcb59-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcb59-105">Syntax</span></span>

```fsharp
// Field.
[static] let [ mutable ] binding1 [ and ... binding-n ]

// Function.
[static] let [ rec ] binding1 [ and ... binding-n ]
```

## <a name="remarks"></a><span data-ttu-id="dcb59-106">Note</span><span class="sxs-lookup"><span data-stu-id="dcb59-106">Remarks</span></span>

<span data-ttu-id="dcb59-107">La sintassi precedente viene visualizzata dopo l'intestazione della classe e le dichiarazioni di ereditarietà, ma prima delle definizioni dei membri.</span><span class="sxs-lookup"><span data-stu-id="dcb59-107">The previous syntax appears after the class heading and inheritance declarations but before any member definitions.</span></span> <span data-ttu-id="dcb59-108">La sintassi è simile a quella `let` delle associazioni esterne alle classi, ma i nomi definiti in una classe hanno un ambito limitato alla classe.</span><span class="sxs-lookup"><span data-stu-id="dcb59-108">The syntax is like that of `let` bindings outside of classes, but the names defined in a class have a scope that is limited to the class.</span></span> <span data-ttu-id="dcb59-109">Un' `let` associazione crea una funzione o un campo privato; per esporre pubblicamente i dati o le funzioni, dichiarare una proprietà o un metodo del membro.</span><span class="sxs-lookup"><span data-stu-id="dcb59-109">A `let` binding creates a private field or function; to expose data or functions publicly, declare a property or a member method.</span></span>

<span data-ttu-id="dcb59-110">Un' `let` associazione non statica viene chiamata Associazione di istanza `let` .</span><span class="sxs-lookup"><span data-stu-id="dcb59-110">A `let` binding that is not static is called an instance `let` binding.</span></span> <span data-ttu-id="dcb59-111">Le `let` associazioni di istanza vengono eseguite quando vengono creati oggetti.</span><span class="sxs-lookup"><span data-stu-id="dcb59-111">Instance `let` bindings execute when objects are created.</span></span> <span data-ttu-id="dcb59-112">Le `let` associazioni statiche fanno parte dell'inizializzatore statico per la classe, che è garantita l'esecuzione prima che il tipo venga usato per la prima volta.</span><span class="sxs-lookup"><span data-stu-id="dcb59-112">Static `let` bindings are part of the static initializer for the class, which is guaranteed to execute before the type is first used.</span></span>

<span data-ttu-id="dcb59-113">Il codice all'interno `let` delle associazioni di istanza può usare i parametri del costruttore primario.</span><span class="sxs-lookup"><span data-stu-id="dcb59-113">The code within instance `let` bindings can use the primary constructor's parameters.</span></span>

<span data-ttu-id="dcb59-114">Attributi e modificatori di accessibilità non sono `let` consentiti nelle associazioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="dcb59-114">Attributes and accessibility modifiers are not permitted on `let` bindings in classes.</span></span>

<span data-ttu-id="dcb59-115">Negli esempi di codice seguenti vengono illustrati diversi `let` tipi di associazioni nelle classi.</span><span class="sxs-lookup"><span data-stu-id="dcb59-115">The following code examples illustrate several types of `let` bindings in classes.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet3001.fs)]

<span data-ttu-id="dcb59-116">L'output è indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="dcb59-116">The output is as follows.</span></span>

```
10 52 1 204
```

## <a name="alternative-ways-to-create-fields"></a><span data-ttu-id="dcb59-117">Metodi alternativi per la creazione di campi</span><span class="sxs-lookup"><span data-stu-id="dcb59-117">Alternative Ways to Create Fields</span></span>

<span data-ttu-id="dcb59-118">È anche possibile usare la `val` parola chiave per creare un campo privato.</span><span class="sxs-lookup"><span data-stu-id="dcb59-118">You can also use the `val` keyword to create a private field.</span></span> <span data-ttu-id="dcb59-119">Quando si usa `val` la parola chiave, al campo non viene assegnato un valore quando viene creato l'oggetto, ma viene invece inizializzato con un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="dcb59-119">When using the `val` keyword, the field is not given a value when the object is created, but instead is initialized with a default value.</span></span> <span data-ttu-id="dcb59-120">Per ulteriori informazioni, vedere [campi espliciti: Parola chiave](explicit-fields-the-val-keyword.md)Val.</span><span class="sxs-lookup"><span data-stu-id="dcb59-120">For more information, see [Explicit Fields: The val Keyword](explicit-fields-the-val-keyword.md).</span></span>

<span data-ttu-id="dcb59-121">È anche possibile definire campi privati in una classe usando una definizione del membro e aggiungendo la parola `private` chiave alla definizione.</span><span class="sxs-lookup"><span data-stu-id="dcb59-121">You can also define private fields in a class by using a member definition and adding the keyword `private` to the definition.</span></span> <span data-ttu-id="dcb59-122">Questa operazione può essere utile se si prevede di modificare l'accessibilità di un membro senza riscrivere il codice.</span><span class="sxs-lookup"><span data-stu-id="dcb59-122">This can be useful if you expect to change the accessibility of a member without rewriting your code.</span></span> <span data-ttu-id="dcb59-123">Per altre informazioni, vedere [Controllo di accesso](../access-control.md).</span><span class="sxs-lookup"><span data-stu-id="dcb59-123">For more information, see [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dcb59-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dcb59-124">See also</span></span>

- [<span data-ttu-id="dcb59-125">Membri</span><span class="sxs-lookup"><span data-stu-id="dcb59-125">Members</span></span>](index.md)
- [<span data-ttu-id="dcb59-126">Associazioni `do` nelle classi</span><span class="sxs-lookup"><span data-stu-id="dcb59-126">`do` Bindings in Classes</span></span>](do-bindings-in-classes.md)
- [<span data-ttu-id="dcb59-127">`let`Associazioni</span><span class="sxs-lookup"><span data-stu-id="dcb59-127">`let` Bindings</span></span>](../functions/let-bindings.md)
