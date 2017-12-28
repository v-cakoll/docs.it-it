---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sull'output pubblicato con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 6651d41d4d60194aec035107e3a65df6a5f70a51
ms.sourcegitcommit: 4a96a0fe9f87de70291245d71b76c7d1b15127ae
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a>Testare l'output pubblicato con dotnet vstest

È possibile eseguire test sull'output già pubblicato usando il comando `dotnet vstest`, che funzionerà per i test xUnit, MSTest e NUnit. È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:

```
dotnet vstest <MyPublishedTests>.dll
```

dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.

## <a name="example-of-running-tests-on-a-published-dll"></a>Esempio di esecuzione di test in una DLL pubblicata

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Nota: se l'app specifica come destinazione un framework diverso da `netcoreapp`, è possibile eseguire il comando `dotnet vstest` passando il framework di destinazione con un flag framework. Ad esempio `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 il framework desiderato viene rilevato automaticamente.

## <a name="see-also"></a>Vedere anche
 [Unit test con test dotnet e xUnit](unit-testing-with-dotnet-test.md)  
 [Unit test con test dotnet e MSTest](unit-testing-with-mstest.md)  
