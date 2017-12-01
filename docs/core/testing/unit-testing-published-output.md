---
title: Eseguire il test pubblicati di output con vstest dotnet
description: Informazioni su come eseguire test su output pubblicato con il comando di vstest dotnet.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a>Eseguire il test pubblicati di output con vstest dotnet

È possibile eseguire test nell'output già pubblicato tramite il `dotnet vstest` comando. Questa impostazione funziona su xUnit, MSTest e NUnit test. È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:
```
dotnet vstest <MyPublishedTests>.dll
```
dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.

### <a name="example-of-running-tests-on-a-published-dll"></a>Esempio di esecuzione di test in una DLL pubblicata

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] Nota: Se l'app è destinato a un framework diverso da `netcoreapp` è comunque possibile eseguire il `dotnet vstest` comando passando il framework di destinazione con un flag di framework. Ad esempio `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 aggiornamento 5 viene rilevato automaticamente il framework desiderato.

### <a name="related-topics"></a>Argomenti correlati
- [Unit test con test dotnet e xUnit](unit-testing-with-dotnet-test.md)
- [Unit test con test dotnet e MSTest](unit-testing-with-mstest.md)
