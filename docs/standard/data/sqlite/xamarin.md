---
title: Limitazioni di Novell
ms.date: 12/13/2019
description: Descrive alcune delle limitazioni che si verificheranno quando si usa Novell.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75447167"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="e1b50-103">Limitazioni di Novell</span><span class="sxs-lookup"><span data-stu-id="e1b50-103">Xamarin limitations</span></span>

<span data-ttu-id="e1b50-104">Microsoft. Data. SQLite è destinato .NET Standard 2,0 ed è supportato in Novell.</span><span class="sxs-lookup"><span data-stu-id="e1b50-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="e1b50-105">La tabella seguente illustra le piattaforme per cui il bundle SQLitePCLRaw predefinito fornisce file binari SQLite nativi.</span><span class="sxs-lookup"><span data-stu-id="e1b50-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="e1b50-106">Vedere [versioni personalizzate di SQLite](custom-versions.md) per informazioni dettagliate sull'uso di un bundle diverso o per fornire file binari SQLite nativi.</span><span class="sxs-lookup"><span data-stu-id="e1b50-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="e1b50-107">Piattaforma</span><span class="sxs-lookup"><span data-stu-id="e1b50-107">Platform</span></span> | <span data-ttu-id="e1b50-108">File binari SQLite</span><span class="sxs-lookup"><span data-stu-id="e1b50-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="e1b50-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="e1b50-109">**Xamarin.Android**</span></span> | <span data-ttu-id="e1b50-110">—</span><span class="sxs-lookup"><span data-stu-id="e1b50-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="e1b50-111">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="e1b50-112">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="e1b50-113">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="e1b50-114">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-114">✔</span></span> |
| <span data-ttu-id="e1b50-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="e1b50-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="e1b50-116">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-116">✔</span></span> |
| <span data-ttu-id="e1b50-117">**Novell. Mac**</span><span class="sxs-lookup"><span data-stu-id="e1b50-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="e1b50-118">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-118">✔</span></span> |
| <span data-ttu-id="e1b50-119">**Novell. TVOS**</span><span class="sxs-lookup"><span data-stu-id="e1b50-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="e1b50-120">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-120">✔</span></span> |
| <span data-ttu-id="e1b50-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="e1b50-121">**UWP**</span></span> | <span data-ttu-id="e1b50-122">—</span><span class="sxs-lookup"><span data-stu-id="e1b50-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="e1b50-123">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="e1b50-124">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="e1b50-125">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="e1b50-126">✔</span><span class="sxs-lookup"><span data-stu-id="e1b50-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="e1b50-127">iOS</span><span class="sxs-lookup"><span data-stu-id="e1b50-127">iOS</span></span>

<span data-ttu-id="e1b50-128">Microsoft. Data. sqlite tenta di inizializzare automaticamente i bundle SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="e1b50-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="e1b50-129">Sfortunatamente, a causa delle limitazioni della compilazione AOT (Ahead of Time) per Novell. iOS, il tentativo ha esito negativo e viene ricevuto l'errore seguente.</span><span class="sxs-lookup"><span data-stu-id="e1b50-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="e1b50-130">È necessario chiamare `SQLitePCL.raw.SetProvider()`.</span><span class="sxs-lookup"><span data-stu-id="e1b50-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="e1b50-131">Se si usa un pacchetto di bundle, questa operazione viene eseguita chiamando `SQLitePCL.Batteries.Init()`.</span><span class="sxs-lookup"><span data-stu-id="e1b50-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="e1b50-132">Per inizializzare il bundle, aggiungere la seguente riga di codice all'app prima di usare Microsoft. Data. sqlite.</span><span class="sxs-lookup"><span data-stu-id="e1b50-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="e1b50-133">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="e1b50-133">See also</span></span>

* [<span data-ttu-id="e1b50-134">Limitazioni asincrone</span><span class="sxs-lookup"><span data-stu-id="e1b50-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="e1b50-135">Versioni di SQLite personalizzate</span><span class="sxs-lookup"><span data-stu-id="e1b50-135">Custom SQLite versions</span></span>](custom-versions.md)
