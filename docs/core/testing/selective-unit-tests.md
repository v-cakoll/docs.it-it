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
# <a name="running-selective-unit-tests"></a>Esecuzione di unit test selettivi

Con il comando `dotnet test` in .NET Core è possibile usare un'espressione filtro per eseguire test selettivi. Questo articolo illustra come filtrare i test eseguiti. Negli esempi seguenti viene usato `dotnet test`. Se si utilizza `vstest.console.exe`, sostituire `--filter` con `--testcasefilter:`.

## <a name="character-escaping"></a>Escape di caratteri

L'uso di filtri che includono punti esclamativi ( `*nix` !) in richiede `!` l'escape perché è riservato. Questo filtro, ad esempio, ignora tutti i test se lo spazio dei nomi `dotnet test --filter FullyQualifiedName\!~IntegrationTests`contiene IntegrationTests:.
Si noti la barra rovesciata che precede il punto esclamativo.

Per `FullyQualifiedName` i valori che includono una virgola per i parametri di tipo generico, `%2C`usare come escape la virgola con. Ad esempio:

```dotnetcli
dotnet test --filter "FullyQualifiedName=MyNamespace.MyTestsClass<ParameterType1%2CParameterType2>.MyTestMethod"
```

## <a name="mstest"></a>MSTest

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

| Expression | Risultato |
| ---------- | ------ |
| `dotnet test --filter Method` | Esegue i test il cui `FullyQualifiedName` contiene `Method`. Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Esegue i test il cui nome contiene `TestMethod1`. |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTest1` | Esegue i test inclusi nella classe `MSTestNamespace.UnitTest1`.<br>**Nota:** il valore `ClassName` deve avere uno spazio dei nomi, pertanto `ClassName=UnitTest1` non funziona. |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTest1.TestMethod1` | Esegue tutti i test tranne `MSTestNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Esegue i test annotati con `[TestCategory("CategoryA")]`. |
| `dotnet test --filter Priority=2` | Esegue i test annotati con `[Priority(2)]`.<br>

**Utilizzo degli operatori condizionali | e &amp;**

| Expression | Risultato |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **o la cui ** `TestCategory` è `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **e la cui ** `TestCategory` è `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` **e la cui ** `TestCategory` è `CategoryA` **o la cui ** `Priority` è 1. |

## <a name="xunit"></a>xUnit

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

| Expression | Risultato |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | Esegue solo un test, `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | Esegue tutti i test tranne `XUnitNamespace.TestClass1.Test1`. |
| `dotnet test --filter DisplayName~TestClass1` | Esegue i test il cui nome visualizzato contiene `TestClass1`. |

Nell'esempio di codice, i tratti definiti con le chiavi `Category` e `Priority` possono essere utilizzati per il filtraggio.

| Expression | Risultato |
| ---------- | ------ |
| `dotnet test --filter XUnit` | Esegue i test il cui `FullyQualifiedName` contiene `XUnit`.  Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Category=CategoryA` | Esegue i test che hanno `[Trait("Category", "CategoryA")]`. |

**Utilizzo degli operatori condizionali | e &amp;**

| Expression | Risultato |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=CategoryA"</code> | Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **o la cui ** `Category` è `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=CategoryA"` | Esegue i test che hanno `TestClass1` in `FullyQualifiedName` **e la cui ** `Category` è `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=CategoryA)&#124;Priority=1"</code> | Esegue i test che hanno `FullyQualifiedName` contenente `TestClass1` **e la cui ** `Category` è `CategoryA` **o la cui ** `Priority` è 1. |

## <a name="nunit"></a>NUnit

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

| Expression | Risultato |
| ---------- | ------ |
| `dotnet test --filter Method` | Esegue i test il cui `FullyQualifiedName` contiene `Method`. Disponibile in `vstest 15.1+`. |
| `dotnet test --filter Name~TestMethod1` | Esegue i test il cui nome contiene `TestMethod1`. |
| `dotnet test --filter FullyQualifiedName~NUnitNamespace.UnitTest1` | Esegue i test inclusi nella classe `NUnitNamespace.UnitTest1`.<br>
| `dotnet test --filter FullyQualifiedName!=NUnitNamespace.UnitTest1.TestMethod1` | Esegue tutti i test tranne `NUnitNamespace.UnitTest1.TestMethod1`. |
| `dotnet test --filter TestCategory=CategoryA` | Esegue i test annotati con `[Category("CategoryA")]`. |
| `dotnet test --filter Priority=2` | Esegue i test annotati con `[Priority(2)]`.<br>

**Utilizzo degli operatori condizionali | e &amp;**

| Expression | Risultato |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTest1&#124;TestCategory=CategoryA"</code> | Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **o la cui ** `TestCategory` è `CategoryA`. |
| `dotnet test --filter "FullyQualifiedName~UnitTest1&TestCategory=CategoryA"` | Esegue i test che hanno `UnitTest1` in `FullyQualifiedName` **e la cui ** `TestCategory` è `CategoryA`. |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTest1&TestCategory=CategoryA)&#124;Priority=1"</code> | Esegue i test che hanno `FullyQualifiedName` contenente `UnitTest1` **e la cui ** `TestCategory` è `CategoryA` **o la cui ** `Priority` è 1. |

Per altre informazioni, vedere [filtro TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).
