---
title: Uso di Azure Key Vault per proteggere i segreti in fase di produzione
description: Architettura di microservizi .NET per applicazioni .NET nei contenitori | Uso di Azure Key Vault per proteggere i segreti in fase di produzione
keywords: Docker, microservizi, ASP.NET, contenitore
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb289c7361362c225eac8b9898bac276c4b623b4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="145c3-104">Uso di Azure Key Vault per proteggere i segreti in fase di produzione</span><span class="sxs-lookup"><span data-stu-id="145c3-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="145c3-105">I segreti archiviati come variabili di ambiente o dallo strumento Secret Manager sono ancora archiviati localmente e non crittografati nel computer.</span><span class="sxs-lookup"><span data-stu-id="145c3-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="145c3-106">Un'opzione più sicura per l'archiviazione di segreti è [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), una posizione centralizzata e sicura per l'archiviazione di chiavi e segreti.</span><span class="sxs-lookup"><span data-stu-id="145c3-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="145c3-107">Il pacchetto Microsoft.Extensions.Configuration.AzureKeyVault consente alle applicazioni ASP.NET Core di leggere le informazioni di configurazione da Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="145c3-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="145c3-108">Per iniziare a usare segreti da Azure Key Vault, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="145c3-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="145c3-109">Registrare prima di tutto l'applicazione come applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="145c3-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="145c3-110">L'accesso agli insiemi di credenziali delle chiavi viene gestito da Azure AD. Questa operazione può essere eseguita tramite il portale di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="145c3-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="145c3-111">In alternativa, se si vuole che l'applicazione effettui l'autenticazione tramite certificato anziché tramite password o segreto client, è possibile usare il cmdlet PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication).</span><span class="sxs-lookup"><span data-stu-id="145c3-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="145c3-112">Il certificato che si registra con Azure Key Vault ha bisogno della sola chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="145c3-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="145c3-113">L'applicazione userà la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="145c3-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="145c3-114">In secondo luogo, concedere all'applicazione registrata l'accesso all'insieme di credenziali delle chiavi creando una nuova entità servizio.</span><span class="sxs-lookup"><span data-stu-id="145c3-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="145c3-115">A tale scopo, è possibile usare i comandi PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="145c3-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="145c3-116">In terzo luogo, includere l'insieme di credenziali delle chiavi come origine di configurazione nell'applicazione chiamando il metodo di estensione IConfigurationBuilder.AddAzureKeyVault quando si crea un'istanza di IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="145c3-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="145c3-117">Si noti che la chiamata ad AddAzureKeyVault richiede l'ID dell'applicazione registrata e a cui è stato concesso l'accesso all'insieme di credenziali delle chiavi nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="145c3-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="145c3-118">.NET Standard e .NET Core attualmente supportano il recupero delle informazioni di configurazione da Azure Key Vault tramite ID client e segreto client.</span><span class="sxs-lookup"><span data-stu-id="145c3-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="145c3-119">Le applicazioni .NET Framework possono usare un overload di IConfigurationBuilder.AddAzureKeyVault che accetta un certificato al posto del segreto client.</span><span class="sxs-lookup"><span data-stu-id="145c3-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="145c3-120">Al momento della stesura di questo articolo, sono [in corso](https://github.com/aspnet/Configuration/issues/605) le attività per rendere tale overload disponibile in .NET Standard e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="145c3-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="145c3-121">Fino a quando non sarà disponibile l'overload di AddAzureKeyVault che accetta un certificato, le applicazioni ASP.NET Core potranno accedere ad Azure Key Vault tramite autenticazione basata su certificato creando un oggetto KeyVaultClient in modo esplicito, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="145c3-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

<span data-ttu-id="145c3-122">In questo esempio, la chiamata ad AddAzureKeyVault viene eseguita alla fine della registrazione del provider di configurazione.</span><span class="sxs-lookup"><span data-stu-id="145c3-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="145c3-123">È procedura consigliata registrare Azure Key Vault come ultimo provider di configurazione, in modo che abbia la possibilità di eseguire l'override dei valori di configurazione dei provider precedenti e possa evitare che i valori dell'insieme di credenziali delle chiavi vengano sostituiti dai valori di configurazione di altre origini.</span><span class="sxs-lookup"><span data-stu-id="145c3-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="145c3-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="145c3-124">Additional resources</span></span>

-   <span data-ttu-id="145c3-125">**Usare Azure Key Vault per proteggere i segreti dell'applicazione**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="145c3-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="145c3-126">**Archiviazione sicura di segreti dell'app durante lo sviluppo**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="145c3-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="145c3-127">**Configurazione della protezione dei dati**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="145c3-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="145c3-128">**Gestione e durata delle chiavi**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="145c3-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="145c3-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="145c3-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="145c3-130">Repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="145c3-130">GitHub repo.</span></span>
    [<span data-ttu-id="145c3-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="145c3-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="145c3-132">[Precedente] (developer-app-secrets-storage.md) [Successivo] (../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="145c3-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
