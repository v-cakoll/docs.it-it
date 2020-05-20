---
title: Eseguire unit test selettivi
description: Come usare un'espressione di filtro per eseguire unit test selettivi con il comando dotnet test in .NET Core.
author: smadala
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: 6a6bbb0687742d1e3288d64fb88f6825dc678e28
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702985"
---
# <a name="run-selective-unit-tests"></a><span data-ttu-id="3491d-103">Eseguire unit test selettivi</span><span class="sxs-lookup"><span data-stu-id="3491d-103">Run selective unit tests</span></span>

<span data-ttu-id="3491d-104">Con il [`dotnet test`](../tools/dotnet-test.md) comando in .NET Core, è possibile usare un'espressione di filtro per eseguire test selettivi.</span><span class="sxs-lookup"><span data-stu-id="3491d-104">With the [`dotnet test`](../tools/dotnet-test.md) command in .NET Core, you can use a filter expression to run selective tests.</span></span> <span data-ttu-id="3491d-105">Questo articolo illustra come filtrare i test eseguiti.</span><span class="sxs-lookup"><span data-stu-id="3491d-105">This article demonstrates how to filter which tests are run.</span></span> <span data-ttu-id="3491d-106">Negli esempi seguenti viene usato `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="3491d-106">The following examples use `dotnet test`.</span></span> <span data-ttu-id="3491d-107">Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="3491d-107">If you're using `vstest.console.exe`, replace `--filter` with `--testcasefilter:`.</span></span>

## <a name="character-escaping"></a><span data-ttu-id="3491d-108">Escape di caratteri</span><span class="sxs-lookup"><span data-stu-id="3491d-108">Character escaping</span></span>

<span data-ttu-id="3491d-109">L'uso di filtri che includono punti esclamativi `!` su `*nix` richiede l'escape perché `!` è riservato.</span><span class="sxs-lookup"><span data-stu-id="3491d-109">Using filters that include exclamation mark `!` on `*nix` requires escaping since `!` is reserved.</span></span> <span data-ttu-id="3491d-110">Questo filtro, ad esempio, ignora tutti i test se lo spazio dei nomi contiene IntegrationTests:</span><span class="sxs-lookup"><span data-stu-id="3491d-110">For example, this filter skips all tests if the namespace contains IntegrationTests:</span></span>

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> <span data-ttu-id="3491d-111">La barra rovesciata precede il punto esclamativo per indicare che si tratta di un carattere di escape `\!` .</span><span class="sxs-lookup"><span data-stu-id="3491d-111">The backslash precedes the exclamation mark to indicate it is an escaped character `\!`.</span></span>

<span data-ttu-id="3491d-112">Per `FullyQualifiedName` i valori che includono una virgola per i parametri di tipo generico, usare come escape la virgola con `%2C` .</span><span class="sxs-lookup"><span data-stu-id="3491d-112">For `FullyQualifiedName` values that include a comma for generic type parameters, escape the comma with `%2C`.</span></span> <span data-ttu-id="3491d-113">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="3491d-113">For example:</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

:::zone pivot="mstest"

```csharp
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace MSTestNamespace
{
    [TestClass]
    public class UnitTest1
    {
        [TestMethod, Priority(1), TestCategory("CategoryA")]
        public void TestMethod1()
        {
        }

        [TestMethod, Priority(2)]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="3491d-114">Espressione</span><span class="sxs-lookup"><span data-stu-id="3491d-114">Expression</span></span> | <span data-ttu-id="3491d-115">Risultato</span><span class="sxs-lookup"><span data-stu-id="3491d-115">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="3491d-116">Esegue i test il cui <xref:System.Reflection.Module.FullyQualifiedName> contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="3491d-116">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="3491d-117">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3491d-117">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3491d-118">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-118">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | <span data-ttu-id="3491d-119">Esegue i test presenti nella classe `MSTestNamespace.UnitTest1` .</span><span class="sxs-lookup"><span data-stu-id="3491d-119">Runs tests that are in class `MSTestNamespace.UnitTest1`.</span></span><br><span data-ttu-id="3491d-120">**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona.</span><span class="sxs-lookup"><span data-stu-id="3491d-120">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTest1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="3491d-121">Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-121">Runs all tests except `MSTestNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3491d-122">Esegue i test annotati con `[TestCategory("CategoryA")]` .</span><span class="sxs-lookup"><span data-stu-id="3491d-122">Runs tests that are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="3491d-123">Esegue i test annotati con `[Priority(2)]` .</span><span class="sxs-lookup"><span data-stu-id="3491d-123">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="3491d-124">Esempi di utilizzo degli operatori condizionali `|` e `&` :</span><span class="sxs-lookup"><span data-stu-id="3491d-124">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="3491d-125">Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **o** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> sono `"CategoryA"` .</span><span class="sxs-lookup"><span data-stu-id="3491d-125">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> is `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="3491d-126">Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **e** hanno un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> di `"CategoryA"` .</span><span class="sxs-lookup"><span data-stu-id="3491d-126">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="3491d-127">Per eseguire test che <xref:System.Reflection.Module.FullyQualifiedName> contengono `UnitTest1` **e** hanno una classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> di `"CategoryA"` **o** hanno un oggetto <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> con priorità `1` .</span><span class="sxs-lookup"><span data-stu-id="3491d-127">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> of `"CategoryA"` **or** have a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> with a priority of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="xunit"

