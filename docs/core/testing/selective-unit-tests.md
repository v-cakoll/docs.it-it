---
title: Esecuzione di unit test selettivi
description: Come usare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test in .NET Core.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: 57428dad2de6c2507ca2cdc42e3df9e83a1edd69
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715453"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="75ab4-103">Esecuzione di unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="75ab4-103">Running selective unit tests</span></span>

<span data-ttu-id="75ab4-104">Con il comando `dotnet test` in .NET Core è possibile usare un'espressione filtro per eseguire test selettivi.</span><span class="sxs-lookup"><span data-stu-id="75ab4-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="75ab4-105">Questo articolo illustra come filtrare i test eseguiti.</span><span class="sxs-lookup"><span data-stu-id="75ab4-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="75ab4-106">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="75ab4-107">Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="75ab4-108">MSTest</span><span class="sxs-lookup"><span data-stu-id="75ab4-108">MSTest</span></span>

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestCategory("CategoryA")]
        [Priority(1)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [Priority(2)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="75ab4-109">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-109">Expression</span></span> | <span data-ttu-id="75ab4-110">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-110">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="75ab4-111">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-111">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="75ab4-112">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-112">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="75ab4-113">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-113">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="75ab4-114">Esegue i test inclusi nella classe `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-114">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="75ab4-115">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="75ab4-115">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="75ab4-116">Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-116">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="75ab4-117">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-117">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="75ab4-118">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-118">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="75ab4-119">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="75ab4-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="75ab4-120">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-120">Expression</span></span> | <span data-ttu-id="75ab4-121">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="75ab4-122">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **o** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-122">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="75ab4-123">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **e** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-123">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="75ab4-124">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` **e** `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="75ab4-124">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="75ab4-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="75ab4-125">xUnit</span></span>

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "CategoryA")]
        [Trait("Priority", "1")]
        [Fact]
        public void Test1()
        {
        }

        [Trait("Priority", "2")]
        [Fact]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="75ab4-126">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-126">Expression</span></span> | <span data-ttu-id="75ab4-127">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="75ab4-128">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="75ab4-129">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="75ab4-130">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="75ab4-131">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="75ab4-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="75ab4-132">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-132">Expression</span></span> | <span data-ttu-id="75ab4-133">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="75ab4-134">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="75ab4-135">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="75ab4-136">Esegue i test che hanno `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-136">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="75ab4-137">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="75ab4-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="75ab4-138">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-138">Expression</span></span> | <span data-ttu-id="75ab4-139">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="75ab4-140">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **o** `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="75ab4-141">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **e** `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="75ab4-142">Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` **e** `Category` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="75ab4-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="75ab4-143">NUnit</span><span class="sxs-lookup"><span data-stu-id="75ab4-143">NUnit</span></span>

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Category("CategoryA")]
        [Property("Priority", 1)]
        [Test]
        public void TestMethod1()
        {
        }

        [Property("Priority", 2)]
        [Test]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="75ab4-144">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-144">Expression</span></span> | <span data-ttu-id="75ab4-145">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-145">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="75ab4-146">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-146">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="75ab4-147">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-147">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="75ab4-148">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-148">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="75ab4-149">Esegue i test inclusi nella classe `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-149">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="75ab4-150">Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-150">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="75ab4-151">Esegue i test annotati con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-151">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="75ab4-152">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-152">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="75ab4-153">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="75ab4-153">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="75ab4-154">Espressione</span><span class="sxs-lookup"><span data-stu-id="75ab4-154">Expression</span></span> | <span data-ttu-id="75ab4-155">Risultato</span><span class="sxs-lookup"><span data-stu-id="75ab4-155">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="75ab4-156">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **o** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-156">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="75ab4-157">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **e** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="75ab4-157">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="75ab4-158">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` **e** `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="75ab4-158">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
