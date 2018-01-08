---
title: Comando dotnet nuget delete - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-nuget-delete rimuove dall'elenco o elimina un pacchetto dal server.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 3c09556fe90a5c447b181bc1ac5b36f014399e4f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.

## <a name="synopsis"></a>Riepilogo

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>Descrizione

Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server. Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.

## <a name="arguments"></a>Argomenti

`PACKAGE_NAME`

Pacchetto da eliminare.

`PACKAGE_VERSION`

Versione del pacchetto da eliminare.

## <a name="options"></a>Opzioni

`-h|--help`

Stampa una breve guida per il comando.

`-s|--source <SOURCE>`

Specifica l'URL del server. Gli URL supportati per nuget.org includono `http://www.nuget.org`, `http://www.nuget.org/api/v3` e `http://www.nuget.org/api/v2/package`. Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).

`--non-interactive`

Non richiede input o conferme dell'utente.

`-k|--api-key <API_KEY>`

Chiave API per il server.

`--force-english-output`

Forza la visualizzazione dell'output della riga di comando in inglese.

## <a name="examples"></a>Esempi

Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`