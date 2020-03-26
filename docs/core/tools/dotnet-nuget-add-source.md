---
title: comando dotnet nuget aggiungere il comando source
description: Il comando dotnet nuget add source aggiunge una nuova origine del pacchetto ai file di configurazione NuGet.The dotnet nuget add source command adds a new package source to your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: c1e398699c7482a69b750cde718e6f9178b5c4bd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148568"
---
# <a name="dotnet-nuget-add-source"></a><span data-ttu-id="a3ad4-103">dotnet nuget add source</span><span class="sxs-lookup"><span data-stu-id="a3ad4-103">dotnet nuget add source</span></span>

<span data-ttu-id="a3ad4-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="a3ad4-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="a3ad4-105">Nome</span><span class="sxs-lookup"><span data-stu-id="a3ad4-105">Name</span></span>

<span data-ttu-id="a3ad4-106">`dotnet nuget add source`- Aggiungere un'origine NuGet.- Add a NuGet source.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-106">`dotnet nuget add source` - Add a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a3ad4-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a3ad4-107">Synopsis</span></span>

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name] [--username]
    [--password] [--store-password-in-clear-text] [--valid-authentication-types]
    [--configfile]
dotnet nuget add source [-h|--help]
```

## <a name="description"></a><span data-ttu-id="a3ad4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a3ad4-108">Description</span></span>

<span data-ttu-id="a3ad4-109">Il `dotnet nuget add source` comando aggiunge una nuova origine del pacchetto ai file di configurazione NuGet.The command adds a new package source to your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-109">The `dotnet nuget add source` command adds a new package source to your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="a3ad4-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a3ad4-110">Arguments</span></span>

- **`PACKAGE_SOURCE_PATH`**

  <span data-ttu-id="a3ad4-111">Percorso dell'origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-111">Path to the package source.</span></span>

## <a name="options"></a><span data-ttu-id="a3ad4-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a3ad4-112">Options</span></span>

- **`--configfile`**

  <span data-ttu-id="a3ad4-113">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-113">The NuGet configuration file.</span></span> <span data-ttu-id="a3ad4-114">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="a3ad4-115">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="a3ad4-116">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="a3ad4-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-n|--name`**

  <span data-ttu-id="a3ad4-117">Nome dell'origine.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-117">Name of the source.</span></span>

- **`-p|--password`**

  <span data-ttu-id="a3ad4-118">Password da utilizzare per la connessione a un'origine autenticata.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-118">Password to be used when connecting to an authenticated source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="a3ad4-119">Consente di archiviare le credenziali di origine del pacchetto portabile disabilitando la crittografia della password.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username`**

  <span data-ttu-id="a3ad4-120">Nome utente da utilizzare per la connessione a un'origine autenticata.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types`**

  <span data-ttu-id="a3ad4-121">Elenco delimitato da virgole di tipi di autenticazione validi per questa origine.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="a3ad4-122">Impostare `basic` questa opzione su se il server annuncia NTLM o Negotiate e le credenziali devono essere inviate usando il meccanismo di base, ad esempio quando si usa un PAT con il server DevOps di Azure locale.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="a3ad4-123">Altri valori `negotiate`validi `kerberos` `ntlm`includono `digest`, , e , ma è improbabile che questi valori siano utili.</span><span class="sxs-lookup"><span data-stu-id="a3ad4-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="a3ad4-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="a3ad4-124">Examples</span></span>

- <span data-ttu-id="a3ad4-125">Aggiungi `nuget.org` come origine:</span><span class="sxs-lookup"><span data-stu-id="a3ad4-125">Add `nuget.org` as a source:</span></span>

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- <span data-ttu-id="a3ad4-126">Aggiungi `c:\packages` come origine locale:</span><span class="sxs-lookup"><span data-stu-id="a3ad4-126">Add `c:\packages` as a local source:</span></span>

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- <span data-ttu-id="a3ad4-127">Aggiungere un'origine che richiede l'autenticazione:Add a source that needs authentication:</span><span class="sxs-lookup"><span data-stu-id="a3ad4-127">Add a source that needs authentication:</span></span>

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- <span data-ttu-id="a3ad4-128">Aggiungere un'origine che richiede l'autenticazione (quindi installare il provider di credenziali:Add a source that needs authentication (then go install credential provider):</span><span class="sxs-lookup"><span data-stu-id="a3ad4-128">Add a source that needs authentication (then go install credential provider):</span></span>

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a><span data-ttu-id="a3ad4-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a3ad4-129">See also</span></span>

- [<span data-ttu-id="a3ad4-130">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="a3ad4-130">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="a3ad4-131">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="a3ad4-131">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
