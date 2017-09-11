---
title: Comando dotnet-nuget-delete - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
keywords: dotnet-nuget-delete, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: karann-msft
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ce6886f2f4cc8cc633cfc61215fe17550f746c91
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-nuget-delete"></a><span data-ttu-id="29b20-104">dotnet-nuget delete</span><span class="sxs-lookup"><span data-stu-id="29b20-104">dotnet-nuget delete</span></span>

## <a name="name"></a><span data-ttu-id="29b20-105">Nome</span><span class="sxs-lookup"><span data-stu-id="29b20-105">Name</span></span>

<span data-ttu-id="29b20-106">`dotnet-nuget-delete`: rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="29b20-106">`dotnet-nuget-delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="29b20-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="29b20-107">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="29b20-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="29b20-108">Description</span></span>

<span data-ttu-id="29b20-109">Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="29b20-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="29b20-110">Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="29b20-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="29b20-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="29b20-111">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="29b20-112">Pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="29b20-112">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="29b20-113">Versione del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="29b20-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="29b20-114">Opzioni</span><span class="sxs-lookup"><span data-stu-id="29b20-114">Options</span></span>

`-h|--help`

<span data-ttu-id="29b20-115">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="29b20-115">Prints out a short help for the command.</span></span>  

`-s|--source <SOURCE>`

<span data-ttu-id="29b20-116">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="29b20-116">Specifies the server URL.</span></span> <span data-ttu-id="29b20-117">Gli URL supportati per nuget.org includono `http://www.nuget.org`, `http://www.nuget.org/api/v3` e `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="29b20-117">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="29b20-118">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="29b20-118">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="29b20-119">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="29b20-119">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="29b20-120">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="29b20-120">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="29b20-121">Forza la visualizzazione dell'output della riga di comando in inglese.</span><span class="sxs-lookup"><span data-stu-id="29b20-121">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="29b20-122">Esempi</span><span class="sxs-lookup"><span data-stu-id="29b20-122">Examples</span></span>

<span data-ttu-id="29b20-123">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="29b20-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="29b20-124">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:</span><span class="sxs-lookup"><span data-stu-id="29b20-124">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`

