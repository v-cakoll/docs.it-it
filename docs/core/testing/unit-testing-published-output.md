---
title: Testare l'output pubblicato con dotnet vstest
description: Informazioni su come eseguire test sulle librerie pubblicate, invece che sul codice sorgente, con il comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: 7618d37782de3a16f1963380bbb56945fb73e8eb
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714259"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="fa9b3-103">Testare l'output pubblicato con dotnet vstest</span><span class="sxs-lookup"><span data-stu-id="fa9b3-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="fa9b3-104">È possibile eseguire test sull'output già pubblicato usando il comando `dotnet vstest`,</span><span class="sxs-lookup"><span data-stu-id="fa9b3-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="fa9b3-105">che funzionerà per i test xUnit, MSTest e NUnit.</span><span class="sxs-lookup"><span data-stu-id="fa9b3-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="fa9b3-106">È sufficiente individuare il file DLL che faceva parte dell'output pubblicato ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="fa9b3-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```dotnetcli
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="fa9b3-107">Dove `<MyPublishedTests>` è il nome del progetto di test pubblicato.</span><span class="sxs-lookup"><span data-stu-id="fa9b3-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="fa9b3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa9b3-108">Example</span></span>

<span data-ttu-id="fa9b3-109">I comandi seguenti illustrano l'esecuzione dei test in una DLL pubblicata.</span><span class="sxs-lookup"><span data-stu-id="fa9b3-109">The commands below demonstrate running tests on a published DLL.</span></span>

```dotnetcli
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="fa9b3-110">Nota: se l'app è destinata a un Framework diverso da `netcoreapp`, è comunque possibile eseguire il comando `dotnet vstest` passando il Framework di destinazione con un flag di Framework.</span><span class="sxs-lookup"><span data-stu-id="fa9b3-110">Note: If your app targets a framework other than `netcoreapp`, you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="fa9b3-111">Ad esempio `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="fa9b3-111">For example, `dotnet vstest <MyPublishedTests>.dll --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="fa9b3-112">In Visual Studio 2017 Update 5 e versioni successive il framework desiderato viene rilevato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="fa9b3-112">In Visual Studio 2017 Update 5 and later, the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="fa9b3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa9b3-113">See also</span></span>

- [<span data-ttu-id="fa9b3-114">Unit test con test dotnet e xUnit</span><span class="sxs-lookup"><span data-stu-id="fa9b3-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="fa9b3-115">Unit test con test dotnet e NUnit</span><span class="sxs-lookup"><span data-stu-id="fa9b3-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="fa9b3-116">Unit test con test dotnet e MSTest</span><span class="sxs-lookup"><span data-stu-id="fa9b3-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
