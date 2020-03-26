---
title: comando dotnet nuget update source (comando)
description: Il comando dotnet nuget update source aggiorna un'origine esistente nei file di configurazione NuGet.The dotnet nuget update source command updates an existing source in your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: 38335e07f91850756c7671413e1193c2578e7e7e
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148547"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive

## <a name="name"></a>Nome

`dotnet nuget update source`- Aggiornare un'origine NuGet.- Update a NuGet source.

## <a name="synopsis"></a>Riepilogo

```dotnetcli
dotnet nuget update source <NAME> [--source] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget update source [-h|--help]
```

## <a name="description"></a>Descrizione

Il `dotnet nuget update source` comando aggiorna un'origine esistente nei file di configurazione Di NuGet.The command updates an existing source in your NuGet configuration files.

## <a name="arguments"></a>Argomenti

- **`NAME`**

  Nome dell'origine.

## <a name="options"></a>Opzioni

- **`--configfile`**

  Il file di configurazione NuGet. Se specificato, verranno utilizzate solo le impostazioni di questo file. Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente. Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`-p|--password`**

  Password da utilizzare per la connessione a un'origine autenticata.

- **`-s|--source`**

  Percorso dell'origine del pacchetto.

- **`--store-password-in-clear-text`**

  Consente di archiviare le credenziali di origine del pacchetto portabile disabilitando la crittografia della password.

- **`-u|--username`**

  Nome utente da utilizzare per la connessione a un'origine autenticata.

- **`--valid-authentication-types`**

  Elenco delimitato da virgole di tipi di autenticazione validi per questa origine. Impostare `basic` questa opzione su se il server annuncia NTLM o Negotiate e le credenziali devono essere inviate usando il meccanismo di base, ad esempio quando si usa un PAT con il server DevOps di Azure locale. Altri valori `negotiate`validi `kerberos` `ntlm`includono `digest`, , e , ma è improbabile che questi valori siano utili.

## <a name="examples"></a>Esempi

- Aggiornare un'origine `mySource`con il nome di :

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>Vedere anche

- [Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files](/nuget/reference/nuget-config-file#package-source-sections)

- [comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
