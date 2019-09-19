---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sulle librerie pubblicate, invece che sul codice sorgente, con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 93b2e1a433b5d5b9694257d4d12e47d9107f4cd7
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117033"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="ee753-103">Testare l'output pubblicato con dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="ee753-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="ee753-104">È possibile eseguire test sull'output già pubblicato usando il comando `dotnet vstest`,</span><span class="sxs-lookup"><span data-stu-id="ee753-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="ee753-105">che funzionerà per i test xUnit, MSTest e NUnit.</span><span class="sxs-lookup"><span data-stu-id="ee753-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="ee753-106">È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="ee753-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="ee753-107">Dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.</span><span class="sxs-lookup"><span data-stu-id="ee753-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="ee753-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee753-108">Example</span></span>

<span data-ttu-id="ee753-109">I comandi seguenti illustrano l'esecuzione dei test in una DLL pubblicata.</span><span class="sxs-lookup"><span data-stu-id="ee753-109">The commands below demonstrate running tests on a published DLL.</span></span>

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="ee753-110">Nota: se l'app specifica come destinazione un framework diverso da `netcoreapp`, è possibile eseguire il comando `dotnet vstest` passando il framework di destinazione con un flag framework.</span><span class="sxs-lookup"><span data-stu-id="ee753-110">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="ee753-111">Ad esempio `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="ee753-111">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="ee753-112">In Visual Studio 2017 Update 5 il framework desiderato viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ee753-112">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee753-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee753-113">See also</span></span>

- [<span data-ttu-id="ee753-114">Unit test con test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="ee753-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="ee753-115">Unit test con test dotnet e NUnit</span><span class="sxs-lookup"><span data-stu-id="ee753-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="ee753-116">Unit test con test dotnet e MSTest</span><span class="sxs-lookup"><span data-stu-id="ee753-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
