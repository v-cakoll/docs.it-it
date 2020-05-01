---
title: Esecuzione di unit test selettivi
description: Come usare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test in .NET Core.
author: smadala
ms.date: 04/29/2020
ms.openlocfilehash: e66455b5ac012114c45d998fae11da7ee769fbe2
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624917"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="5b5a2-103">Esecuzione di unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="5b5a2-103">Running selective unit tests</span></span>

<span data-ttu-id="5b5a2-104">Con il comando `dotnet test` in .NET Core è possibile usare un'espressione filtro per eseguire test selettivi.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-104">With the `dotnet test` command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="5b5a2-105">Questo articolo illustra come filtrare i test eseguiti.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-105">This article demonstrates how to filter which test are run.</span></span> <span data-ttu-id="5b5a2-106">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="5b5a2-107">Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="5b5a2-108">Escape di caratteri</span><span class="sxs-lookup"><span data-stu-id="5b5a2-108">Character escaping</span></span>

<span data-ttu-id="5b5a2-109">L'uso di filtri che includono punti esclamativi ( `*nix` !) in richiede `!` l'escape perché è riservato.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-109">Using filters that include exclamation mark (!) on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="5b5a2-110">Questo filtro, ad esempio, ignora tutti i test se lo spazio dei nomi `dotnet test --filter FullyQualifiedName\!~IntegrationTests`contiene IntegrationTests:.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-110">For example, this filter skips all tests if the namespace contains IntegrationTests: `dotnet test --filter FullyQualifiedName\!~IntegrationTests`.</span></span>
<span data-ttu-id="5b5a2-111">Si noti la barra rovesciata che precede il punto esclamativo.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-111">Note the backslash that precedes the exclamation mark.</span></span>

<span data-ttu-id="5b5a2-112">Per `FullyQualifiedName` i valori che includono una virgola per i parametri di tipo generico, `%2C`usare come escape la virgola con.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="5b5a2-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5b5a2-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a><span data-ttu-id="5b5a2-114">MSTest</span><span class="sxs-lookup"><span data-stu-id="5b5a2-114">MSTest</span></span>

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

| <span data-ttu-id="5b5a2-115">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-115">Expression</span></span> | <span data-ttu-id="5b5a2-116">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-116">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="5b5a2-117">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-117">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="5b5a2-118">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-118">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="5b5a2-119">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-119">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="5b5a2-120">Esegue i test inclusi nella classe `MSTestNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-120">Runs tests which are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="5b5a2-121">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-121">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="5b5a2-122">Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-122">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="5b5a2-123">Esegue i test annotati con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-123">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="5b5a2-124">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-124">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="5b5a2-125">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="5b5a2-125">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="5b5a2-126">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-126">Expression</span></span> | <span data-ttu-id="5b5a2-127">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-127">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="5b5a2-128">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*o la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-128">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="5b5a2-129">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*e la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-129">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="5b5a2-130">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` \*\*e la cui \*\* `TestCategory` è `CategoryA` \*\*o la cui \*\* `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-130">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="5b5a2-131">xUnit</span><span class="sxs-lookup"><span data-stu-id="5b5a2-131">xUnit</span></span>

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

| <span data-ttu-id="5b5a2-132">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-132">Expression</span></span> | <span data-ttu-id="5b5a2-133">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="5b5a2-134">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-134">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="5b5a2-135">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-135">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="5b5a2-136">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-136">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="5b5a2-137">Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-137">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="5b5a2-138">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-138">Expression</span></span> | <span data-ttu-id="5b5a2-139">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-139">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="5b5a2-140">Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-140">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="5b5a2-141">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-141">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="5b5a2-142">Esegue i test che hanno `[Trait("Category", "CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-142">Runs tests which have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="5b5a2-143">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="5b5a2-143">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="5b5a2-144">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-144">Expression</span></span> | <span data-ttu-id="5b5a2-145">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-145">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | <span data-ttu-id="5b5a2-146">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` \*\*o la cui \*\* `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-146">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | <span data-ttu-id="5b5a2-147">Esegue i test che hanno `TestClass1` in `FullyQualifiedName` \*\*e la cui \*\* `Category` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-147">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="5b5a2-148">Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` \*\*e la cui \*\* `Category` è `CategoryA` \*\*o la cui \*\* `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-148">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="nunit"></a><span data-ttu-id="5b5a2-149">NUnit</span><span class="sxs-lookup"><span data-stu-id="5b5a2-149">NUnit</span></span>

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

| <span data-ttu-id="5b5a2-150">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-150">Expression</span></span> | <span data-ttu-id="5b5a2-151">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-151">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="5b5a2-152">Esegue i test il cui `FullyQualifiedName` contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-152">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="5b5a2-153">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-153">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="5b5a2-154">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-154">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="5b5a2-155">Esegue i test inclusi nella classe `NUnitNamespace.UnitTest1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-155">Runs tests which are in class `NUnitNamespace.UnitTest1`.</span></span><br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="5b5a2-156">Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-156">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="5b5a2-157">Esegue i test annotati con `[Category("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-157">Runs tests which are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="5b5a2-158">Esegue i test annotati con `[Priority(2)]`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-158">Runs tests which are annotated with `[Priority(2)]`.</span></span><br>

<span data-ttu-id="5b5a2-159">**Utilizzo degli operatori condizionali | e &amp;**</span><span class="sxs-lookup"><span data-stu-id="5b5a2-159">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="5b5a2-160">Expression</span><span class="sxs-lookup"><span data-stu-id="5b5a2-160">Expression</span></span> | <span data-ttu-id="5b5a2-161">Risultato</span><span class="sxs-lookup"><span data-stu-id="5b5a2-161">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="5b5a2-162">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*o la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-162">Runs tests which have `UnitTest1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | <span data-ttu-id="5b5a2-163">Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` \*\*e la cui \*\* `TestCategory` è `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-163">Runs tests which have `UnitTest1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="5b5a2-164">Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` \*\*e la cui \*\* `TestCategory` è `CategoryA` \*\*o la cui \*\* `Priority` è 1.</span><span class="sxs-lookup"><span data-stu-id="5b5a2-164">Runs tests which have either `FullyQualifiedName` containing `UnitTest1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

<span data-ttu-id="5b5a2-165">Per altre informazioni, vedere [filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="5b5a2-165">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>