```csharp
using Xunit;

namespace XUnitNamespace
{
    public class TestClass1
    {
        [Fact, Trait("Priority", "1"), Trait("Category", "CategoryA")]
        public void Test1()
        {
        }

        [Fact, Trait("Priority", "2")]
        public void Test2()
        {
        }
    }
}
```

| <span data-ttu-id="3491d-128">Espressione</span><span class="sxs-lookup"><span data-stu-id="3491d-128">Expression</span></span> | <span data-ttu-id="3491d-129">Risultato</span><span class="sxs-lookup"><span data-stu-id="3491d-129">Result</span></span> |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3491d-130">Esegue solo un test, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-130">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="3491d-131">Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-131">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="3491d-132">Esegue i test il cui nome visualizzato contiene `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-132">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="3491d-133">Nell'esempio di codice, i tratti definiti con le chiavi `"Category"` e `"Priority"` possono essere utilizzati per il filtraggio.</span><span class="sxs-lookup"><span data-stu-id="3491d-133">In the code example, the defined traits with keys `"Category"` and `"Priority"` can be used for filtering.</span></span>

| <span data-ttu-id="3491d-134">Espressione</span><span class="sxs-lookup"><span data-stu-id="3491d-134">Expression</span></span> | <span data-ttu-id="3491d-135">Risultato</span><span class="sxs-lookup"><span data-stu-id="3491d-135">Result</span></span> |
|--|--|
| `dotnet test --filter XUnit` | <span data-ttu-id="3491d-136">Esegue i test il cui <xref:System.Reflection.Module.FullyQualifiedName> contiene `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="3491d-136">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `XUnit`.</span></span>  <span data-ttu-id="3491d-137">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3491d-137">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=CategoryA` | <span data-ttu-id="3491d-138">Esegue i test con `[Trait("Category", "CategoryA")]` .</span><span class="sxs-lookup"><span data-stu-id="3491d-138">Runs tests that have `[Trait("Category", "CategoryA")]`.</span></span> |

<span data-ttu-id="3491d-139">Esempi di utilizzo degli operatori condizionali `|` e `&` :</span><span class="sxs-lookup"><span data-stu-id="3491d-139">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="3491d-140">Per eseguire i test che hanno `TestClass1` in <xref:System.Reflection.Module.FullyQualifiedName> **o** avere un `Trait` con la chiave `"Category"` e il valore di `"CategoryA"` .</span><span class="sxs-lookup"><span data-stu-id="3491d-140">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

<span data-ttu-id="3491d-141">Per eseguire i test che hanno `TestClass1` in <xref:System.Reflection.Module.FullyQualifiedName> **e** hanno un oggetto `Trait` con una chiave `"Category"` e un valore pari a `"CategoryA"` .</span><span class="sxs-lookup"><span data-stu-id="3491d-141">To run tests that have `TestClass1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

<span data-ttu-id="3491d-142">Per eseguire i test che <xref:System.Reflection.Module.FullyQualifiedName> contengono `TestClass1` **e** hanno un oggetto `Trait` con la chiave `"Category"` e il valore di `"CategoryA"` **o** hanno un `Trait` con la chiave `"Priority"` e il valore di `1` .</span><span class="sxs-lookup"><span data-stu-id="3491d-142">To run tests that have either <xref:System.Reflection.Module.FullyQualifiedName> containing `TestClass1` **and** have a `Trait` with a key of `"Category"` and value of `"CategoryA"` **or** have a `Trait` with a key of `"Priority"` and value of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)|Priority=1"
```

:::zone-end
:::zone pivot="nunit"

```csharp
using NUnit.Framework;

namespace NUnitNamespace
{
    public class UnitTest1
    {
        [Test, Property("Priority", 1), Category("CategoryA")]
        public void TestMethod1()
        {
        }

        [Test, Property("Priority", 2)]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="3491d-143">Espressione</span><span class="sxs-lookup"><span data-stu-id="3491d-143">Expression</span></span> | <span data-ttu-id="3491d-144">Risultato</span><span class="sxs-lookup"><span data-stu-id="3491d-144">Result</span></span> |
|--|--|
| `dotnet test --filter Method` | <span data-ttu-id="3491d-145">Esegue i test il cui <xref:System.Reflection.Module.FullyQualifiedName> contiene `Method`.</span><span class="sxs-lookup"><span data-stu-id="3491d-145">Runs tests whose <xref:System.Reflection.Module.FullyQualifiedName> contains `Method`.</span></span> <span data-ttu-id="3491d-146">Disponibile in `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="3491d-146">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="3491d-147">Esegue i test il cui nome contiene `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-147">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | <span data-ttu-id="3491d-148">Esegue i test presenti nella classe `NUnitNamespace.UnitTest1` .</span><span class="sxs-lookup"><span data-stu-id="3491d-148">Runs tests that are in class `NUnitNamespace.UnitTest1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | <span data-ttu-id="3491d-149">Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="3491d-149">Runs all tests except `NUnitNamespace.UnitTest1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="3491d-150">Esegue i test annotati con `[Category("CategoryA")]` .</span><span class="sxs-lookup"><span data-stu-id="3491d-150">Runs tests that are annotated with `[Category("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=2` | <span data-ttu-id="3491d-151">Esegue i test annotati con `[Priority(2)]` .</span><span class="sxs-lookup"><span data-stu-id="3491d-151">Runs tests that are annotated with `[Priority(2)]`.</span></span> |

<span data-ttu-id="3491d-152">Esempi di utilizzo degli operatori condizionali `|` e `&` :</span><span class="sxs-lookup"><span data-stu-id="3491d-152">Examples using the conditional operators `|` and `&`:</span></span>

<span data-ttu-id="3491d-153">Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **o** hanno un `Category` di `"CategoryA"` .</span><span class="sxs-lookup"><span data-stu-id="3491d-153">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **or** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

<span data-ttu-id="3491d-154">Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **e** hanno un `Category` di `"CategoryA"` .</span><span class="sxs-lookup"><span data-stu-id="3491d-154">To run tests that have `UnitTest1` in their <xref:System.Reflection.Module.FullyQualifiedName> **and** have a `Category` of `"CategoryA"`.</span></span>

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

<span data-ttu-id="3491d-155">Per eseguire i test che dispongono di un oggetto che <xref:System.Reflection.Module.FullyQualifiedName> contiene `UnitTest1` **e** hanno un oggetto o un oggetto `Category` `"CategoryA"` **or** `Property` con un oggetto `"Priority"` di tipo `1` .</span><span class="sxs-lookup"><span data-stu-id="3491d-155">To run tests that have either a <xref:System.Reflection.Module.FullyQualifiedName> containing `UnitTest1` **and** have a `Category` of `"CategoryA"` **or** have a `Property` with a `"Priority"` of `1`.</span></span>

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

<span data-ttu-id="3491d-156">Per altre informazioni, vedere [filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span><span class="sxs-lookup"><span data-stu-id="3491d-156">For more information, see [TestCase filter](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).</span></span>

:::zone-end

## <a name="see-also"></a><span data-ttu-id="3491d-157">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3491d-157">See also</span></span>

- [<span data-ttu-id="3491d-158">dotnet test</span><span class="sxs-lookup"><span data-stu-id="3491d-158">dotnet test</span></span>](../tools/dotnet-test.md)
- [<span data-ttu-id="3491d-159">test DotNet-filtro</span><span class="sxs-lookup"><span data-stu-id="3491d-159">dotnet test --filter</span></span>](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a><span data-ttu-id="3491d-160">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3491d-160">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="3491d-161">Ordina unit test</span><span class="sxs-lookup"><span data-stu-id="3491d-161">Order unit tests</span></span>](order-unit-tests.md)
