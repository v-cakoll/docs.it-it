---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sulle librerie pubblicate, invece che sul codice sorgente, con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: 7618d37782de3a16f1963380bbb56945fb73e8eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714259"
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
> Nota: se l'app `netcoreapp`è destinata a `dotnet vstest` un framework diverso da , è comunque possibile eseguire il comando passando il framework di destinazione con un flag del framework. Ad esempio: `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`. In Visual Studio 2017 Update 5 e versioni successive, viene rilevato automaticamente il framework desiderato.

## <a name="see-also"></a>Vedere anche

- [Unit test con dotnet test e xUnit](unit-testing-with-dotnet-test.md)
- [Unit test con test dotnet e NUnit](unit-testing-with-nunit.md)
- [Unit test con dotnet test e MSTest](unit-testing-with-mstest.md)
