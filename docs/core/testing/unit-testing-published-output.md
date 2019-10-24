---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sulle librerie pubblicate, invece che sul codice sorgente, con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: e4fd25dc9ff30bdfe85cd1167a1dc41ea20a5f80
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771930"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Testare l'output pubblicato con dotnet vstest

È possibile eseguire test sull'output già pubblicato usando il comando `dotnet vstest`, che funzionerà per i test xUnit, MSTest e NUnit. È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

Dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.

## <a name="example"></a>Esempio

I comandi seguenti illustrano l'esecuzione dei test in una DLL pubblicata.

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Nota: se l'app è destinata a un Framework diverso da `netcoreapp`, è comunque possibile eseguire il comando `dotnet vstest` passando il Framework di destinazione con un flag di Framework. Ad esempio `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 e versioni successive il framework desiderato viene rilevato automaticamente.

## <a name="see-also"></a>Vedere anche

- [Unit test con test dotnet e xUnit](unit-testing-with-dotnet-test.md)
- [Unit test con test dotnet e NUnit](unit-testing-with-nunit.md)
- [Unit test con test dotnet e MSTest](unit-testing-with-mstest.md)
