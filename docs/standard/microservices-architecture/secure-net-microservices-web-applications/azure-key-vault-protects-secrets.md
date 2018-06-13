---
title: Uso di Azure Key Vault per proteggere i segreti in fase di produzione
description: Architettura di microservizi .NET per applicazioni .NET nei contenitori | Uso di Azure Key Vault per proteggere i segreti in fase di produzione
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 5ad5686909c29eba5916cbcc4b7115a16108a004
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580403"
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Uso di Azure Key Vault per proteggere i segreti in fase di produzione

I segreti archiviati come variabili di ambiente o dallo strumento Secret Manager sono ancora archiviati localmente e non crittografati nel computer. Un'opzione più sicura per l'archiviazione di segreti è [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), una posizione centralizzata e sicura per l'archiviazione di chiavi e segreti.

Il pacchetto Microsoft.Extensions.Configuration.AzureKeyVault consente alle applicazioni ASP.NET Core di leggere le informazioni di configurazione da Azure Key Vault. Per iniziare a usare segreti da Azure Key Vault, eseguire i passaggi seguenti:

Registrare prima di tutto l'applicazione come applicazione Azure AD. L'accesso agli insiemi di credenziali delle chiavi viene gestito da Azure AD. Questa operazione può essere eseguita tramite il portale di gestione di Azure.

In alternativa, se si vuole che l'applicazione effettui l'autenticazione tramite certificato anziché tramite password o segreto client, è possibile usare il cmdlet PowerShell [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication). Il certificato che si registra con Azure Key Vault ha bisogno della sola chiave pubblica. L'applicazione userà la chiave privata.

In secondo luogo, concedere all'applicazione registrata l'accesso all'insieme di credenziali delle chiavi creando una nuova entità servizio. A tale scopo, è possibile usare i comandi PowerShell seguenti:

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

In terzo luogo, includere l'insieme di credenziali delle chiavi come origine di configurazione nell'applicazione chiamando il metodo di estensione IConfigurationBuilder.AddAzureKeyVault quando si crea un'istanza di IConfigurationRoot. Si noti che la chiamata ad AddAzureKeyVault richiede l'ID dell'applicazione registrata e a cui è stato concesso l'accesso all'insieme di credenziali delle chiavi nei passaggi precedenti.

  .NET Standard e .NET Core attualmente supportano il recupero delle informazioni di configurazione da Azure Key Vault tramite ID client e segreto client. Le applicazioni .NET Framework possono usare un overload di IConfigurationBuilder.AddAzureKeyVault che accetta un certificato al posto del segreto client. Al momento della stesura di questo articolo, sono [in corso](https://github.com/aspnet/Configuration/issues/605) le attività per rendere tale overload disponibile in .NET Standard e .NET Core. Fino a quando non sarà disponibile l'overload di AddAzureKeyVault che accetta un certificato, le applicazioni ASP.NET Core potranno accedere ad Azure Key Vault tramite autenticazione basata su certificato creando un oggetto KeyVaultClient in modo esplicito, come illustrato nell'esempio seguente:

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

In questo esempio, la chiamata ad AddAzureKeyVault viene eseguita alla fine della registrazione del provider di configurazione. È procedura consigliata registrare Azure Key Vault come ultimo provider di configurazione, in modo che abbia la possibilità di eseguire l'override dei valori di configurazione dei provider precedenti e possa evitare che i valori dell'insieme di credenziali delle chiavi vengano sostituiti dai valori di configurazione di altre origini.

## <a name="additional-resources"></a>Risorse aggiuntive

-   **Using Azure Key Vault to protect application secrets**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault) (Uso di Azure Key Vault per proteggere i segreti dell'applicazione)

-   **Safe storage of app secrets during development**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets) (Archiviazione sicura di segreti dell'app durante lo sviluppo)

-   **Configuring data protection**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview) (Configurazione della protezione dati)

-   **Key management and lifetime**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings) (Gestione e durata della chiave; impostazioni predefinite di protezione dati)

-   **Microsoft.Extensions.Configuration.DockerSecrets.** Repository GitHub.
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[Precedente] (developer-app-secrets-storage.md) [Successivo] (../key-takeaways.md)
