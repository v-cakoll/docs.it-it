---
title: Esecuzione di unit test selettivi - .NET Core
description: Come usare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test in .NET Core.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.custom: seodec18
ms.openlocfilehash: 3c24fb8cc5024399ae523801373b0fd8eff85f45
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151746"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="55e62-103">Esecuzione di unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="55e62-103">Running selective unit tests</span></span>

<span data-ttu-id="55e62-104">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="55e62-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="55e62-105">Se si utilizza `vstest.console.exe`, sostituire `--filter ` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="55e62-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="55e62-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="55e62-106">MSTest</span></span>

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

| <span data-ttu-id="55e62-107">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-107">Expression</span></span> | <span data-ttu-id="55e62-108">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="55e62-109">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="55e62-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="55e62-110">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="55e62-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="55e62-111">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="55e62-112">Esegue i test inclusi nella classe `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-112">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="55e62-113">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="55e62-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="55e62-114">Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-114">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="55e62-115">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="55e62-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="55e62-116">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="55e62-116">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="55e62-117">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="55e62-117">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="55e62-118">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-118">Expression</span></span> | <span data-ttu-id="55e62-119">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-119">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="55e62-120">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **o la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e62-120">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="55e62-121">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **e la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e62-121">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="55e62-122">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` **e la cui**  `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="55e62-122">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="55e62-123">xUnit</span><span class="sxs-lookup"><span data-stu-id="55e62-123">xUnit</span></span>

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

| <span data-ttu-id="55e62-124">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-124">Expression</span></span> | <span data-ttu-id="55e62-125">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-125">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="55e62-126">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-126">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="55e62-127">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-127">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="55e62-128">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-128">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="55e62-129">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="55e62-129">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="55e62-130">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-130">Expression</span></span> | <span data-ttu-id="55e62-131">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-131">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="55e62-132">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="55e62-132">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="55e62-133">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="55e62-133">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="55e62-134">Esegue i test che hanno `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="55e62-134">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="55e62-135">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="55e62-135">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="55e62-136">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-136">Expression</span></span> | <span data-ttu-id="55e62-137">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-137">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="55e62-138">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **o la cui**  `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e62-138">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="55e62-139">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **e la cui**  `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e62-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="55e62-140">Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` **e la cui**  `Category` è `CategoryA` **o la cui**  `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="55e62-140">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="55e62-141">NUnit</span><span class="sxs-lookup"><span data-stu-id="55e62-141">NUnit</span></span>

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

| <span data-ttu-id="55e62-142">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-142">Expression</span></span> | <span data-ttu-id="55e62-143">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-143">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="55e62-144">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="55e62-144">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="55e62-145">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="55e62-145">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="55e62-146">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-146">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="55e62-147">Esegue i test inclusi nella classe `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-147">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="55e62-148">Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="55e62-148">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="55e62-149">Esegue i test annotati con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="55e62-149">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="55e62-150">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="55e62-150">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="55e62-151">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="55e62-151">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="55e62-152">Espressione</span><span class="sxs-lookup"><span data-stu-id="55e62-152">Expression</span></span> | <span data-ttu-id="55e62-153">Risultato</span><span class="sxs-lookup"><span data-stu-id="55e62-153">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="55e62-154">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **o la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e62-154">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="55e62-155">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **e la cui**  `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="55e62-155">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="55e62-156">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` **e la cui**  `TestCategory` è `CategoryA` **o la cui**  `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="55e62-156">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
