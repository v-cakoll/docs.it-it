---
title: Comando dotnet nuget delete
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 4fa4f24adba251d7872986de4a8b1a63203c36c3
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463589"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="a1b36-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="a1b36-103">dotnet nuget delete</span></span>

<span data-ttu-id="a1b36-104">**Questo articolo si applica a:** ✔️ .NET Core 1.x SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="a1b36-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="a1b36-105">Nome</span><span class="sxs-lookup"><span data-stu-id="a1b36-105">Name</span></span>

<span data-ttu-id="a1b36-106">`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="a1b36-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a1b36-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a1b36-107">Synopsis</span></span>

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [--no-service-endpoint]
    [--non-interactive] [-s|--source <SOURCE>]

dotnet nuget delete -h|--help
```

## <a name="description"></a><span data-ttu-id="a1b36-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a1b36-108">Description</span></span>

<span data-ttu-id="a1b36-109">Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="a1b36-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="a1b36-110">Per [nuget.org](https://www.nuget.org/), l'azione consiste nell'annullare l'elenco del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a1b36-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="a1b36-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a1b36-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="a1b36-112">Nome/ID del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="a1b36-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="a1b36-113">Versione del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="a1b36-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="a1b36-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a1b36-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="a1b36-115">Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.</span><span class="sxs-lookup"><span data-stu-id="a1b36-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="a1b36-116">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a1b36-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="a1b36-117">Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale.</span><span class="sxs-lookup"><span data-stu-id="a1b36-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="a1b36-118">Opzione disponibile a partire da .NET Core 2.2 SDK.</span><span class="sxs-lookup"><span data-stu-id="a1b36-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="a1b36-119">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="a1b36-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="a1b36-120">Non aggiunge "api/v2/package" all'URL di origine.</span><span class="sxs-lookup"><span data-stu-id="a1b36-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="a1b36-121">Opzione disponibile a partire da .NET Core 2.1 SDK.</span><span class="sxs-lookup"><span data-stu-id="a1b36-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="a1b36-122">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a1b36-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="a1b36-123">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="a1b36-123">Specifies the server URL.</span></span> <span data-ttu-id="a1b36-124">Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="a1b36-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="a1b36-125">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="a1b36-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="a1b36-126">Esempi</span><span class="sxs-lookup"><span data-stu-id="a1b36-126">Examples</span></span>

* <span data-ttu-id="a1b36-127">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="a1b36-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="a1b36-128">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:</span><span class="sxs-lookup"><span data-stu-id="a1b36-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
