---
title: Proprietà dell'interfaccia - Guida per programmatori C#
ms.date: 01/31/2020
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: 5798b80526f34e923e2eaab43847b98f6c64e14b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77626620"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="99cd9-102">Proprietà dell'interfaccia (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="99cd9-102">Interface Properties (C# Programming Guide)</span></span>

<span data-ttu-id="99cd9-103">Le proprietà possono essere dichiarate su una [interfaccia](../../language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="99cd9-103">Properties can be declared on an [interface](../../language-reference/keywords/interface.md).</span></span> <span data-ttu-id="99cd9-104">Nell'esempio seguente viene dichiarata una funzione di accesso alle proprietà dell'interfaccia:The following example declares an interface property accessor:</span><span class="sxs-lookup"><span data-stu-id="99cd9-104">The following example declares an interface property accessor:</span></span>

[!code-csharp[DeclareProperties](~/samples/snippets/csharp/interfaces/properties.cs#DeclareInterfaceProperties)]

<span data-ttu-id="99cd9-105">Le proprietà dell'interfaccia in genere non dispongono di un corpo.</span><span class="sxs-lookup"><span data-stu-id="99cd9-105">Interface properties typically don't have a body.</span></span> <span data-ttu-id="99cd9-106">Le funzioni di accesso indicano se la proprietà è di lettura/scrittura, di sola lettura o di sola scrittura.</span><span class="sxs-lookup"><span data-stu-id="99cd9-106">The accessors indicate whether the property is read-write, read-only, or write-only.</span></span> <span data-ttu-id="99cd9-107">A differenza delle classi e degli struct, la dichiarazione delle funzioni di accesso senza un corpo non dichiara una [proprietà implementata automaticamente.](auto-implemented-properties.md)</span><span class="sxs-lookup"><span data-stu-id="99cd9-107">Unlike in classes and structs, declaring the accessors without a body doesn't declare an [auto-implemented property](auto-implemented-properties.md).</span></span> <span data-ttu-id="99cd9-108">A partire dalla versione 8.0 di C, un'interfaccia può definire un'implementazione predefinita per i membri, incluse le proprietà.</span><span class="sxs-lookup"><span data-stu-id="99cd9-108">Beginning with C# 8.0, an interface may define a default implementation for members, including properties.</span></span> <span data-ttu-id="99cd9-109">La definizione di un'implementazione predefinita per una proprietà in un'interfaccia è rara perché le interfacce non possono definire campi dati di istanza.</span><span class="sxs-lookup"><span data-stu-id="99cd9-109">Defining a default implementation for a property in an interface is rare because interfaces may not define instance data fields.</span></span>

## <a name="example"></a><span data-ttu-id="99cd9-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="99cd9-110">Example</span></span>

<span data-ttu-id="99cd9-111">Nell'esempio seguente l'interfaccia `IEmployee` include una proprietà in lettura-scrittura, `Name`, e una proprietà in sola lettura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="99cd9-111">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="99cd9-112">La classe `Employee` implementa l'interfaccia `IEmployee` e usa le due proprietà.</span><span class="sxs-lookup"><span data-stu-id="99cd9-112">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="99cd9-113">Il programma legge il nome di un nuovo dipendente e il numero corrente di dipendenti e quindi visualizza il nome del dipendente e il relativo numero calcolato.</span><span class="sxs-lookup"><span data-stu-id="99cd9-113">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>

<span data-ttu-id="99cd9-114">È possibile usare il nome completo della proprietà, che fa riferimento all'interfaccia in cui il membro è dichiarato.</span><span class="sxs-lookup"><span data-stu-id="99cd9-114">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="99cd9-115">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="99cd9-115">For example:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="99cd9-116">Nell'esempio precedente viene illustrata [l'implementazione esplicita dell'interfaccia](../interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="99cd9-116">The preceding example demonstrates [Explicit Interface Implementation](../interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="99cd9-117">Se la classe `Employee` implementa, ad esempio, due interfacce, `ICitizen` e `IEmployee`, ed entrambe le interfacce includono la proprietà `Name`, sarà necessaria l'implementazione esplicita del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="99cd9-117">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="99cd9-118">In altre parole, la dichiarazione di proprietà seguente:</span><span class="sxs-lookup"><span data-stu-id="99cd9-118">That is, the following property declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#ExplicitImplementation)]

<span data-ttu-id="99cd9-119">implementa la proprietà `Name` nell'interfaccia `IEmployee`, mentre la dichiarazione seguente:</span><span class="sxs-lookup"><span data-stu-id="99cd9-119">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>

[!code-csharp[ExplicitProperties](~/samples/snippets/csharp/interfaces/properties.cs#CitizenImplementation)]

<span data-ttu-id="99cd9-120">implementa la proprietà `Name` nell'interfaccia `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="99cd9-120">implements the `Name` property on the `ICitizen` interface.</span></span>

[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#PropertyExample)]
[!code-csharp[Example](~/samples/snippets/csharp/interfaces/properties.cs#UseProperty)]

**`210 Hazem Abolrous`**

## <a name="sample-output"></a><span data-ttu-id="99cd9-121">Output di esempio</span><span class="sxs-lookup"><span data-stu-id="99cd9-121">Sample output</span></span>

```console
Enter number of employees: 210
Enter the name of the new employee: Hazem Abolrous
The employee information:
Employee number: 211
Employee name: Hazem Abolrous
```

## <a name="see-also"></a><span data-ttu-id="99cd9-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99cd9-122">See also</span></span>

- [<span data-ttu-id="99cd9-123">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="99cd9-123">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="99cd9-124">Proprietà</span><span class="sxs-lookup"><span data-stu-id="99cd9-124">Properties</span></span>](./properties.md)
- [<span data-ttu-id="99cd9-125">Utilizzo delle proprietà</span><span class="sxs-lookup"><span data-stu-id="99cd9-125">Using Properties</span></span>](./using-properties.md)
- [<span data-ttu-id="99cd9-126">Confronto tra proprietà e indicizzatori</span><span class="sxs-lookup"><span data-stu-id="99cd9-126">Comparison Between Properties and Indexers</span></span>](../indexers/comparison-between-properties-and-indexers.md)
- [<span data-ttu-id="99cd9-127">Indicizzatori</span><span class="sxs-lookup"><span data-stu-id="99cd9-127">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="99cd9-128">Interfacce</span><span class="sxs-lookup"><span data-stu-id="99cd9-128">Interfaces</span></span>](../interfaces/index.md)
