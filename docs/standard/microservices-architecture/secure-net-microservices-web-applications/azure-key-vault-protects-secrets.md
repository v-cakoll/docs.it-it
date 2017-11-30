---
title: Utilizzando l'insieme di credenziali chiave di Azure per proteggere i segreti in fase di produzione
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Utilizzando l'insieme di credenziali chiave di Azure per proteggere i segreti in fase di produzione
keywords: Docker, microservizi, ASP.NET, contenitore
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="2aab6-104">Utilizzando l'insieme di credenziali chiave di Azure per proteggere i segreti in fase di produzione</span><span class="sxs-lookup"><span data-stu-id="2aab6-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="2aab6-105">I segreti archiviati come variabili di ambiente o dallo strumento di gestione segreto sono ancora archiviati localmente e non crittografati nel computer.</span><span class="sxs-lookup"><span data-stu-id="2aab6-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="2aab6-106">È un'opzione più sicura per l'archiviazione di segreti [insieme credenziali chiavi Azure](https://azure.microsoft.com/services/key-vault/), che fornisce una posizione centrale sicura per l'archiviazione delle chiavi e segreti.</span><span class="sxs-lookup"><span data-stu-id="2aab6-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="2aab6-107">Il pacchetto Microsoft.Extensions.Configuration.AzureKeyVault consente a un'applicazione ASP.NET Core leggere le informazioni di configurazione dall'insieme di credenziali chiave di Azure.</span><span class="sxs-lookup"><span data-stu-id="2aab6-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="2aab6-108">Per iniziare a utilizzare i segreti da un insieme di credenziali chiave di Azure, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2aab6-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="2aab6-109">In primo luogo, registrare l'applicazione come un'applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="2aab6-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="2aab6-110">(L'accesso per gli insiemi di credenziali chiave viene gestito da Azure AD). Questa operazione può essere eseguita tramite il portale di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="2aab6-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="2aab6-111">In alternativa, se si desidera l'applicazione per l'autenticazione tramite certificato anziché un segreto client o la password, è possibile utilizzare il [New AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) cmdlet di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2aab6-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="2aab6-112">Il certificato che si registra con insieme credenziali chiavi Azure deve solo con la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="2aab6-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="2aab6-113">(L'applicazione utilizzerà la chiave privata.)</span><span class="sxs-lookup"><span data-stu-id="2aab6-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="2aab6-114">In secondo luogo, è possibile assegnare l'accesso all'applicazione registrato nell'insieme di credenziali chiave creando una nuova entità servizio.</span><span class="sxs-lookup"><span data-stu-id="2aab6-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="2aab6-115">È possibile farlo usando i seguenti comandi PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2aab6-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="2aab6-116">In terzo luogo, includere l'insieme di credenziali chiave come un'origine di configurazione dell'applicazione chiamando il metodo di estensione IConfigurationBuilder.AddAzureKeyVault quando si crea un'istanza di IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="2aab6-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="2aab6-117">Si noti che la chiamata AddAzureKeyVault richiederà l'ID dell'applicazione che è stato registrato e concesso l'accesso all'insieme di credenziali chiave nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="2aab6-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="2aab6-118">Attualmente, Standard .NET e .NET Core supporta il recupero di informazioni di configurazione da un insieme di credenziali chiave di Azure usando un ID client e il segreto client.</span><span class="sxs-lookup"><span data-stu-id="2aab6-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="2aab6-119">Le applicazioni .NET framework è possano usare un overload di IConfigurationBuilder.AddAzureKeyVault che accetta un certificato al posto il segreto client.</span><span class="sxs-lookup"><span data-stu-id="2aab6-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="2aab6-120">In questo modo, il lavoro è [in corso](https://github.com/aspnet/Configuration/issues/605) per rendere disponibile tale overload in .NET Standard e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="2aab6-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="2aab6-121">Fino a quando l'overload AddAzureKeyVault che accetta che un certificato è disponibile, le applicazioni ASP.NET Core accedere un insieme di credenziali chiave di Azure con l'autenticazione basata su certificato, in modo esplicito la creazione di un oggetto KeyVaultClient, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2aab6-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="2aab6-122">In questo esempio, la chiamata a AddAzureKeyVault viene fornito alla fine della registrazione del provider di configurazione.</span><span class="sxs-lookup"><span data-stu-id="2aab6-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="2aab6-123">È consigliabile registrare l'insieme di credenziali chiave di Azure come ultimo provider di configurazione in modo che abbia la possibilità di eseguire l'override dei valori di configurazione da provider precedenti e non i valori di configurazione da altre origini prevalgono su quelle dall'insieme di credenziali chiave.</span><span class="sxs-lookup"><span data-stu-id="2aab6-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2aab6-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="2aab6-124">Additional resources</span></span>

-   <span data-ttu-id="2aab6-125">**Utilizzando l'insieme di credenziali chiave di Azure per proteggere i segreti dell'applicazione**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="2aab6-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="2aab6-126">**Archiviazione sicura di segreti dell'app durante lo sviluppo**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="2aab6-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="2aab6-127">**Configurazione della protezione dati**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="2aab6-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="2aab6-128">**Gestione e la durata della chiave**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#impostazioni predefinite di protezione dati*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="2aab6-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="2aab6-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="2aab6-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="2aab6-130">Repository di GitHub.</span><span class="sxs-lookup"><span data-stu-id="2aab6-130">GitHub repo.</span></span>
    [<span data-ttu-id="2aab6-131">*https://github.com/ASPNET/Configuration/Tree/DEV/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="2aab6-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="2aab6-132">[Precedente] (per sviluppatori-app-segreti-storage.md) [Avanti] (... / chiave takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="2aab6-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
