---
title: Uso di Azure Key Vault per proteggere i segreti in fase di produzione
description: Sicurezza in microservizi .NET e applicazioni Web - Azure Key Vault è un metodo eccellente per la gestione dei segreti dell'applicazione completamente controllati dagli amministratori. Gli amministratori possono anche assegnare e revocare valori di sviluppo senza richiederne la gestione agli sviluppatori.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: cc95d491136c945255408cec2bd49d4d6579e29a
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501758"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="6f046-104">Usare Azure Key Vault per proteggere i segreti in fase di produzione</span><span class="sxs-lookup"><span data-stu-id="6f046-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="6f046-105">I segreti archiviati come variabili di ambiente o dallo strumento Secret Manager sono ancora archiviati localmente e non crittografati nel computer.</span><span class="sxs-lookup"><span data-stu-id="6f046-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="6f046-106">Un'opzione più sicura per l'archiviazione di segreti è [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), una posizione centralizzata e sicura per l'archiviazione di chiavi e segreti.</span><span class="sxs-lookup"><span data-stu-id="6f046-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="6f046-107">Il pacchetto **Microsoft.Extensions.Configuration.AzureKeyVault** consente alle applicazioni ASP.NET Core di leggere le informazioni di configurazione da Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="6f046-107">The **Microsoft.Extensions.Configuration.AzureKeyVault** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="6f046-108">Per iniziare a usare segreti da Azure Key Vault, eseguire i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f046-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="6f046-109">Registrare l'applicazione come applicazione Azure AD.</span><span class="sxs-lookup"><span data-stu-id="6f046-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="6f046-110">L'accesso agli insiemi di credenziali delle chiavi è gestito da Azure AD. Questa operazione può essere eseguita tramite il portale di gestione di Azure.</span><span class="sxs-lookup"><span data-stu-id="6f046-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.\</span></span>

   <span data-ttu-id="6f046-111">In alternativa, se si vuole che l'applicazione effettui l'autenticazione tramite certificato anziché tramite password o segreto client, è possibile usare il cmdlet PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication).</span><span class="sxs-lookup"><span data-stu-id="6f046-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="6f046-112">Il certificato che si registra con Azure Key Vault ha bisogno della sola chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6f046-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="6f046-113">L'applicazione userà la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="6f046-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="6f046-114">Concedere all'applicazione registrata l'accesso all'insieme di credenziali delle chiavi, creando una nuova entità servizio.</span><span class="sxs-lookup"><span data-stu-id="6f046-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="6f046-115">A tale scopo, è possibile usare i comandi PowerShell seguenti:</span><span class="sxs-lookup"><span data-stu-id="6f046-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="6f046-116">Includere l'insieme di credenziali delle chiavi nell'applicazione come origine di configurazione, chiamando il metodo di estensione <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> quando si crea un'istanza <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>.</span><span class="sxs-lookup"><span data-stu-id="6f046-116">Include the key vault as a configuration source in your application by calling the <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span> <span data-ttu-id="6f046-117">Si noti che la chiamata di `AddAzureKeyVault` richiede l'ID dell'applicazione registrata e a cui è stato concesso l'accesso all'insieme di credenziali delle chiavi nei passaggi precedenti.</span><span class="sxs-lookup"><span data-stu-id="6f046-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span>

   <span data-ttu-id="6f046-118">È anche possibile usare un overload di `AddAzureKeyVault` che accetta un certificato al posto del segreto client, includendo solo un riferimento al pacchetto [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory).</span><span class="sxs-lookup"><span data-stu-id="6f046-118">You can also use an overload of `AddAzureKeyVault` that takes a certificate in place of the client secret by just including a reference to the [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory) package.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f046-119">Si consiglia di registrare Azure Key Vault come ultimo provider di configurazione, in modo che sia possibile eseguire l'override dei valori di configurazione dei provider precedenti.</span><span class="sxs-lookup"><span data-stu-id="6f046-119">We recommend that you register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f046-120">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6f046-120">Additional resources</span></span>

- <span data-ttu-id="6f046-121">**Usare Azure Key Vault per proteggere i segreti dell'applicazione** </span><span class="sxs-lookup"><span data-stu-id="6f046-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault](/azure/guidance/guidance-multitenant-identity-keyvault)

- <span data-ttu-id="6f046-122">**Archiviazione sicura di segreti dell'app durante lo sviluppo** </span><span class="sxs-lookup"><span data-stu-id="6f046-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="6f046-123">**Configurazione della protezione dati** </span><span class="sxs-lookup"><span data-stu-id="6f046-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="6f046-124">**Gestione e durata delle chiavi di protezione dati in ASP.NET Core** </span><span class="sxs-lookup"><span data-stu-id="6f046-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- <span data-ttu-id="6f046-125">Repository GitHub **Microsoft.Extensions.Configuration.KeyPerFile**.</span><span class="sxs-lookup"><span data-stu-id="6f046-125">**Microsoft.Extensions.Configuration.KeyPerFile** GitHub repository.</span></span> \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration/Config.KeyPerFile>

>[!div class="step-by-step"]
><span data-ttu-id="6f046-126">[Precedente](developer-app-secrets-storage.md)
>[Successivo](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="6f046-126">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
