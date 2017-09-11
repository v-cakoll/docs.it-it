---
title: Interfacce C# - Panoramica del linguaggio C#
description: Le interfacce definiscono contratti implementati dai tipi in C#
keywords: ".NET, csharp, interfacce, ereditarietà multipla, polimorfismo"
author: BillWagner
ms.author: wiwagn
ms.date: 08/10/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 673ac56f3f5732fcda02d313b6f4273708ae365f
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="interfaces"></a><span data-ttu-id="65551-104">Interfacce</span><span class="sxs-lookup"><span data-stu-id="65551-104">Interfaces</span></span>

<span data-ttu-id="65551-105">Un'***interfaccia*** definisce un contratto che può essere implementato da classi e struct.</span><span class="sxs-lookup"><span data-stu-id="65551-105">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="65551-106">Può contenere metodi, proprietà, eventi e indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="65551-106">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="65551-107">Un'interfaccia non fornisce le implementazioni dei membri che definisce, ma specifica semplicemente i membri che devono essere forniti dalle classi o dai tipi struct che la implementano.</span><span class="sxs-lookup"><span data-stu-id="65551-107">An interface does not provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="65551-108">Le interfacce possono usare l'***ereditarietà multipla***.</span><span class="sxs-lookup"><span data-stu-id="65551-108">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="65551-109">Nell'esempio seguente l'interfaccia `IComboBox` eredita da `ITextBox` e `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="65551-109">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

<span data-ttu-id="65551-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span><span class="sxs-lookup"><span data-stu-id="65551-110">[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]</span></span>

<span data-ttu-id="65551-111">Classi e struct possono implementare più interfacce.</span><span class="sxs-lookup"><span data-stu-id="65551-111">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="65551-112">Nell'esempio seguente la classe `EditBox` implementa `IControl` e `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="65551-112">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

<span data-ttu-id="65551-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span><span class="sxs-lookup"><span data-stu-id="65551-113">[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]</span></span>

<span data-ttu-id="65551-114">Quando una classe o un tipo struct implementa un'interfaccia specifica, le istanze di tale classe o struct possono essere convertite in modo implicito in quel tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65551-114">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="65551-115">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65551-115">For example</span></span>

<span data-ttu-id="65551-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span><span class="sxs-lookup"><span data-stu-id="65551-116">[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]</span></span>

<span data-ttu-id="65551-117">Nei casi in cui un'istanza non implementa staticamente un'interfaccia specifica è possibile usare cast di tipo dinamico.</span><span class="sxs-lookup"><span data-stu-id="65551-117">In cases where an instance is not statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="65551-118">Le istruzioni seguenti usano ad esempio cast di tipo dinamico per ottenere implementazioni delle interfacce `IControl` e `IDataBound` di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="65551-118">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="65551-119">Poiché il tipo effettivo in fase di esecuzione dell'oggetto è `EditBox`, i cast vengono eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="65551-119">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

<span data-ttu-id="65551-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span><span class="sxs-lookup"><span data-stu-id="65551-120">[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]</span></span>

<span data-ttu-id="65551-121">Nella classe `EditBox` precedente il metodo `Paint` dell'interfaccia `IControl` e il metodo `Bind` dell'interfaccia `IDataBound` vengono implementati usando membri pubblici.</span><span class="sxs-lookup"><span data-stu-id="65551-121">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="65551-122">C# supporta anche ***implementazioni di un membro dell'interfaccia*** esplicite, che consentono alla classe o al tipo struct di evitare di rendere pubblici i membri.</span><span class="sxs-lookup"><span data-stu-id="65551-122">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="65551-123">Un'implementazione esplicita di un membro dell'interfaccia viene scritta usando il nome completo del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65551-123">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="65551-124">La classe `EditBox` può ad esempio implementare i metodi `IControl.Paint` e `IDataBound.Bind` usando implementazioni esplicite di un membro dell'interfaccia, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="65551-124">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

<span data-ttu-id="65551-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span><span class="sxs-lookup"><span data-stu-id="65551-125">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]</span></span>

<span data-ttu-id="65551-126">È possibile accedere ai membri dell'interfaccia esplicita solo tramite il tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="65551-126">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="65551-127">Ad esempio, l'implementazione del metodo `IControl.Paint` fornito dalla classe EditBox precedente può essere richiamata solo dopo che è stato convertito il riferimento `EditBox` al tipo di interfaccia `IControl`.</span><span class="sxs-lookup"><span data-stu-id="65551-127">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

<span data-ttu-id="65551-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span><span class="sxs-lookup"><span data-stu-id="65551-128">[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="65551-129">[Precedente](arrays.md)
[Successivo](enums.md)</span><span class="sxs-lookup"><span data-stu-id="65551-129">[Previous](arrays.md)
[Next](enums.md)</span></span>

