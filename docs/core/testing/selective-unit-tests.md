---
title: Esecuzione di unit test selettivi
description: Illustra come utilizzare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test.
keywords: .NET, .NET Core, unit test, test selettivo
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="6a973-104">Esecuzione di unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="6a973-104">Running selective unit tests</span></span>

<span data-ttu-id="6a973-105">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="6a973-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="6a973-106">Se si utilizza `vstest.console.exe`, sostituire `--filter ` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="6a973-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="6a973-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="6a973-107">MSTest</span></span>

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="6a973-108">Espressione</span><span class="sxs-lookup"><span data-stu-id="6a973-108">Expression</span></span> | <span data-ttu-id="6a973-109">Risultato</span><span class="sxs-lookup"><span data-stu-id="6a973-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="6a973-110">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="6a973-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="6a973-111">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="6a973-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="6a973-112">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="6a973-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="6a973-113">Esegue i test inclusi nella classe `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="6a973-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="6a973-114">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTestClass1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="6a973-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="6a973-115">Esegue tutti i test tranne `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="6a973-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="6a973-116">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="6a973-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="6a973-117">Esegue i test annotati con `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="6a973-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="6a973-118">**Nota:** `Priority~3` è un valore non valido, in quanto non è una stringa.</span><span class="sxs-lookup"><span data-stu-id="6a973-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="6a973-119">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="6a973-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="6a973-120">Espressione</span><span class="sxs-lookup"><span data-stu-id="6a973-120">Expression</span></span> | <span data-ttu-id="6a973-121">Risultato</span><span class="sxs-lookup"><span data-stu-id="6a973-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="6a973-122">Esegue i test che hanno `UnitTestClass1` in `FullyQualifiedName` **o la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="6a973-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="6a973-123">Esegue i test che hanno `UnitTestClass1` in `FullyQualifiedName` **e la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="6a973-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="6a973-124">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTestClass1` **e la cui**  `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="6a973-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="6a973-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="6a973-125">xUnit</span></span>

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| <span data-ttu-id="6a973-126">Espressione</span><span class="sxs-lookup"><span data-stu-id="6a973-126">Expression</span></span> | <span data-ttu-id="6a973-127">Risultato</span><span class="sxs-lookup"><span data-stu-id="6a973-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="6a973-128">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="6a973-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="6a973-129">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="6a973-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="6a973-130">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="6a973-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="6a973-131">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="6a973-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="6a973-132">Espressione</span><span class="sxs-lookup"><span data-stu-id="6a973-132">Expression</span></span> | <span data-ttu-id="6a973-133">Risultato</span><span class="sxs-lookup"><span data-stu-id="6a973-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="6a973-134">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="6a973-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="6a973-135">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="6a973-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="6a973-136">Esegue i test che hanno `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="6a973-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="6a973-137">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="6a973-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="6a973-138">Espressione</span><span class="sxs-lookup"><span data-stu-id="6a973-138">Expression</span></span> | <span data-ttu-id="6a973-139">Risultato</span><span class="sxs-lookup"><span data-stu-id="6a973-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="6a973-140">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **o la cui**  `Category` è `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="6a973-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="6a973-141">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **e la cui**  `Category` è `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="6a973-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="6a973-142">Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` **e la cui**  `Category` è `CategoryA` **o la cui**  `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="6a973-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
