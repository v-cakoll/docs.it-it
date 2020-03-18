---
title: Implementazione esplicita dell'interfaccia - Guida per programmatori C#
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167673"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a><span data-ttu-id="2299a-102">Implementazione esplicita dell'interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="2299a-102">Explicit Interface Implementation (C# Programming Guide)</span></span>

<span data-ttu-id="2299a-103">Se [class](../../language-reference/keywords/class.md) implementa due interfacce che contengono un membro con la stessa firma e quest'ultimo viene implementato nella classe, entrambe le interfacce useranno il membro come propria implementazione.</span><span class="sxs-lookup"><span data-stu-id="2299a-103">If a [class](../../language-reference/keywords/class.md) implements two interfaces that contain a member with the same signature, then implementing that member on the class will cause both interfaces to use that member as their implementation.</span></span> <span data-ttu-id="2299a-104">Nell'esempio seguente tutte le chiamate a `Paint` richiamano lo stesso metodo.</span><span class="sxs-lookup"><span data-stu-id="2299a-104">In the following example, all the calls to `Paint` invoke the same method.</span></span> <span data-ttu-id="2299a-105">Questo primo esempio definisce i tipi:This first sample defines the types:</span><span class="sxs-lookup"><span data-stu-id="2299a-105">This first sample defines the types:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

<span data-ttu-id="2299a-106">Nell'esempio seguente vengono chiamii i metodi:</span><span class="sxs-lookup"><span data-stu-id="2299a-106">The following sample calls the methods:</span></span>

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

<span data-ttu-id="2299a-107">Quando due membri di interfaccia non eseguono la stessa funzione, porta a un'implementazione non corretta di una o entrambe le interfacce.</span><span class="sxs-lookup"><span data-stu-id="2299a-107">When two interface members don't perform the same function, it leads to an incorrect implementation of one or both of the interfaces.</span></span> <span data-ttu-id="2299a-108">È possibile implementare un membro di interfaccia in modo esplicito, creando un membro di classe che viene chiamato solo tramite l'interfaccia ed è specifico di tale interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2299a-108">It's possible to implement an interface member explicitly—creating a class member that is only called through the interface, and is specific to that interface.</span></span> <span data-ttu-id="2299a-109">Assegnare al membro della classe il nome dell'interfaccia e un punto.</span><span class="sxs-lookup"><span data-stu-id="2299a-109">Name the class member with the name of the interface and a period.</span></span> <span data-ttu-id="2299a-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2299a-110">For example:</span></span>

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

<span data-ttu-id="2299a-111">Il membro di classe `IControl.Paint` è disponibile solo tramite l'interfaccia`IControl` e `ISurface.Paint` è disponibile solo tramite `ISurface`.</span><span class="sxs-lookup"><span data-stu-id="2299a-111">The class member `IControl.Paint` is only available through the `IControl` interface, and `ISurface.Paint` is only available through `ISurface`.</span></span> <span data-ttu-id="2299a-112">Entrambe le implementazioni del metodo sono separate e nessuna delle due è disponibile direttamente nella classe.</span><span class="sxs-lookup"><span data-stu-id="2299a-112">Both method implementations are separate, and neither are available directly on the class.</span></span> <span data-ttu-id="2299a-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2299a-113">For example:</span></span>

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

<span data-ttu-id="2299a-114">L'implementazione esplicita viene utilizzata anche per risolvere i casi in cui due interfacce dichiarano membri diversi con lo stesso nome, ad esempio una proprietà e un metodo.</span><span class="sxs-lookup"><span data-stu-id="2299a-114">Explicit implementation is also used to resolve cases where two interfaces each declare different members of the same name such as a property and a method.</span></span> <span data-ttu-id="2299a-115">Per implementare entrambe le interfacce, una classe `P`deve utilizzare `P`un'implementazione esplicita per la proprietà , oppure per il metodo , o entrambe, per evitare un errore del compilatore.</span><span class="sxs-lookup"><span data-stu-id="2299a-115">To implement both interfaces, a class has to use explicit implementation either for the property `P`, or the method `P`, or both, to avoid a compiler error.</span></span> <span data-ttu-id="2299a-116">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2299a-116">For example:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

<span data-ttu-id="2299a-117">A partire dalla [versione 8.0](../../whats-new/csharp-8.md#default-interface-methods)di C, è possibile definire un'implementazione per i membri dichiarati in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2299a-117">Beginning with [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods), you can define an implementation for members declared in an interface.</span></span> <span data-ttu-id="2299a-118">Se una classe eredita un'implementazione del metodo da un'interfaccia, tale metodo è accessibile solo tramite un riferimento del tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2299a-118">If a class inherits a method implementation from an interface, that method is only accessible through a reference of the interface type.</span></span> <span data-ttu-id="2299a-119">Il membro ereditato non viene visualizzato come parte dell'interfaccia pubblica.</span><span class="sxs-lookup"><span data-stu-id="2299a-119">The inherited member doesn't appear as part of the public interface.</span></span> <span data-ttu-id="2299a-120">L'esempio seguente definisce un'implementazione predefinita per un metodo di interfaccia:The following sample defines a default implementation for an interface method:</span><span class="sxs-lookup"><span data-stu-id="2299a-120">The following sample defines a default implementation for an interface method:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

<span data-ttu-id="2299a-121">L'esempio seguente richiama l'implementazione predefinita:The following sample invokes the default implementation:</span><span class="sxs-lookup"><span data-stu-id="2299a-121">The following sample invokes the default implementation:</span></span>

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

<span data-ttu-id="2299a-122">Qualsiasi classe che `IControl` implementa l'interfaccia può eseguire l'override del metodo predefinito, `Paint` come metodo pubblico o come implementazione esplicita dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="2299a-122">Any class that implements the `IControl` interface can override the default `Paint` method, either as a public method, or as an explicit interface implementation.</span></span>

## <a name="see-also"></a><span data-ttu-id="2299a-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2299a-123">See also</span></span>

- [<span data-ttu-id="2299a-124">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="2299a-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2299a-125">Classi e struct</span><span class="sxs-lookup"><span data-stu-id="2299a-125">Classes and Structs</span></span>](../classes-and-structs/index.md)
- [<span data-ttu-id="2299a-126">Interfacce</span><span class="sxs-lookup"><span data-stu-id="2299a-126">Interfaces</span></span>](./index.md)
- [<span data-ttu-id="2299a-127">Ereditarietà</span><span class="sxs-lookup"><span data-stu-id="2299a-127">Inheritance</span></span>](../classes-and-structs/inheritance.md)
