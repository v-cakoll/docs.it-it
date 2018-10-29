---
title: Comando dotnet nuget delete - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: f4aa027a465c4adea1de13853063d03e8e295411
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180880"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="59a2d-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="59a2d-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="59a2d-104">nome</span><span class="sxs-lookup"><span data-stu-id="59a2d-104">Name</span></span>

<span data-ttu-id="59a2d-105">`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="59a2d-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="59a2d-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="59a2d-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="59a2d-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="59a2d-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="59a2d-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="59a2d-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="59a2d-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="59a2d-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="59a2d-110">Description</span></span>

<span data-ttu-id="59a2d-111">Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-111">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="59a2d-112">Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="59a2d-112">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="59a2d-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="59a2d-113">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="59a2d-114">Nome/ID del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="59a2d-114">Name/ID of the package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="59a2d-115">Versione del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="59a2d-115">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="59a2d-116">Opzioni</span><span class="sxs-lookup"><span data-stu-id="59a2d-116">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="59a2d-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="59a2d-117">.NET Core 2.1</span></span>](#tab/netcore21)

`--force-english-output`

 <span data-ttu-id="59a2d-118">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="59a2d-118">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="59a2d-119">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="59a2d-119">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="59a2d-120">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-120">The API key for the server.</span></span>

<span data-ttu-id="59a2d-121">`--no-service-endpoint` Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="59a2d-121">`--no-service-endpoint` Doesn't append "api/v2/package" to the source URL.</span></span>

`--non-interactive`

<span data-ttu-id="59a2d-122">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59a2d-122">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="59a2d-123">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-123">Specifies the server URL.</span></span> <span data-ttu-id="59a2d-124">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="59a2d-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="59a2d-125">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="59a2d-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="59a2d-126">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="59a2d-126">.NET Core 2.0</span></span>](#tab/netcore20)

`--force-english-output`

 <span data-ttu-id="59a2d-127">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="59a2d-127">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="59a2d-128">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="59a2d-128">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="59a2d-129">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-129">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="59a2d-130">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59a2d-130">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="59a2d-131">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-131">Specifies the server URL.</span></span> <span data-ttu-id="59a2d-132">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="59a2d-132">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="59a2d-133">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="59a2d-133">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="59a2d-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="59a2d-134">.NET Core 1.x</span></span>](#tab/netcore1x)

`--force-english-output`

 <span data-ttu-id="59a2d-135">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="59a2d-135">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="59a2d-136">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="59a2d-136">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="59a2d-137">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-137">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="59a2d-138">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="59a2d-138">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="59a2d-139">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="59a2d-139">Specifies the server URL.</span></span> <span data-ttu-id="59a2d-140">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="59a2d-140">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="59a2d-141">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="59a2d-141">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="59a2d-142">Esempi</span><span class="sxs-lookup"><span data-stu-id="59a2d-142">Examples</span></span>

<span data-ttu-id="59a2d-143">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="59a2d-143">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

<span data-ttu-id="59a2d-144">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:</span><span class="sxs-lookup"><span data-stu-id="59a2d-144">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
