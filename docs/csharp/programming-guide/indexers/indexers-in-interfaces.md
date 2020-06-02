---
title: Indicizzatori nelle interfacce - Guida per programmatori C#
ms.date: 02/08/2020
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
ms.openlocfilehash: 9ce6e4f0e0533c2880c6241f44409435248a336a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287480"
---
# <a name="indexers-in-interfaces-c-programming-guide"></a><span data-ttu-id="061de-102">Indicizzatori nelle interfacce (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="061de-102">Indexers in Interfaces (C# Programming Guide)</span></span>

<span data-ttu-id="061de-103">Gli indicizzatori possono essere dichiarati su una [interfaccia](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="061de-103">Indexers can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="061de-104">Le funzioni di accesso degli indicizzatori di interfaccia differiscono dalle funzioni di accesso degli indicizzatori di [classe](../../language-reference/keywords/class.md) per gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="061de-104">Accessors of interface indexers differ from the accessors of [class](../../language-reference/keywords/class.md) indexers in the following ways:</span></span>

- <span data-ttu-id="061de-105">Le funzioni di accesso di interfaccia non usano modificatori.</span><span class="sxs-lookup"><span data-stu-id="061de-105">Interface accessors do not use modifiers.</span></span>
- <span data-ttu-id="061de-106">Una funzione di accesso di interfaccia non dispone in genere di un corpo.</span><span class="sxs-lookup"><span data-stu-id="061de-106">An interface accessor typically does not have a body.</span></span>

<span data-ttu-id="061de-107">Lo scopo della funzione di accesso è indicare se l'indicizzatore è di lettura/scrittura, di sola lettura o di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="061de-107">The purpose of the accessor is to indicate whether the indexer is read-write, read-only, or write-only.</span></span> <span data-ttu-id="061de-108">È possibile fornire un'implementazione per un indicizzatore definito in un'interfaccia, ma si tratta di una situazione rara.</span><span class="sxs-lookup"><span data-stu-id="061de-108">You may provide an implementation for an indexer defined in an interface, but this is rare.</span></span> <span data-ttu-id="061de-109">Gli indicizzatori in genere definiscono un'API per accedere ai campi dati e i campi dati non possono essere definiti in un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="061de-109">Indexers typically define an API to access data fields, and data fields cannot be defined in an interface.</span></span>

<span data-ttu-id="061de-110">Nell'esempio seguente viene illustrata la funzione di accesso di un indicizzatore di interfaccia:</span><span class="sxs-lookup"><span data-stu-id="061de-110">The following is an example of an interface indexer accessor:</span></span>

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#DefineIndexer)]

<span data-ttu-id="061de-111">È necessario che la firma di un indicizzatore sia diversa dalle firme di tutti gli altri indicizzatori dichiarati nella stessa interfaccia.</span><span class="sxs-lookup"><span data-stu-id="061de-111">The signature of an indexer must differ from the signatures of all other indexers declared in the same interface.</span></span>

## <a name="example"></a><span data-ttu-id="061de-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="061de-112">Example</span></span>

<span data-ttu-id="061de-113">Nell'esempio seguente viene illustrato come implementare gli indicizzatori di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="061de-113">The following example shows how to implement interface indexers.</span></span>

[!code-csharp[Implement](~/samples/snippets/csharp/interfaces/indexers.cs#ImplementInterface)]

[!code-csharp[DefineInterface](~/samples/snippets/csharp/interfaces/indexers.cs#ExampleCode)]

<span data-ttu-id="061de-114">Nell'esempio precedente era possibile adottare l'implementazione esplicita del membro dell'interfaccia usando il nome completo del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="061de-114">In the preceding example, you could use the explicit interface member implementation by using the fully qualified name of the interface member.</span></span> <span data-ttu-id="061de-115">Ad esempio</span><span class="sxs-lookup"><span data-stu-id="061de-115">For example</span></span>

```csharp
string IIndexInterface.this[int index]
{
}
```

<span data-ttu-id="061de-116">Il nome completo, tuttavia, è necessario soltanto per evitare l'ambiguità quando la classe implementa più di un'interfaccia con la stessa firma di indicizzatore.</span><span class="sxs-lookup"><span data-stu-id="061de-116">However, the fully qualified name is only needed to avoid ambiguity when the class is implementing more than one interface with the same indexer signature.</span></span> <span data-ttu-id="061de-117">Se una classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce hanno la stessa firma di indicizzatore, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="061de-117">For example, if an `Employee` class is implementing two interfaces, `ICitizen` and `IEmployee`, and both interfaces have the same indexer signature, the explicit interface member implementation is necessary.</span></span> <span data-ttu-id="061de-118">In altre parole, la dichiarazione di indicizzatore seguente:</span><span class="sxs-lookup"><span data-stu-id="061de-118">That is, the following indexer declaration:</span></span>

```csharp
string IEmployee.this[int index]
{
}
```

<span data-ttu-id="061de-119">implementa l'indicizzatore nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="061de-119">implements the indexer on the `IEmployee` interface, while the following declaration:</span></span>

```csharp
string ICitizen.this[int index]
{
}
```

<span data-ttu-id="061de-120">implementa l'indicizzatore nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="061de-120">implements the indexer on the `ICitizen` interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="061de-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="061de-121">See also</span></span>

- [<span data-ttu-id="061de-122">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="061de-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="061de-123">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="061de-123">Indexers</span></span>](./index.md)
- [<span data-ttu-id="061de-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="061de-124">Properties</span></span>](../classes-and-structs/properties.md)
- [<span data-ttu-id="061de-125">Interfacce</span><span class="sxs-lookup"><span data-stu-id="061de-125">Interfaces</span></span>](../interfaces/index.md)
