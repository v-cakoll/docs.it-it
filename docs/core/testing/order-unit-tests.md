---
title: Ordinare unit test
description: Informazioni su come ordinare unit test con .NET Core.
author: IEvangelist
ms.author: dapine
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: eb426b790e0623b0cf233a763e93d2bd501b8034
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100821"
---
# <a name="order-unit-tests"></a><span data-ttu-id="655fa-103">Ordinare unit test</span><span class="sxs-lookup"><span data-stu-id="655fa-103">Order unit tests</span></span>

<span data-ttu-id="655fa-104">In alcuni casi può essere necessario eseguire unit test in un ordine specifico.</span><span class="sxs-lookup"><span data-stu-id="655fa-104">Occasionally, you may want to have unit tests run in a specific order.</span></span> <span data-ttu-id="655fa-105">Idealmente, l'ordine in cui vengono eseguiti gli unit test _non_ è rilevante ed è [consigliabile evitare di ordinare](unit-testing-best-practices.md) unit test.</span><span class="sxs-lookup"><span data-stu-id="655fa-105">Ideally, the order in which unit tests run should _not_ matter, and it is [best practice](unit-testing-best-practices.md) to avoid ordering unit tests.</span></span> <span data-ttu-id="655fa-106">A prescindere, potrebbe essere necessario eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="655fa-106">Regardless, there may be a need to do so.</span></span> <span data-ttu-id="655fa-107">In tal caso, in questo articolo viene illustrato come ordinare le esecuzioni di test.</span><span class="sxs-lookup"><span data-stu-id="655fa-107">In that case, this article demonstrates how to order test runs.</span></span>

<span data-ttu-id="655fa-108">Se si preferisce esplorare il codice sorgente, vedere il repository di esempio [per gli unit test di .NET Core](/samples/dotnet/samples/order-unit-tests-cs) .</span><span class="sxs-lookup"><span data-stu-id="655fa-108">If you prefer to browse the source code, see the [order .NET Core unit tests](/samples/dotnet/samples/order-unit-tests-cs) sample repository.</span></span>

> [!TIP]
> <span data-ttu-id="655fa-109">Oltre alle funzionalità di ordinamento descritte in questo articolo, è consigliabile [creare playlist personalizzate con Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) come alternativa.</span><span class="sxs-lookup"><span data-stu-id="655fa-109">In addition to the ordering capabilities outlined in this article, consider [creating custom playlists with Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) as an alternative.</span></span>

:::zone pivot="mstest"

## <a name="order-alphabetically"></a><span data-ttu-id="655fa-110">Ordina alfabeticamente</span><span class="sxs-lookup"><span data-stu-id="655fa-110">Order alphabetically</span></span>

<span data-ttu-id="655fa-111">Con MSTest, i test vengono ordinati automaticamente in base al nome del test.</span><span class="sxs-lookup"><span data-stu-id="655fa-111">With MSTest, tests are automatically ordered by their test name.</span></span>

> [!NOTE]
> <span data-ttu-id="655fa-112">Un test denominato `Test14` verrà eseguito prima `Test2` anche se il numero `2` è minore di `14` .</span><span class="sxs-lookup"><span data-stu-id="655fa-112">A test named `Test14` will run before `Test2` even though the number  `2` is less than `14`.</span></span> <span data-ttu-id="655fa-113">Questo è dovuto al fatto che l'ordinamento del nome del test usa il nome di testo del test.</span><span class="sxs-lookup"><span data-stu-id="655fa-113">This is because, test name ordering uses the text name of the test.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

<span data-ttu-id="655fa-114">Il Framework di test di xUnit consente una maggiore granularità e il controllo dell'ordine di esecuzione dei test.</span><span class="sxs-lookup"><span data-stu-id="655fa-114">The xUnit test framework allows for more granularity and control of test run order.</span></span> <span data-ttu-id="655fa-115">Implementare le `ITestCaseOrderer` interfacce e `ITestCollectionOrderer` per controllare l'ordine dei test case per una classe o per le raccolte di test.</span><span class="sxs-lookup"><span data-stu-id="655fa-115">You implement the `ITestCaseOrderer` and `ITestCollectionOrderer` interfaces to control the order of test cases for a class, or test collections.</span></span>

