---
title: Implementazione esplicita dell'interfaccia - Guida per programmatori C#
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628150"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="75b98-102">Implementazione esplicita dell'interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="75b98-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="75b98-103">Se [class](../../language-reference/keywords/class.md) implementa due interfacce che contengono un membro con la stessa firma e quest'ultimo viene implementato nella classe, entrambe le interfacce useranno il membro come propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="75b98-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="75b98-104">Nell'esempio seguente tutte le chiamate a `Paint` richiamano lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="75b98-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="75b98-105">Il primo esempio definisce i tipi:</span><span class="sxs-lookup"><span data-stu-id="75b98-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="75b98-106">Nell'esempio seguente vengono chiamati i metodi:</span><span class="sxs-lookup"><span data-stu-id="75b98-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="75b98-107">Quando due membri di interfaccia non eseguono la stessa funzione, comporta un'implementazione non corretta di una o entrambe le interfacce.</span><span class="sxs-lookup"><span data-stu-id="75b98-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="75b98-108">È possibile implementare un membro di interfaccia in modo esplicito, creando un membro della classe che viene chiamato solo tramite l'interfaccia ed è specifico di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="75b98-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="75b98-109">Denominare il membro della classe con il nome dell'interfaccia e un punto.</span><span class="sxs-lookup"><span data-stu-id="75b98-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="75b98-110">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="75b98-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="75b98-111">Il membro di classe `IControl.Paint` è disponibile solo tramite l'interfaccia`IControl` e `ISurface.Paint` è disponibile solo tramite `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="75b98-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="75b98-112">Entrambe le implementazioni dei metodi sono separate e nessuna delle due è disponibile direttamente nella classe.</span><span class="sxs-lookup"><span data-stu-id="75b98-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="75b98-113">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="75b98-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="75b98-114">L'implementazione esplicita viene usata anche per risolvere i casi in cui due interfacce dichiarano membri diversi con lo stesso nome, ad esempio una proprietà e un metodo.</span><span class="sxs-lookup"><span data-stu-id="75b98-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="75b98-115">Per implementare entrambe le interfacce, una classe deve usare l'implementazione esplicita per la proprietà `P`o il metodo `P`, o entrambi, per evitare un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="75b98-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="75b98-116">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="75b98-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="75b98-117">Se una classe eredita un'implementazione del metodo da un'interfaccia, il metodo è accessibile solo tramite un riferimento del tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="75b98-117">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="75b98-118">Il membro ereditato non viene visualizzato come parte dell'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="75b98-118">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="75b98-119">Nell'esempio seguente viene definita un'implementazione predefinita per un metodo di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="75b98-119">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="75b98-120">Nell'esempio seguente viene richiamata l'implementazione predefinita:</span><span class="sxs-lookup"><span data-stu-id="75b98-120">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="75b98-121">Qualsiasi classe che implementa l'interfaccia `IControl` può eseguire l'override del metodo `Paint` predefinito, sia come metodo pubblico, che come implementazione esplicita dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="75b98-121">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="75b98-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75b98-122">See also</span></span>

- [<span data-ttu-id="75b98-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="75b98-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="75b98-124">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="75b98-124">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="75b98-125">Interfacce</span><span class="sxs-lookup"><span data-stu-id="75b98-125">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="75b98-126">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="75b98-126">Inheritance</span></span>](../classes-and-structs/inheritance.md)
