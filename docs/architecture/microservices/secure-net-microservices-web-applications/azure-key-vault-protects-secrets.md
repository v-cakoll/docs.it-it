---
title: Uso di Azure Key Vault per proteggere i segreti in fase di produzione
description: Sicurezza in microservizi .NET e applicazioni Web - Azure Key Vault è un metodo eccellente per la gestione dei segreti dell'applicazione completamente controllati dagli amministratori. Gli amministratori possono anche assegnare e revocare valori di sviluppo senza richiederne la gestione agli sviluppatori.
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 4d121f584188c5d5fa9ddf0d91bea5e107eff0cb
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899663"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a>Usare Azure Key Vault per proteggere i segreti in fase di produzione

I segreti archiviati come variabili di ambiente o dallo strumento Secret Manager sono ancora archiviati localmente e non crittografati nel computer. Un'opzione più sicura per l'archiviazione di segreti è [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), una posizione centralizzata e sicura per l'archiviazione di chiavi e segreti.

Il pacchetto **Microsoft.Extensions.Configuration.AzureKeyVault** consente alle applicazioni ASP.NET Core di leggere le informazioni di configurazione da Azure Key Vault. Per iniziare a usare segreti da Azure Key Vault, eseguire i passaggi seguenti:

1. Registrare l'applicazione come applicazione Azure AD. L'accesso agli insiemi di credenziali delle chiavi è gestito da Azure AD. Questa operazione può essere eseguita tramite il portale di gestione di Azure.

   In alternativa, se si vuole che l'applicazione effettui l'autenticazione tramite certificato anziché tramite password o segreto client, è possibile usare il cmdlet PowerShell [New-AzADApplication](/powershell/module/az.resources/new-azadapplication). Il certificato che si registra con Azure Key Vault ha bisogno della sola chiave pubblica. L'applicazione userà la chiave privata.

2. Concedere all'applicazione registrata l'accesso all'insieme di credenziali delle chiavi, creando una nuova entità servizio. A tale scopo, è possibile usare i comandi PowerShell seguenti:

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. Includere l'insieme di credenziali delle chiavi nell'applicazione come origine di configurazione, chiamando il metodo di estensione <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType> quando si crea un'istanza <xref:Microsoft.Extensions.Configuration.IConfigurationRoot>. Si noti che la chiamata di `AddAzureKeyVault` richiede l'ID dell'applicazione registrata e a cui è stato concesso l'accesso all'insieme di credenziali delle chiavi nei passaggi precedenti.

   È anche possibile usare un overload di `AddAzureKeyVault` che accetta un certificato al posto del segreto client, includendo solo un riferimento al pacchetto [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory).

> [!IMPORTANT]
> È consigliabile registrare Azure Key Vault come ultimo provider di configurazione, per far sì che esegua l'override dei valori di configurazione dei provider precedenti.

## <a name="additional-resources"></a>Risorse aggiuntive

- **Usare Azure Key Vault per proteggere i segreti dell'applicazione** \
  [https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault](/azure/guidance/guidance-multitenant-identity-keyvault)

- **Archiviazione sicura di segreti dell'app durante lo sviluppo** \
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- **Configurazione della protezione dati** \
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- **Gestione e durata delle chiavi di protezione dati in ASP.NET Core** \
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

- Repository GitHub **Microsoft.Extensions.Configuration.KeyPerFile**. \
  <https://github.com/dotnet/extensions/tree/master/src/Configuration/Config.KeyPerFile>

>[!div class="step-by-step"]
>[Precedente](developer-app-secrets-storage.md)
>[Successivo](../key-takeaways.md)
