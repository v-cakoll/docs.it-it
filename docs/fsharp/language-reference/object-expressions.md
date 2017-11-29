---
title: Espressioni di oggetto (F#)
description: 'Informazioni su come utilizzare le espressioni di oggetto di F # quando si desidera evitare il codice aggiuntivo e l''overhead necessario per creare un nuovo tipo denominato.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c6dcf4c9-e7fd-4eee-9e4e-1176f4c27f57
ms.openlocfilehash: 28660d430473de02a8a55e37a26609827b364012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="object-expressions"></a><span data-ttu-id="f9349-104">Espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="f9349-104">Object Expressions</span></span>

<span data-ttu-id="f9349-105">Un *oggetto espressione* è un'espressione che crea una nuova istanza di un tipo di oggetto anonimo creato dinamicamente che si basa su un tipo di base esistente, interfaccia o set di interfacce.</span><span class="sxs-lookup"><span data-stu-id="f9349-105">An *object expression* is an expression that creates a new instance of a dynamically created, anonymous object type that is based on an existing base type, interface, or set of interfaces.</span></span>


## <a name="syntax"></a><span data-ttu-id="f9349-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f9349-106">Syntax</span></span>

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a><span data-ttu-id="f9349-107">Note</span><span class="sxs-lookup"><span data-stu-id="f9349-107">Remarks</span></span>
<span data-ttu-id="f9349-108">Nella sintassi precedente, il *typename* rappresenta un tipo di classe esistente o un tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9349-108">In the previous syntax, the *typename* represents an existing class type or interface type.</span></span> <span data-ttu-id="f9349-109">*parametri di tipo* vengono descritti i parametri di tipo generico facoltativi.</span><span class="sxs-lookup"><span data-stu-id="f9349-109">*type-params* describes the optional generic type parameters.</span></span> <span data-ttu-id="f9349-110">Il *argomenti* vengono utilizzati solo per i tipi di classe, che richiedono che i parametri del costruttore.</span><span class="sxs-lookup"><span data-stu-id="f9349-110">The *arguments* are used only for class types, which require constructor parameters.</span></span> <span data-ttu-id="f9349-111">Il *definizioni di membro* sono override dei metodi della classe base o implementazioni di metodi astratti di un'interfaccia o una classe di base.</span><span class="sxs-lookup"><span data-stu-id="f9349-111">The *member-definitions* are overrides of base class methods, or implementations of abstract methods from either a base class or an interface.</span></span>

<span data-ttu-id="f9349-112">L'esempio seguente illustra i diversi tipi di espressioni di oggetto.</span><span class="sxs-lookup"><span data-stu-id="f9349-112">The following example illustrates several different types of object expressions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a><span data-ttu-id="f9349-113">Utilizzo di espressioni di oggetto</span><span class="sxs-lookup"><span data-stu-id="f9349-113">Using Object Expressions</span></span>
<span data-ttu-id="f9349-114">Usare le espressioni di oggetto quando si desidera evitare il codice aggiuntivo e l'overhead necessario per creare un nuovo tipo denominato.</span><span class="sxs-lookup"><span data-stu-id="f9349-114">You use object expressions when you want to avoid the extra code and overhead that is required to create a new, named type.</span></span> <span data-ttu-id="f9349-115">Se si utilizzano espressioni di oggetto per ridurre al minimo il numero di tipi creati in un programma, è possibile ridurre il numero di righe di codice e impedire la proliferazione dei tipi non necessaria.</span><span class="sxs-lookup"><span data-stu-id="f9349-115">If you use object expressions to minimize the number of types created in a program, you can reduce the number of lines of code and prevent the unnecessary proliferation of types.</span></span> <span data-ttu-id="f9349-116">Invece di creare molti tipi per gestire situazioni specifiche, è possibile utilizzare un'espressione di oggetto che consente di personalizzare un tipo esistente o fornisce un'implementazione di un'interfaccia per il case specifico.</span><span class="sxs-lookup"><span data-stu-id="f9349-116">Instead of creating many types just to handle specific situations, you can use an object expression that customizes an existing type or provides an appropriate implementation of an interface for the specific case at hand.</span></span>


## <a name="see-also"></a><span data-ttu-id="f9349-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9349-117">See Also</span></span>
[<span data-ttu-id="f9349-118">Riferimenti per il linguaggio F#</span><span class="sxs-lookup"><span data-stu-id="f9349-118">F# Language Reference</span></span>](index.md)
