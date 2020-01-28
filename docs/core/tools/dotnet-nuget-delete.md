---
title: Comando dotnet nuget delete
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 0950f03c0986bde17ae3e2e7170d402ea8222853
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733127"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="abbca-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="abbca-103">dotnet nuget delete</span></span>

<span data-ttu-id="abbca-104">**Questo articolo si applica a:** ✔️ .NET Core 1. x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="abbca-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="abbca-105">Name</span><span class="sxs-lookup"><span data-stu-id="abbca-105">Name</span></span>

<span data-ttu-id="abbca-106">`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="abbca-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="abbca-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="abbca-107">Synopsis</span></span>

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

## <a name="description"></a><span data-ttu-id="abbca-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="abbca-108">Description</span></span>

<span data-ttu-id="abbca-109">Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="abbca-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="abbca-110">Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="abbca-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="abbca-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="abbca-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="abbca-112">Nome/ID del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="abbca-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="abbca-113">Versione del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="abbca-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="abbca-114">Options</span><span class="sxs-lookup"><span data-stu-id="abbca-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="abbca-115">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="abbca-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="abbca-116">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="abbca-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="abbca-117">Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="abbca-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="abbca-118">Opzione disponibile a partire da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="abbca-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="abbca-119">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="abbca-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="abbca-120">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="abbca-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="abbca-121">Opzione disponibile a partire da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="abbca-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="abbca-122">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="abbca-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="abbca-123">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="abbca-123">Specifies the server URL.</span></span> <span data-ttu-id="abbca-124">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="abbca-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="abbca-125">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="abbca-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="abbca-126">Esempi</span><span class="sxs-lookup"><span data-stu-id="abbca-126">Examples</span></span>

* <span data-ttu-id="abbca-127">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="abbca-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="abbca-128">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:</span><span class="sxs-lookup"><span data-stu-id="abbca-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
