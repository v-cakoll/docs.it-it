---
title: Esecuzione di unit test selettivi
description: Illustra come utilizzare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: caea91e9884dba6bc07a7ef6a99699e43d23399c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="b528f-103">Esecuzione di unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="b528f-103">Running selective unit tests</span></span>

<span data-ttu-id="b528f-104">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="b528f-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="b528f-105">Se si utilizza `vstest.console.exe`, sostituire `--filter ` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="b528f-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="b528f-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="b528f-106">MSTest</span></span>

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

| <span data-ttu-id="b528f-107">Espressione</span><span class="sxs-lookup"><span data-stu-id="b528f-107">Expression</span></span> | <span data-ttu-id="b528f-108">Risultato</span><span class="sxs-lookup"><span data-stu-id="b528f-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="b528f-109">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="b528f-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="b528f-110">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="b528f-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="b528f-111">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="b528f-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="b528f-112">Esegue i test inclusi nella classe `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="b528f-112">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="b528f-113">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTestClass1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="b528f-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="b528f-114">Esegue tutti i test tranne `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="b528f-114">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="b528f-115">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="b528f-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="b528f-116">Esegue i test annotati con `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="b528f-116">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="b528f-117">**Nota:** `Priority~3` è un valore non valido, in quanto non è una stringa.</span><span class="sxs-lookup"><span data-stu-id="b528f-117">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="b528f-118">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="b528f-118">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="b528f-119">Espressione</span><span class="sxs-lookup"><span data-stu-id="b528f-119">Expression</span></span> | <span data-ttu-id="b528f-120">Risultato</span><span class="sxs-lookup"><span data-stu-id="b528f-120">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="b528f-121">Esegue i test che hanno `UnitTestClass1` in `FullyQualifiedName` **o la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="b528f-121">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="b528f-122">Esegue i test che hanno `UnitTestClass1` in `FullyQualifiedName` **e la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="b528f-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="b528f-123">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTestClass1` **e la cui**  `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="b528f-123">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="b528f-124">xUnit</span><span class="sxs-lookup"><span data-stu-id="b528f-124">xUnit</span></span>

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

| <span data-ttu-id="b528f-125">Espressione</span><span class="sxs-lookup"><span data-stu-id="b528f-125">Expression</span></span> | <span data-ttu-id="b528f-126">Risultato</span><span class="sxs-lookup"><span data-stu-id="b528f-126">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="b528f-127">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="b528f-127">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="b528f-128">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="b528f-128">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="b528f-129">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="b528f-129">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="b528f-130">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="b528f-130">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="b528f-131">Espressione</span><span class="sxs-lookup"><span data-stu-id="b528f-131">Expression</span></span> | <span data-ttu-id="b528f-132">Risultato</span><span class="sxs-lookup"><span data-stu-id="b528f-132">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="b528f-133">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="b528f-133">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="b528f-134">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="b528f-134">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="b528f-135">Esegue i test che hanno `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="b528f-135">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="b528f-136">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="b528f-136">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="b528f-137">Espressione</span><span class="sxs-lookup"><span data-stu-id="b528f-137">Expression</span></span> | <span data-ttu-id="b528f-138">Risultato</span><span class="sxs-lookup"><span data-stu-id="b528f-138">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="b528f-139">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **o la cui**  `Category` è `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="b528f-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="b528f-140">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **e la cui**  `Category` è `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="b528f-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="b528f-141">Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` **e la cui**  `Category` è `CategoryA` **o la cui**  `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="b528f-141">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
