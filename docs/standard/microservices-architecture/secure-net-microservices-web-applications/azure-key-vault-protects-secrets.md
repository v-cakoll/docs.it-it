---
title: Uso di Azure Key Vault per proteggere i segreti in fase di produzione
description: Architettura di microservizi .NET per applicazioni .NET nei contenitori | Uso di Azure Key Vault per proteggere i segreti in fase di produzione
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5738b81c90c886aff48451742881807dc09a9ff9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863987"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="46d5b-103">Uso di Azure Key Vault per proteggere i segreti in fase di produzione</span><span class="sxs-lookup"><span data-stu-id="46d5b-103">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="46d5b-104">I segreti archiviati come variabili di ambiente o dallo strumento Secret Manager sono ancora archiviati localmente e non crittografati nel computer.</span><span class="sxs-lookup"><span data-stu-id="46d5b-104">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="46d5b-105">Un'opzione più sicura per l'archiviazione di segreti è [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), una posizione centralizzata e sicura per l'archiviazione di chiavi e segreti.</span><span class="sxs-lookup"><span data-stu-id="46d5b-105">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="46d5b-106">Il pacchetto Microsoft.Extensions.Configuration.AzureKeyVault consente alle applicazioni ASP.NET Core di leggere le informazioni di configurazione da Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="46d5b-106">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="46d5b-107">Per iniziare a usare segreti da Azure Key Vault, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="46d5b-107">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="46d5b-108">Registrare prima di tutto l'applicazione come applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="46d5b-108">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="46d5b-109">L'accesso agli insiemi di credenziali delle chiavi viene gestito da Azure AD. Questa operazione può essere eseguita tramite il portale di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="46d5b-109">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="46d5b-110">In alternativa, se si vuole che l'applicazione effettui l'autenticazione tramite certificato anziché tramite password o segreto client, è possibile usare il cmdlet PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/module/azurerm.resources/new-azurermadapplication).</span><span class="sxs-lookup"><span data-stu-id="46d5b-110">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/module/azurerm.resources/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="46d5b-111">Il certificato che si registra con Azure Key Vault ha bisogno della sola chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="46d5b-111">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="46d5b-112">L'applicazione userà la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="46d5b-112">(Your application will use the private key.)</span></span>

<span data-ttu-id="46d5b-113">In secondo luogo, concedere all'applicazione registrata l'accesso all'insieme di credenziali delle chiavi creando una nuova entità servizio.</span><span class="sxs-lookup"><span data-stu-id="46d5b-113">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="46d5b-114">A tale scopo, è possibile usare i comandi PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="46d5b-114">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="46d5b-115">In terzo luogo, includere l'insieme di credenziali delle chiavi come origine di configurazione nell'applicazione chiamando il metodo di estensione IConfigurationBuilder.AddAzureKeyVault quando si crea un'istanza di IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="46d5b-115">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="46d5b-116">Si noti che la chiamata ad AddAzureKeyVault richiede l'ID dell'applicazione registrata e a cui è stato concesso l'accesso all'insieme di credenziali delle chiavi nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="46d5b-116">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="46d5b-117">.NET Standard e .NET Core attualmente supportano il recupero delle informazioni di configurazione da Azure Key Vault tramite ID client e segreto client.</span><span class="sxs-lookup"><span data-stu-id="46d5b-117">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="46d5b-118">Le applicazioni .NET Framework possono usare un overload di IConfigurationBuilder.AddAzureKeyVault che accetta un certificato al posto del segreto client.</span><span class="sxs-lookup"><span data-stu-id="46d5b-118">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="46d5b-119">Al momento della stesura di questo articolo, sono [in corso](https://github.com/aspnet/Configuration/issues/605) le attività per rendere tale overload disponibile in .NET Standard e .NET Core.</span><span class="sxs-lookup"><span data-stu-id="46d5b-119">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="46d5b-120">Fino a quando non sarà disponibile l'overload di AddAzureKeyVault che accetta un certificato, le applicazioni ASP.NET Core potranno accedere ad Azure Key Vault tramite autenticazione basata su certificato creando un oggetto KeyVaultClient in modo esplicito, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="46d5b-120">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="46d5b-121">In questo esempio, la chiamata ad AddAzureKeyVault viene eseguita alla fine della registrazione del provider di configurazione.</span><span class="sxs-lookup"><span data-stu-id="46d5b-121">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="46d5b-122">È procedura consigliata registrare Azure Key Vault come ultimo provider di configurazione, in modo che abbia la possibilità di eseguire l'override dei valori di configurazione dei provider precedenti e possa evitare che i valori dell'insieme di credenziali delle chiavi vengano sostituiti dai valori di configurazione di altre origini.</span><span class="sxs-lookup"><span data-stu-id="46d5b-122">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46d5b-123">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="46d5b-123">Additional resources</span></span>

-   <span data-ttu-id="46d5b-124">**Using Azure Key Vault to protect application secrets**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault) (Uso di Azure Key Vault per proteggere i segreti dell'applicazione)</span><span class="sxs-lookup"><span data-stu-id="46d5b-124">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="46d5b-125">**Safe storage of app secrets during development**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets) (Archiviazione sicura di segreti dell'app durante lo sviluppo)</span><span class="sxs-lookup"><span data-stu-id="46d5b-125">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="46d5b-126">**Configuring data protection**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview) (Configurazione della protezione dati)</span><span class="sxs-lookup"><span data-stu-id="46d5b-126">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="46d5b-127">**Gestione e durata delle chiavi**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="46d5b-127">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="46d5b-128">Repository GitHub **Microsoft.Extensions.Configuration.KeyPerFile**.</span><span class="sxs-lookup"><span data-stu-id="46d5b-128">**Microsoft.Extensions.Configuration.KeyPerFile** GitHub repo.</span></span>
    [*https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile*](https://github.com/aspnet/Configuration/tree/master/src/Config.KeyPerFile)

>[!div class="step-by-step"]
<span data-ttu-id="46d5b-129">[Precedente](developer-app-secrets-storage.md)
[Successivo](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="46d5b-129">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
