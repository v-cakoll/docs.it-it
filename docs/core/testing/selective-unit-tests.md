---
title: Esecuzione di unit test selettivi
description: Come usare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test in .NET Core.
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: 50642126f3b470180ddd303ed4a2d2d90bfa5b8f
ms.sourcegitcommit: 7370aa8203b6036cea1520021b5511d0fd994574
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/02/2020
ms.locfileid: "82728187"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="9f2ae-103">Eseguire unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="9f2ae-103">Run selective unit tests</span></span>

<span data-ttu-id="9f2ae-104">Con il comando `dotnet test` in .NET Core è possibile usare un'espressione filtro per eseguire test selettivi.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="9f2ae-105">Questo articolo illustra come filtrare i test eseguiti.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="9f2ae-106">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="9f2ae-107">Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="9f2ae-108">Escape di caratteri</span><span class="sxs-lookup"><span data-stu-id="9f2ae-108">Character escaping</span></span>

<span data-ttu-id="9f2ae-109">L'uso di filtri che includono punti esclamativi ( `*nix` !) in richiede `!` l'escape perché è riservato.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="9f2ae-110">Questo filtro, ad esempio, ignora tutti i test se lo spazio dei nomi `dotnet test --filter FullyQualifiedName\!~IntegrationTests`contiene IntegrationTests:.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="9f2ae-111">Si noti la barra rovesciata che precede il punto esclamativo.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="9f2ae-112">Per `FullyQualifiedName` i valori che includono una virgola per i parametri di tipo generico, `%2C`usare come escape la virgola con.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="9f2ae-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="9f2ae-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="9f2ae-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="9f2ae-114">MSTest</span></span>

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

| <span data-ttu-id="9f2ae-115">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-115">Expression</span></span> | <span data-ttu-id="9f2ae-116">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="9f2ae-117">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="9f2ae-118">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="9f2ae-119">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="9f2ae-120">Esegue i test presenti nella classe `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-120">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="9f2ae-121">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="9f2ae-122">Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="9f2ae-123">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-123">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="9f2ae-124">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-124">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="9f2ae-125">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="9f2ae-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="9f2ae-126">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-126">Expression</span></span> | <span data-ttu-id="9f2ae-127">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="9f2ae-128">Esegue i test che `UnitTest1` hanno `FullyQualifiedName` in **o** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-128">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="9f2ae-129">Esegue i test che `UnitTest1` hanno `FullyQualifiedName` in **e** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-129">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="9f2ae-130">`FullyQualifiedName` Esegue i test che contengono `UnitTest1` **e** `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-130">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="9f2ae-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="9f2ae-131">xUnit</span></span>

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

| <span data-ttu-id="9f2ae-132">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-132">Expression</span></span> | <span data-ttu-id="9f2ae-133">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="9f2ae-134">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="9f2ae-135">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="9f2ae-136">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="9f2ae-137">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="9f2ae-138">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-138">Expression</span></span> | <span data-ttu-id="9f2ae-139">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="9f2ae-140">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="9f2ae-141">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="9f2ae-142">Esegue i test con `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-142">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="9f2ae-143">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="9f2ae-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="9f2ae-144">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-144">Expression</span></span> | <span data-ttu-id="9f2ae-145">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="9f2ae-146">Esegue i test che `TestClass1` hanno `FullyQualifiedName` in **o** `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-146">Runs tests that have `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="9f2ae-147">Esegue i test che `TestClass1` hanno `FullyQualifiedName` in **e** `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-147">Runs tests that have `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="9f2ae-148">`FullyQualifiedName` Esegue i test che contengono `TestClass1` **e** `Category` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-148">Runs tests that have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="9f2ae-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="9f2ae-149">NUnit</span></span>

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

| <span data-ttu-id="9f2ae-150">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-150">Expression</span></span> | <span data-ttu-id="9f2ae-151">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="9f2ae-152">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="9f2ae-153">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="9f2ae-154">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="9f2ae-155">Esegue i test presenti nella classe `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-155">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="9f2ae-156">Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="9f2ae-157">Esegue i test annotati con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-157">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="9f2ae-158">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-158">Runs tests that are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="9f2ae-159">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="9f2ae-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="9f2ae-160">Expression</span><span class="sxs-lookup"><span data-stu-id="9f2ae-160">Expression</span></span> | <span data-ttu-id="9f2ae-161">Risultato</span><span class="sxs-lookup"><span data-stu-id="9f2ae-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="9f2ae-162">Esegue i test che `UnitTest1` hanno `FullyQualifiedName` in **o** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-162">Runs tests that have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="9f2ae-163">Esegue i test che `UnitTest1` hanno `FullyQualifiedName` in **e** `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-163">Runs tests that have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="9f2ae-164">`FullyQualifiedName` Esegue i test che contengono `UnitTest1` **e** `TestCategory` è `CategoryA` **o** `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="9f2ae-164">Runs tests that have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="9f2ae-165">Per altre informazioni, vedere [filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="9f2ae-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