## <a name="order-by-test-case-alphabetically"></a><span data-ttu-id="655fa-116">Ordina per test case alfabeticamente</span><span class="sxs-lookup"><span data-stu-id="655fa-116">Order by test case alphabetically</span></span>

<span data-ttu-id="655fa-117">Per ordinare i test case in base al nome del metodo, implementare `ITestCaseOrderer` e fornire un meccanismo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="655fa-117">To order test cases by their method name, you implement the `ITestCaseOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

<span data-ttu-id="655fa-118">Quindi, in una classe di test, impostare l'ordine di test case con `TestCaseOrdererAttribute` .</span><span class="sxs-lookup"><span data-stu-id="655fa-118">Then in a test class you set the test case order with the `TestCaseOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a><span data-ttu-id="655fa-119">Ordina per raccolta alfabeticamente</span><span class="sxs-lookup"><span data-stu-id="655fa-119">Order by collection alphabetically</span></span>

<span data-ttu-id="655fa-120">Per ordinare le raccolte di test in base al nome visualizzato, è necessario implementare `ITestCollectionOrderer` e fornire un meccanismo di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="655fa-120">To order test collections by their display name, you implement the `ITestCollectionOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

<span data-ttu-id="655fa-121">Poiché le raccolte di test vengono potenzialmente eseguite in parallelo, è necessario disabilitare in modo esplicito la parallelizzazione dei test delle raccolte con `CollectionBehaviorAttribute` .</span><span class="sxs-lookup"><span data-stu-id="655fa-121">Since test collections potentially run in parallel, you must explicitly disable test parallelization of the collections with the `CollectionBehaviorAttribute`.</span></span> <span data-ttu-id="655fa-122">Specificare quindi l'implementazione di `TestCollectionOrdererAttribute` .</span><span class="sxs-lookup"><span data-stu-id="655fa-122">Then specify the implementation to the `TestCollectionOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a><span data-ttu-id="655fa-123">Ordina per attributo personalizzato</span><span class="sxs-lookup"><span data-stu-id="655fa-123">Order by custom attribute</span></span>

<span data-ttu-id="655fa-124">Per ordinare i test di xUnit con attributi personalizzati, è necessario prima di tutto un attributo da utilizzare.</span><span class="sxs-lookup"><span data-stu-id="655fa-124">To order xUnit tests with custom attributes, you first need an attribute to rely on.</span></span> <span data-ttu-id="655fa-125">Definire un `TestPriorityAttribute` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="655fa-125">Define a `TestPriorityAttribute` as follows:</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

<span data-ttu-id="655fa-126">Si consideri quindi la seguente `PriorityOrderer` implementazione dell' `ITestCaseOrderer` interfaccia.</span><span class="sxs-lookup"><span data-stu-id="655fa-126">Next, consider the following `PriorityOrderer` implementation of the `ITestCaseOrderer` interface.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

<span data-ttu-id="655fa-127">Quindi, in una classe di test, impostare il test case ordine con la classe `TestCaseOrdererAttribute` su `PriorityOrderer` .</span><span class="sxs-lookup"><span data-stu-id="655fa-127">Then in a test class you set the test case order with the `TestCaseOrdererAttribute` to the `PriorityOrderer`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a><span data-ttu-id="655fa-128">Ordina per priorità</span><span class="sxs-lookup"><span data-stu-id="655fa-128">Order by priority</span></span>

<span data-ttu-id="655fa-129">Per ordinare i test in modo esplicito, NUnit fornisce un [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute) .</span><span class="sxs-lookup"><span data-stu-id="655fa-129">To order tests explicitly, NUnit provides an [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute).</span></span> <span data-ttu-id="655fa-130">I test con questo attributo vengono avviati prima dei test senza.</span><span class="sxs-lookup"><span data-stu-id="655fa-130">Tests with this attribute are started before tests without.</span></span> <span data-ttu-id="655fa-131">Il valore Order viene usato per determinare l'ordine di esecuzione degli unit test.</span><span class="sxs-lookup"><span data-stu-id="655fa-131">The order value is used to determined the order to run the unit tests.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a><span data-ttu-id="655fa-132">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="655fa-132">Next Steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="655fa-133">Code coverage di unit test</span><span class="sxs-lookup"><span data-stu-id="655fa-133">Unit test code coverage</span></span>](unit-testing-code-coverage.md)
