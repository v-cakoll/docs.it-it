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
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nome

`dotnet nuget delete`: rimuove dall'elenco o elimina un pacchetto dal server.

## <a name="synopsis"></a>Riepilogo

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```

---

## <a name="description"></a>Description

Il comando `dotnet nuget delete` rimuove dall'elenco o elimina un pacchetto dal server. Per [nuget.org](https://www.nuget.org/) l'azione consiste nel rimuovere il pacchetto dall'elenco.

## <a name="arguments"></a>Argomenti

* **`PACKAGE_NAME`**

  Nome/ID del pacchetto da eliminare.

* **`PACKAGE_VERSION`**

  Versione del pacchetto da eliminare.

## <a name="options"></a>Opzioni

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

* **`--force-english-output`**

  Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`--interactive`**

  Consente al comando di bloccare operazioni quali l'autenticazione e richiede un intervento manuale. Opzione disponibile a partire da .NET Core 2.2 SDK.

* **`-k|--api-key <API_KEY>`**

  Chiave API per il server.

* **`--no-service-endpoint`**

  Non aggiunge "api/v2/package" all'URL di origine. Opzione disponibile a partire da .NET Core 2.1 SDK.

* **`--non-interactive`**

  Non richiede input o conferme dell'utente.

* **`-s|--source <SOURCE>`**

  Specifica l'URL del server. Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`. Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

* **`--force-english-output`**

  Impone all'applicazione l'esecuzione con una cultura invariante e di lingua inglese.

* **`-h|--help`**

  Stampa una breve guida per il comando.

* **`-k|--api-key <API_KEY>`**

  Chiave API per il server.

* **`--non-interactive`**

  Non richiede input o conferme dell'utente.

* **`-s|--source <SOURCE>`**

  Specifica l'URL del server. Gli URL supportati per nuget.org includono `https://www.nuget.org`, `https://www.nuget.org/api/v3` e `https://www.nuget.org/api/v2/package`. Per i feed privati, sostituire il nome host (ad esempio, `%hostname%/api/v3`).

---

## <a name="examples"></a>Esempi

* Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc`:

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* Elimina la versione 1.0 del pacchetto `Microsoft.AspNetCore.Mvc` senza richiedere all'utente credenziali o altro input:

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```