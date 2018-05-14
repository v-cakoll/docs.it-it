---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sull'output pubblicato con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: dbce1b6e616916e60e56318b773e8fcecbc55580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
