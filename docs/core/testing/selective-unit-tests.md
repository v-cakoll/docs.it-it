---
title: Esecuzione di unit test selettivi
description: Come usare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test in .NET Core.
author: smadala
ms.date: 03/22/2017
ms.openlocfilehash: b9156300587215e68c01c609e298dbc1a2c53d11
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77543508"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="cb34f-103">Esecuzione di unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="cb34f-103">Running selective unit tests</span></span>

<span data-ttu-id="cb34f-104">Con il comando `dotnet test` in .NET Core è possibile usare un'espressione filtro per eseguire test selettivi.</span><span class="sxs-lookup"><span data-stu-id="cb34f-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="cb34f-105">Questo articolo illustra come filtrare i test eseguiti.</span><span class="sxs-lookup"><span data-stu-id="cb34f-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="cb34f-106">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="cb34f-107">Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

> [!NOTE]
> <span data-ttu-id="cb34f-108">L'utilizzo di filtri che includono `*nix` un punto esclamativo (!) su richiede l'esclusione poiché `!` è riservato.</span><span class="sxs-lookup"><span data-stu-id="cb34f-108">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="cb34f-109">Ad esempio, questo filtro ignora tutti i test `dotnet test --filter FullyQualifiedName\!~IntegrationTests`se lo spazio dei nomi contiene IntegrationTests: .</span><span class="sxs-lookup"><span data-stu-id="cb34f-109">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
> <span data-ttu-id="cb34f-110">Si noti la barra rovesciata che precede il punto esclamativo.</span><span class="sxs-lookup"><span data-stu-id="cb34f-110">Note the backslash that precedes the exclamation mark.</span></span>

## <a name="mstest"></a><span data-ttu-id="cb34f-111">MSTest</span><span class="sxs-lookup"><span data-stu-id="cb34f-111">MSTest</span></span>

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

| <span data-ttu-id="cb34f-112">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-112">Expression</span></span> | <span data-ttu-id="cb34f-113">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-113">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="cb34f-114">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-114">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="cb34f-115">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-115">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cb34f-116">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-116">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="cb34f-117">Esegue i test inclusi nella classe `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-117">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="cb34f-118">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="cb34f-118">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cb34f-119">Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-119">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cb34f-120">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-120">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cb34f-121">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-121">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="cb34f-122">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="cb34f-122">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cb34f-123">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-123">Expression</span></span> | <span data-ttu-id="cb34f-124">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-124">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="cb34f-125">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*o la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-125">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="cb34f-126">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*e la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-126">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cb34f-127">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` \*\*e la cui \*\* `TestCategory` è `CategoryA` \*\*o la cui \*\* `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="cb34f-127">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="cb34f-128">xUnit</span><span class="sxs-lookup"><span data-stu-id="cb34f-128">xUnit</span></span>

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

| <span data-ttu-id="cb34f-129">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-129">Expression</span></span> | <span data-ttu-id="cb34f-130">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-130">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cb34f-131">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-131">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="cb34f-132">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-132">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="cb34f-133">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-133">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="cb34f-134">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="cb34f-134">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="cb34f-135">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-135">Expression</span></span> | <span data-ttu-id="cb34f-136">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-136">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="cb34f-137">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-137">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="cb34f-138">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-138">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="cb34f-139">Esegue i test che hanno `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-139">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="cb34f-140">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="cb34f-140">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cb34f-141">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-141">Expression</span></span> | <span data-ttu-id="cb34f-142">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-142">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="cb34f-143">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` \*\*o la cui \*\* `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-143">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="cb34f-144">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` \*\*e la cui \*\* `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-144">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cb34f-145">Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` \*\*e la cui \*\* `Category` è `CategoryA` \*\*o la cui \*\* `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="cb34f-145">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="cb34f-146">NUnit</span><span class="sxs-lookup"><span data-stu-id="cb34f-146">NUnit</span></span>

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

| <span data-ttu-id="cb34f-147">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-147">Expression</span></span> | <span data-ttu-id="cb34f-148">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-148">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="cb34f-149">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-149">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="cb34f-150">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-150">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="cb34f-151">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-151">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="cb34f-152">Esegue i test inclusi nella classe `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-152">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="cb34f-153">Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-153">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="cb34f-154">Esegue i test annotati con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-154">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="cb34f-155">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-155">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="cb34f-156">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="cb34f-156">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="cb34f-157">Expression</span><span class="sxs-lookup"><span data-stu-id="cb34f-157">Expression</span></span> | <span data-ttu-id="cb34f-158">Risultato</span><span class="sxs-lookup"><span data-stu-id="cb34f-158">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="cb34f-159">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*o la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-159">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="cb34f-160">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*e la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="cb34f-160">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="cb34f-161">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` \*\*e la cui \*\* `TestCategory` è `CategoryA` \*\*o la cui \*\* `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="cb34f-161">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |
