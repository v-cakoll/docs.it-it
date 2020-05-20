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
# <a name="run-selective-unit-tests"></a>Eseguire unit test selettivi

Con il [`dotnet test`](../tools/dotnet-test.md) comando in .NET Core, è possibile usare un'espressione di filtro per eseguire test selettivi. Questo articolo illustra come filtrare i test eseguiti. Negli esempi seguenti viene usato `dotnet test`. Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.

## <a name="character-escaping"></a>Escape di caratteri

L'uso di filtri che includono punti esclamativi `!` su `*nix` richiede l'escape perché `!` è riservato. Questo filtro, ad esempio, ignora tutti i test se lo spazio dei nomi contiene IntegrationTests:

```dotnetcli
dotnet test --filter FullyQualifiedName\!~IntegrationTests
```

> [!IMPORTANT]
> La barra rovesciata precede il punto esclamativo per indicare che si tratta di un carattere di escape `\!` .

Per `FullyQualifiedName` i valori che includono una virgola per i parametri di tipo generico, usare come escape la virgola con `%2C` . Ad esempio:

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

| Espressione | Risultato |
|--|--|
| `dotnet test --filter Method` | Esegue i test il cui <xref:System.Reflection.Module.FullyQualifiedName> contiene `Method`. Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Esegue i test il cui nome contiene `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | Esegue i test presenti nella classe `MSTestNamespace.UnitTest1` .<br>**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Esegue i test annotati con `[TestCategory("CategoryA")]` . |
| `dotnet test --filter Priority=2` | Esegue i test annotati con `[Priority(2)]` . |

Esempi di utilizzo degli operatori condizionali `|` e `&` :

Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **o** <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> sono `"CategoryA"` .

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **e** hanno un <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> di `"CategoryA"` .

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

Per eseguire test che <xref:System.Reflection.Module.FullyQualifiedName> contengono `UnitTest1` **e** hanno una classe <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCategoryAttribute> di `"CategoryA"` **o** hanno un oggetto <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute> con priorità `1` .

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

| Espressione | Risultato |
|--|--|
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Esegue solo un test, `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Esegue i test il cui nome visualizzato contiene `TestClass1`. |

Nell'esempio di codice, i tratti definiti con le chiavi `"Category"` e `"Priority"` possono essere utilizzati per il filtraggio.

| Espressione | Risultato |
|--|--|
| `dotnet test --filter XUnit` | Esegue i test il cui <xref:System.Reflection.Module.FullyQualifiedName> contiene `XUnit`.  Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Category=CategoryA` | Esegue i test con `[Trait("Category", "CategoryA")]` . |

Esempi di utilizzo degli operatori condizionali `|` e `&` :

Per eseguire i test che hanno `TestClass1` in <xref:System.Reflection.Module.FullyQualifiedName> **o** avere un `Trait` con la chiave `"Category"` e il valore di `"CategoryA"` .

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1|Category=CategoryA"
```

Per eseguire i test che hanno `TestClass1` in <xref:System.Reflection.Module.FullyQualifiedName> **e** hanno un oggetto `Trait` con una chiave `"Category"` e un valore pari a `"CategoryA"` .

```dotnetcli
dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"
```

Per eseguire i test che <xref:System.Reflection.Module.FullyQualifiedName> contengono `TestClass1` **e** hanno un oggetto `Trait` con la chiave `"Category"` e il valore di `"CategoryA"` **o** hanno un `Trait` con la chiave `"Priority"` e il valore di `1` .

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

| Espressione | Risultato |
|--|--|
| `dotnet test --filter Method` | Esegue i test il cui <xref:System.Reflection.Module.FullyQualifiedName> contiene `Method`. Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Esegue i test il cui nome contiene `TestMethod1`. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | Esegue i test presenti nella classe `NUnitNamespace.UnitTest1` . |
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Esegue i test annotati con `[Category("CategoryA")]` . |
| `dotnet test --filter Priority=2` | Esegue i test annotati con `[Priority(2)]` . |

Esempi di utilizzo degli operatori condizionali `|` e `&` :

Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **o** hanno un `Category` di `"CategoryA"` .

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1|TestCategory=CategoryA"
```

Per eseguire i test che hanno `UnitTest1` in <xref:System.Reflection.Module.FullyQualifiedName> **e** hanno un `Category` di `"CategoryA"` .

```dotnetcli
dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"
```

Per eseguire i test che dispongono di un oggetto che <xref:System.Reflection.Module.FullyQualifiedName> contiene `UnitTest1` **e** hanno un oggetto o un oggetto `Category` `"CategoryA"` **or** `Property` con un oggetto `"Priority"` di tipo `1` .

```dotnetcli
dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)|Priority=1"
```

Per altre informazioni, vedere [filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).

:::zone-end

## <a name="see-also"></a>Vedere anche

- [dotnet test](../tools/dotnet-test.md)
- [test DotNet-filtro](../tools/dotnet-test.md#filter-option-details)

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Ordina unit test](order-unit-tests.md)
