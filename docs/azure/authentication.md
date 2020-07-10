---
title: Informazioni sull'autenticazione nelle librerie di Azure per .NET
description: Illustra le diverse modalità di autenticazione con Azure SDK per .NET.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 5ed29d5485dc7f59bcc757c8903116edf6bd5d7d
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174945"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a>Eseguire l'autenticazione con Azure SDK per .NET

## <a name="recommended-azureidentity"></a>Consigliato: Azure. Identity

I pacchetti più recenti in Azure SDK per .NET usano un pacchetto di autenticazione comune per l'autenticazione `Azure.Identity` . L'uso `Azure.Identity` di è consigliato rispetto ad altri meccanismi di autenticazione descritti più avanti in questo documento. I pacchetti che supportano le credenziali fornite da `Azure.Identity` contengono gli identificatori di pacchetto a partire da *Azure.* [Per ulteriori informazioni, vedere le versioni più recenti in Azure SDK per .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).

Per istruzioni dettagliate sull'uso `Azure.Identity` del nel progetto, vedere la documentazione relativa al [client di identità di Azure per .NET](/dotnet/api/overview/azure/identity-readme).

> [!TIP]
> Per esempi relativi all'uso di identità di Azure per la gestione e l'accesso alle risorse di Azure, vedere l'esempio relativo a [identità, gestione delle risorse e archiviazione](/samples/dotnet/samples/azure-identity-resource-management-storage/) di Azure.

Per eseguire l'autenticazione con le librerie che non supportano Azure. Identity, vedere la parte restante di questo argomento.

## <a name="access-azure-resources"></a>Accedere alle risorse di Azure

Per interagire con le risorse di Azure, ad esempio il recupero di un segreto da Key Vault o l'archiviazione di un BLOB nella risorsa di archiviazione, molte librerie di servizi di Azure richiedono una stringa di connessione o chiavi per l'autenticazione. Ad esempio, il database SQL usa una [stringa di connessione SQL standard](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core). Le stringhe di connessione del servizio vengono usate in altri servizi di Azure, ad esempio [CosmosDB](/azure/cosmos-db/), [cache di Azure per Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)e il [bus di servizio](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues). È possibile ottenere tali stringhe usando il portale di Azure, l'interfaccia della riga di comando o PowerShell. È anche possibile usare le librerie di gestione di Azure per .NET per eseguire query nelle risorse per creare stringhe di connessione nel codice.

I metodi per l'utilizzo di una stringa di connessione variano in base al prodotto. [Vedere la documentazione relativa al prodotto Azure](/azure/?product=featured).

## <a name="manage-azure-resources"></a>Gestire le risorse di Azure

[!include[Create service principal](includes/create-sp.md)]

Dopo la creazione dell'entità servizio, sono disponibili due opzioni per l'autenticazione nell'entità servizio per la creazione e la gestione delle risorse.

Per entrambe le opzioni è necessario aggiungere i pacchetti NuGet seguenti al progetto.

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a>Eseguire l'autenticazione con le credenziali del token

Il primo metodo consiste nel creare l'oggetto credenziali del token nel codice. È necessario archiviare le credenziali in modo sicuro nel file di configurazione, nel Registro di sistema o in Azure Key Vault.

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

Usare i valori di *clientId*, *clientSecret* e *tenantId* dell'output JSON della creazione dell'entità servizio.

Creare quindi l'oggetto `Azure` del punto di ingresso per iniziare a usare l'API:

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a>Autenticazione basata su file

L'autenticazione basata su file consente di inserire le credenziali dell'entità servizio in un file di testo normale e di proteggerlo nel file system.

[!include[File-based authentication](includes/file-based-auth.md)]

Leggere i contenuti del file e creare l'oggetto `Azure` del punto di ingresso per iniziare a usare l'API:

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
