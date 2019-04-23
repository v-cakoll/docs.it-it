---
title: Comando dotnet nuget delete
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: a657fa273ca6b5229a1713fbcaf003217a59fd7f
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612628"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="d5013-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="d5013-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d5013-104">nome</span><span class="sxs-lookup"><span data-stu-id="d5013-104">Name</span></span>

<span data-ttu-id="d5013-105">`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="d5013-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d5013-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d5013-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d5013-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d5013-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d5013-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d5013-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="d5013-109">Description</span><span class="sxs-lookup"><span data-stu-id="d5013-109">Description</span></span>

<span data-ttu-id="d5013-110">Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="d5013-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="d5013-111">Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="d5013-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="d5013-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d5013-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="d5013-113">Nome/ID del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="d5013-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="d5013-114">Versione del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="d5013-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="d5013-115">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d5013-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d5013-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d5013-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="d5013-117">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="d5013-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="d5013-118">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d5013-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="d5013-119">Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="d5013-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="d5013-120">Opzione disponibile a partire da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="d5013-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="d5013-121">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="d5013-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="d5013-122">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="d5013-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="d5013-123">Opzione disponibile a partire da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="d5013-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="d5013-124">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d5013-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="d5013-125">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="d5013-125">Specifies the server URL.</span></span> <span data-ttu-id="d5013-126">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="d5013-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="d5013-127">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="d5013-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d5013-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d5013-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="d5013-129">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="d5013-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="d5013-130">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d5013-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="d5013-131">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="d5013-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="d5013-132">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d5013-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="d5013-133">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="d5013-133">Specifies the server URL.</span></span> <span data-ttu-id="d5013-134">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="d5013-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="d5013-135">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="d5013-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="d5013-136">Esempi</span><span class="sxs-lookup"><span data-stu-id="d5013-136">Examples</span></span>

* <span data-ttu-id="d5013-137">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="d5013-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="d5013-138">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:</span><span class="sxs-lookup"><span data-stu-id="d5013-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```