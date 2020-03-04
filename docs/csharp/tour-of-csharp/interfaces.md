---
title: Interfacce C# - Panoramica del linguaggio C#
description: Le interfacce definiscono contratti implementati dai tipi in C#
ms.date: 02/27/2020
ms.assetid: a9bf82f4-efd1-4216-bd34-4ef0fa48c968
ms.openlocfilehash: 62d94462fa481379cf70d63a598deb7f36be204f
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159130"
---
# <a name="interfaces"></a><span data-ttu-id="f9786-103">Interfacce</span><span class="sxs-lookup"><span data-stu-id="f9786-103">Interfaces</span></span>

<span data-ttu-id="f9786-104">Un'***interfaccia*** definisce un contratto che può essere implementato da classi e struct.</span><span class="sxs-lookup"><span data-stu-id="f9786-104">An ***interface*** defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="f9786-105">Può contenere metodi, proprietà, eventi e indicizzatori.</span><span class="sxs-lookup"><span data-stu-id="f9786-105">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="f9786-106">Un'interfaccia non fornisce implementazioni dei membri che definisce: specifica semplicemente i membri che devono essere forniti da classi o struct che implementano l'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9786-106">An interface doesn't provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="f9786-107">Le interfacce possono usare l'***ereditarietà multipla***.</span><span class="sxs-lookup"><span data-stu-id="f9786-107">Interfaces may employ ***multiple inheritance***.</span></span> <span data-ttu-id="f9786-108">Nell'esempio seguente l'interfaccia `IComboBox` eredita da `ITextBox` e `IListBox`.</span><span class="sxs-lookup"><span data-stu-id="f9786-108">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

[!code-csharp[InterfacesOne](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L5-L17)]

<span data-ttu-id="f9786-109">Classi e struct possono implementare più interfacce.</span><span class="sxs-lookup"><span data-stu-id="f9786-109">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="f9786-110">Nell'esempio seguente la classe `EditBox` implementa `IControl` e `IDataBound`.</span><span class="sxs-lookup"><span data-stu-id="f9786-110">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

[!code-csharp[InterfacesTwo](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L19-L27)]

<span data-ttu-id="f9786-111">Quando una classe o un tipo struct implementa un'interfaccia specifica, le istanze di tale classe o struct possono essere convertite in modo implicito in quel tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9786-111">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="f9786-112">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9786-112">For example</span></span>

[!code-csharp[InterfacesThree](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L33-L35)]

<span data-ttu-id="f9786-113">Nei casi in cui un'istanza non è nota in modo statico per implementare un'interfaccia particolare, è possibile utilizzare i cast di tipo dinamico.</span><span class="sxs-lookup"><span data-stu-id="f9786-113">In cases where an instance isn't statically known to implement a particular interface, dynamic type casts can be used.</span></span> <span data-ttu-id="f9786-114">Le istruzioni seguenti usano ad esempio cast di tipo dinamico per ottenere implementazioni delle interfacce `IControl` e `IDataBound` di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="f9786-114">For example, the following statements use dynamic type casts to obtain an object’s `IControl` and `IDataBound` interface implementations.</span></span> <span data-ttu-id="f9786-115">Poiché il tipo effettivo in fase di esecuzione dell'oggetto è `EditBox`, i cast vengono eseguiti correttamente.</span><span class="sxs-lookup"><span data-stu-id="f9786-115">Because the run-time actual type of the object is `EditBox`, the casts succeed.</span></span>

[!code-csharp[InterfacesFour](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L40-L42)]

<span data-ttu-id="f9786-116">Nella classe `EditBox` precedente il metodo `Paint` dell'interfaccia `IControl` e il metodo `Bind` dell'interfaccia `IDataBound` vengono implementati usando membri pubblici.</span><span class="sxs-lookup"><span data-stu-id="f9786-116">In the previous `EditBox` class, the `Paint` method from the `IControl` interface and the `Bind` method from the `IDataBound` interface are implemented using public members.</span></span> <span data-ttu-id="f9786-117">C# supporta anche ***implementazioni di un membro dell'interfaccia*** esplicite, che consentono alla classe o al tipo struct di evitare di rendere pubblici i membri.</span><span class="sxs-lookup"><span data-stu-id="f9786-117">C# also supports explicit ***interface member implementations***, enabling the class or struct to avoid making the members public.</span></span> <span data-ttu-id="f9786-118">Un'implementazione esplicita di un membro dell'interfaccia viene scritta usando il nome completo del membro dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9786-118">An explicit interface member implementation is written using the fully qualified interface member name.</span></span> <span data-ttu-id="f9786-119">La classe `EditBox` può ad esempio implementare i metodi `IControl.Paint` e `IDataBound.Bind` usando implementazioni esplicite di un membro dell'interfaccia, come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="f9786-119">For example, the `EditBox` class could implement the `IControl.Paint` and `IDataBound.Bind` methods using explicit interface member implementations as follows.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L60-L64)]

<span data-ttu-id="f9786-120">È possibile accedere ai membri dell'interfaccia esplicita solo tramite il tipo di interfaccia.</span><span class="sxs-lookup"><span data-stu-id="f9786-120">Explicit interface members can only be accessed via the interface type.</span></span> <span data-ttu-id="f9786-121">Ad esempio, l'implementazione del metodo `IControl.Paint` fornito dalla classe EditBox precedente può essere richiamata solo dopo che è stato convertito il riferimento `EditBox` al tipo di interfaccia `IControl`.</span><span class="sxs-lookup"><span data-stu-id="f9786-121">For example, the implementation of `IControl.Paint` provided by the previous EditBox class can only be invoked by first converting the `EditBox` reference to the `IControl` interface type.</span></span>

[!code-csharp[InterfacesFive](../../../samples/snippets/csharp/tour/interfaces/Program.cs#L71-L74)]

>[!div class="step-by-step"]
><span data-ttu-id="f9786-122">[Precedente](arrays.md)
>[Successivo](delegates.md)</span><span class="sxs-lookup"><span data-stu-id="f9786-122">[Previous](arrays.md)
[Next](delegates.md)</span></span>
