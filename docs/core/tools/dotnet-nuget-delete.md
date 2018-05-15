---
title: Comando dotnet nuget delete - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.openlocfilehash: 639ade54bfed5eb2de89bdb3b7f451393b4be187
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="30ac5-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="30ac5-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="30ac5-104">nome</span><span class="sxs-lookup"><span data-stu-id="30ac5-104">Name</span></span>

<span data-ttu-id="30ac5-105">`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="30ac5-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="30ac5-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="30ac5-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="30ac5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="30ac5-107">Description</span></span>

<span data-ttu-id="30ac5-108">Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server.</span><span class="sxs-lookup"><span data-stu-id="30ac5-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="30ac5-109">Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="30ac5-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="30ac5-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30ac5-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="30ac5-111">Pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="30ac5-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="30ac5-112">Versione del pacchetto da eliminare.</span><span class="sxs-lookup"><span data-stu-id="30ac5-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="30ac5-113">Opzioni</span><span class="sxs-lookup"><span data-stu-id="30ac5-113">Options</span></span>

`-h|--help`

<span data-ttu-id="30ac5-114">Stampa una breve guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="30ac5-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="30ac5-115">Specifica l'URL del server.</span><span class="sxs-lookup"><span data-stu-id="30ac5-115">Specifies the server URL.</span></span> <span data-ttu-id="30ac5-116">Gli URL supportati per nuget.org includono `http://www.nuget.org`, `http://www.nuget.org/api/v3` e `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="30ac5-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="30ac5-117">Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="30ac5-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="30ac5-118">Non richiede input o conferme dell'utente.</span><span class="sxs-lookup"><span data-stu-id="30ac5-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="30ac5-119">Chiave API per il server.</span><span class="sxs-lookup"><span data-stu-id="30ac5-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="30ac5-120">Forza la visualizzazione dell'output della riga di comando in inglese.</span><span class="sxs-lookup"><span data-stu-id="30ac5-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="30ac5-121">Esempi</span><span class="sxs-lookup"><span data-stu-id="30ac5-121">Examples</span></span>

<span data-ttu-id="30ac5-122">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="30ac5-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="30ac5-123">Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:</span><span class="sxs-lookup"><span data-stu-id="30ac5-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`