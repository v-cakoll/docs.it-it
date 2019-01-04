---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sulle librerie pubblicate, invece che sul codice sorgente, con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 9d842f26336d0ddf5375d49676523086bb632684
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239527"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Testare l'output pubblicato con dotnet vstest

È possibile eseguire test sull'output già pubblicato usando il comando `dotnet vstest`, che funzionerà per i test xUnit, MSTest e NUnit. È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:

```
dotnet vstest <MyPublishedTests>.dll
```

Dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.

## <a name="example"></a>Esempio

I comandi seguenti illustrano l'esecuzione dei test in una DLL pubblicata.

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Nota: se l'app specifica come destinazione un framework diverso da `netcoreapp`, è possibile eseguire il comando `dotnet vstest` passando il framework di destinazione con un flag framework. Ad esempio `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 il framework desiderato viene rilevato automaticamente.

## <a name="see-also"></a>Vedere anche
- [Unit test con test dotnet e xUnit](unit-testing-with-dotnet-test.md)
- [Unit test con test dotnet e NUnit](unit-testing-with-nunit.md)
- [Unit test con test dotnet e MSTest](unit-testing-with-mstest.md)
