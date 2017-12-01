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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Utilizzando l'insieme di credenziali chiave di Azure per proteggere i segreti in fase di produzione

I segreti archiviati come variabili di ambiente o dallo strumento di gestione segreto sono ancora archiviati localmente e non crittografati nel computer. È un'opzione più sicura per l'archiviazione di segreti [insieme credenziali chiavi Azure](https://azure.microsoft.com/services/key-vault/), che fornisce una posizione centrale sicura per l'archiviazione delle chiavi e segreti.

Il pacchetto Microsoft.Extensions.Configuration.AzureKeyVault consente a un'applicazione ASP.NET Core leggere le informazioni di configurazione dall'insieme di credenziali chiave di Azure. Per iniziare a utilizzare i segreti da un insieme di credenziali chiave di Azure, eseguire la procedura seguente:

In primo luogo, registrare l'applicazione come un'applicazione Azure AD. (L'accesso per gli insiemi di credenziali chiave viene gestito da Azure AD). Questa operazione può essere eseguita tramite il portale di gestione di Azure.

In alternativa, se si desidera l'applicazione per l'autenticazione tramite certificato anziché un segreto client o la password, è possibile utilizzare il [New AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) cmdlet di PowerShell. Il certificato che si registra con insieme credenziali chiavi Azure deve solo con la chiave pubblica. (L'applicazione utilizzerà la chiave privata.)

In secondo luogo, è possibile assegnare l'accesso all'applicazione registrato nell'insieme di credenziali chiave creando una nuova entità servizio. È possibile farlo usando i seguenti comandi PowerShell:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

In terzo luogo, includere l'insieme di credenziali chiave come un'origine di configurazione dell'applicazione chiamando il metodo di estensione IConfigurationBuilder.AddAzureKeyVault quando si crea un'istanza di IConfigurationRoot. Si noti che la chiamata AddAzureKeyVault richiederà l'ID dell'applicazione che è stato registrato e concesso l'accesso all'insieme di credenziali chiave nei passaggi precedenti.

  Attualmente, Standard .NET e .NET Core supporta il recupero di informazioni di configurazione da un insieme di credenziali chiave di Azure usando un ID client e il segreto client. Le applicazioni .NET framework è possano usare un overload di IConfigurationBuilder.AddAzureKeyVault che accetta un certificato al posto il segreto client. In questo modo, il lavoro è [in corso](https://github.com/aspnet/Configuration/issues/605) per rendere disponibile tale overload in .NET Standard e .NET Core. Fino a quando l'overload AddAzureKeyVault che accetta che un certificato è disponibile, le applicazioni ASP.NET Core accedere un insieme di credenziali chiave di Azure con l'autenticazione basata su certificato, in modo esplicito la creazione di un oggetto KeyVaultClient, come illustrato nell'esempio seguente:

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

In questo esempio, la chiamata a AddAzureKeyVault viene fornito alla fine della registrazione del provider di configurazione. È consigliabile registrare l'insieme di credenziali chiave di Azure come ultimo provider di configurazione in modo che abbia la possibilità di eseguire l'override dei valori di configurazione da provider precedenti e non i valori di configurazione da altre origini prevalgono su quelle dall'insieme di credenziali chiave.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Utilizzando l'insieme di credenziali chiave di Azure per proteggere i segreti dell'applicazione**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **Archiviazione sicura di segreti dell'app durante lo sviluppo**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **Configurazione della protezione dati**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **Gestione e la durata della chiave**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#impostazioni predefinite di protezione dati*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** Repository di GitHub.
    [*https://github.com/ASPNET/Configuration/Tree/DEV/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Precedente] (per sviluppatori-app-segreti-storage.md) [Avanti] (... / chiave takeaways.md)
