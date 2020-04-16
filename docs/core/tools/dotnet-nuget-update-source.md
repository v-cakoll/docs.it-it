---
title: comando dotnet nuget update source (comando)
description: Il comando dotnet nuget update source aggiorna un'origine esistente nei file di configurazione NuGet.The dotnet nuget update source command updates an existing source in your NuGet configuration files.
ms.date: 03/20/2020
ms.openlocfilehash: 42b1aec95cdd57e53f966400f6692a3d0150c16c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463482"
---
# <a name="dotnet-nuget-update-source"></a><span data-ttu-id="ac1de-103">dotnet nuget update source</span><span class="sxs-lookup"><span data-stu-id="ac1de-103">dotnet nuget update source</span></span>

<span data-ttu-id="ac1de-104">**Questo articolo si applica a:** ✔️ .NET Core 3.1.200 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="ac1de-104">**This article applies to:** ✔️ .NET Core 3.1.200 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ac1de-105">Nome</span><span class="sxs-lookup"><span data-stu-id="ac1de-105">Name</span></span>

<span data-ttu-id="ac1de-106">`dotnet nuget update source`- Aggiornare un'origine NuGet.- Update a NuGet source.</span><span class="sxs-lookup"><span data-stu-id="ac1de-106">`dotnet nuget update source` - Update a NuGet source.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ac1de-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="ac1de-107">Synopsis</span></span>

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a><span data-ttu-id="ac1de-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac1de-108">Description</span></span>

<span data-ttu-id="ac1de-109">Il `dotnet nuget update source` comando aggiorna un'origine esistente nei file di configurazione Di NuGet.The command updates an existing source in your NuGet configuration files.</span><span class="sxs-lookup"><span data-stu-id="ac1de-109">The `dotnet nuget update source` command updates an existing source in your NuGet configuration files.</span></span>

## <a name="arguments"></a><span data-ttu-id="ac1de-110">Argomenti</span><span class="sxs-lookup"><span data-stu-id="ac1de-110">Arguments</span></span>

- **`NAME`**

  <span data-ttu-id="ac1de-111">Nome dell'origine.</span><span class="sxs-lookup"><span data-stu-id="ac1de-111">Name of the source.</span></span>

## <a name="options"></a><span data-ttu-id="ac1de-112">Opzioni</span><span class="sxs-lookup"><span data-stu-id="ac1de-112">Options</span></span>

- **`--configfile <FILE>`**

  <span data-ttu-id="ac1de-113">Il file di configurazione NuGet.</span><span class="sxs-lookup"><span data-stu-id="ac1de-113">The NuGet configuration file.</span></span> <span data-ttu-id="ac1de-114">Se specificato, verranno utilizzate solo le impostazioni di questo file.</span><span class="sxs-lookup"><span data-stu-id="ac1de-114">If specified, only the settings from this file will be used.</span></span> <span data-ttu-id="ac1de-115">Se non specificato, verrà utilizzata la gerarchia dei file di configurazione dalla directory corrente.</span><span class="sxs-lookup"><span data-stu-id="ac1de-115">If not specified, the hierarchy of configuration files from the current directory will be used.</span></span> <span data-ttu-id="ac1de-116">Per ulteriori informazioni, vedere [Configurazioni comuni NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span><span class="sxs-lookup"><span data-stu-id="ac1de-116">For more information, see [Common NuGet Configurations](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).</span></span>

- **`-p|--password <PASSWORD>`**

  <span data-ttu-id="ac1de-117">Password da utilizzare per la connessione a un'origine autenticata.</span><span class="sxs-lookup"><span data-stu-id="ac1de-117">Password to be used when connecting to an authenticated source.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="ac1de-118">Percorso dell'origine del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ac1de-118">Path to the package source.</span></span>

- **`--store-password-in-clear-text`**

  <span data-ttu-id="ac1de-119">Consente di archiviare le credenziali di origine del pacchetto portabile disabilitando la crittografia della password.</span><span class="sxs-lookup"><span data-stu-id="ac1de-119">Enables storing portable package source credentials by disabling password encryption.</span></span>

- **`-u|--username <USER>`**

  <span data-ttu-id="ac1de-120">Nome utente da utilizzare per la connessione a un'origine autenticata.</span><span class="sxs-lookup"><span data-stu-id="ac1de-120">Username to be used when connecting to an authenticated source.</span></span>

- **`--valid-authentication-types <TYPES>`**

  <span data-ttu-id="ac1de-121">Elenco delimitato da virgole di tipi di autenticazione validi per questa origine.</span><span class="sxs-lookup"><span data-stu-id="ac1de-121">Comma-separated list of valid authentication types for this source.</span></span> <span data-ttu-id="ac1de-122">Impostare `basic` questa opzione su se il server annuncia NTLM o Negotiate e le credenziali devono essere inviate usando il meccanismo di base, ad esempio quando si usa un PAT con il server DevOps di Azure locale.</span><span class="sxs-lookup"><span data-stu-id="ac1de-122">Set this to `basic` if the server advertises NTLM or Negotiate and your credentials must be sent using the Basic mechanism, for instance when using a PAT with on-premises Azure DevOps Server.</span></span> <span data-ttu-id="ac1de-123">Altri valori `negotiate`validi `kerberos` `ntlm`includono `digest`, , e , ma è improbabile che questi valori siano utili.</span><span class="sxs-lookup"><span data-stu-id="ac1de-123">Other valid values include `negotiate`, `kerberos`, `ntlm`, and `digest`, but these values are unlikely to be useful.</span></span>

## <a name="examples"></a><span data-ttu-id="ac1de-124">Esempi</span><span class="sxs-lookup"><span data-stu-id="ac1de-124">Examples</span></span>

- <span data-ttu-id="ac1de-125">Aggiornare un'origine `mySource`con il nome di :</span><span class="sxs-lookup"><span data-stu-id="ac1de-125">Update a source with name of `mySource`:</span></span>

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a><span data-ttu-id="ac1de-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac1de-126">See also</span></span>

- [<span data-ttu-id="ac1de-127">Sezioni di origine del pacchetto nei file NuGet.configPackage source sections in NuGet.config files</span><span class="sxs-lookup"><span data-stu-id="ac1de-127">Package source sections in NuGet.config files</span></span>](/nuget/reference/nuget-config-file#package-source-sections)

- [<span data-ttu-id="ac1de-128">comando sources (nuget.exe)</span><span class="sxs-lookup"><span data-stu-id="ac1de-128">sources command (nuget.exe)</span></span>](/nuget/reference/cli-reference/cli-ref-sources)
