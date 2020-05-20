---
title: Ordina unit test
description: Informazioni su come ordinare unit test con .NET Core.
author: IEvangelist
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: ce0d01c924075ffcc9ad49ef8aca49222c10c921
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83704559"
---
# <a name="order-unit-tests"></a>Ordina unit test

In alcuni casi può essere necessario eseguire unit test in un ordine specifico. Idealmente, l'ordine in cui vengono eseguiti gli unit test _non_ è rilevante ed è [consigliabile evitare di ordinare](unit-testing-best-practices.md) unit test. A prescindere, potrebbe essere necessario eseguire questa operazione. In tal caso, in questo articolo viene illustrato come ordinare le esecuzioni di test.

Se si preferisce esplorare il codice sorgente, vedere il repository di esempio [per gli unit test di .NET Core](/samples/dotnet/samples/order-unit-tests-cs) .

> [!TIP]
> Oltre alle funzionalità di ordinamento descritte in questo articolo, è consigliabile [creare playlist personalizzate con Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) come alternativa.

:::zone pivot="mstest"

## <a name="order-alphabetically"></a>Ordina alfabeticamente

Con MSTest, i test vengono ordinati automaticamente in base al nome del test.

> [!NOTE]
> Un test denominato `Test14` verrà eseguito prima `Test2` anche se il numero `2` è minore di `14` . Questo è dovuto al fatto che l'ordinamento del nome del test usa il nome di testo del test.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

Il Framework di test di xUnit consente una maggiore granularità e il controllo dell'ordine di esecuzione dei test. Implementare le `ITestCaseOrderer` interfacce e `ITestCollectionOrderer` per controllare l'ordine dei test case per una classe o per le raccolte di test.

## <a name="order-by-test-case-alphabetically"></a>Ordina per test case alfabeticamente

Per ordinare i test case in base al nome del metodo, implementare `ITestCaseOrderer` e fornire un meccanismo di ordinamento.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

Quindi, in una classe di test, impostare l'ordine di test case con `TestCaseOrdererAttribute` .

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a>Ordina per raccolta alfabeticamente

Per ordinare le raccolte di test in base al nome visualizzato, è necessario implementare `ITestCollectionOrderer` e fornire un meccanismo di ordinamento.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

Poiché le raccolte di test vengono potenzialmente eseguite in parallelo, è necessario disabilitare in modo esplicito la parallelizzazione dei test delle raccolte con `CollectionBehaviorAttribute` . Specificare quindi l'implementazione di `TestCollectionOrdererAttribute` .

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a>Ordina per attributo personalizzato

Per ordinare i test di xUnit con attributi personalizzati, è necessario prima di tutto un attributo da utilizzare. Definire un `TestPriorityAttribute` come indicato di seguito:

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

Si consideri quindi la seguente `PriorityOrderer` implementazione dell' `ITestCaseOrderer` interfaccia.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

Quindi, in una classe di test, impostare il test case ordine con la classe `TestCaseOrdererAttribute` su `PriorityOrderer` .

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a>Ordina per priorità

Per ordinare i test in modo esplicito, NUnit fornisce un [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute) . I test con questo attributo vengono avviati prima dei test senza. Il valore Order viene usato per determinare l'ordine di esecuzione degli unit test.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a>Passaggi successivi

> [!div class="nextstepaction"]
> [Procedure consigliate per gli unit test](unit-testing-best-practices.md)
