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
# <a name="authenticate-with-the-azure-sdk-for-net"></a><span data-ttu-id="01327-103">Eseguire l'autenticazione con Azure SDK per .NET</span><span class="sxs-lookup"><span data-stu-id="01327-103">Authenticate with the Azure SDK for .NET</span></span>

## <a name="recommended-azureidentity"></a><span data-ttu-id="01327-104">Consigliato: Azure. Identity</span><span class="sxs-lookup"><span data-stu-id="01327-104">Recommended: Azure.Identity</span></span>

<span data-ttu-id="01327-105">I pacchetti più recenti in Azure SDK per .NET usano un pacchetto di autenticazione comune per l'autenticazione `Azure.Identity` .</span><span class="sxs-lookup"><span data-stu-id="01327-105">The latest packages in the Azure SDK for .NET use a common authentication package to authenticate, `Azure.Identity`.</span></span> <span data-ttu-id="01327-106">L'uso `Azure.Identity` di è consigliato rispetto ad altri meccanismi di autenticazione descritti più avanti in questo documento.</span><span class="sxs-lookup"><span data-stu-id="01327-106">Using `Azure.Identity` is recommended over other authentication mechanisms described later in this document.</span></span> <span data-ttu-id="01327-107">I pacchetti che supportano le credenziali fornite da `Azure.Identity` contengono gli identificatori di pacchetto a partire da *Azure.*</span><span class="sxs-lookup"><span data-stu-id="01327-107">Packages supporting the credentials provided by `Azure.Identity` have package identifiers starting with *Azure.*</span></span> <span data-ttu-id="01327-108">[Per ulteriori informazioni, vedere le versioni più recenti in Azure SDK per .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).</span><span class="sxs-lookup"><span data-stu-id="01327-108">[For more information, see the latest releases in the Azure SDK for .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).</span></span>

<span data-ttu-id="01327-109">Per istruzioni dettagliate sull'uso `Azure.Identity` del nel progetto, vedere la documentazione relativa al [client di identità di Azure per .NET](/dotnet/api/overview/azure/identity-readme).</span><span class="sxs-lookup"><span data-stu-id="01327-109">For complete instructions on using `Azure.Identity` in your project, see the documentation for [Azure Identity client for .NET](/dotnet/api/overview/azure/identity-readme).</span></span>

> [!TIP]
> <span data-ttu-id="01327-110">Per esempi relativi all'uso di identità di Azure per la gestione e l'accesso alle risorse di Azure, vedere l'esempio relativo a [identità, gestione delle risorse e archiviazione](/samples/dotnet/samples/azure-identity-resource-management-storage/) di Azure.</span><span class="sxs-lookup"><span data-stu-id="01327-110">See the [Azure Identity, Resource Management, and Storage sample](/samples/dotnet/samples/azure-identity-resource-management-storage/) for examples of using Azure Identity to manage and access Azure resources.</span></span>

<span data-ttu-id="01327-111">Per eseguire l'autenticazione con le librerie che non supportano Azure. Identity, vedere la parte restante di questo argomento.</span><span class="sxs-lookup"><span data-stu-id="01327-111">To authenticate with libraries that don't support Azure.Identity, see the rest of this topic.</span></span>

## <a name="access-azure-resources"></a><span data-ttu-id="01327-112">Accedere alle risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="01327-112">Access Azure resources</span></span>

<span data-ttu-id="01327-113">Per interagire con le risorse di Azure, ad esempio il recupero di un segreto da Key Vault o l'archiviazione di un BLOB nella risorsa di archiviazione, molte librerie di servizi di Azure richiedono una stringa di connessione o chiavi per l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="01327-113">To interact with Azure resources, such as retrieving a secret from Key Vault or storing a blob in Storage, many Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="01327-114">Ad esempio, il database SQL usa una [stringa di connessione SQL standard](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="01327-114">For example, SQL Database uses a [standard SQL connection string](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core).</span></span> <span data-ttu-id="01327-115">Le stringhe di connessione del servizio vengono usate in altri servizi di Azure, ad esempio [CosmosDB](/azure/cosmos-db/), [cache di Azure per Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)e il [bus di servizio](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span><span class="sxs-lookup"><span data-stu-id="01327-115">Service connection strings are used in other Azure services like [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues).</span></span> <span data-ttu-id="01327-116">È possibile ottenere tali stringhe usando il portale di Azure, l'interfaccia della riga di comando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="01327-116">You can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="01327-117">È anche possibile usare le librerie di gestione di Azure per .NET per eseguire query nelle risorse per creare stringhe di connessione nel codice.</span><span class="sxs-lookup"><span data-stu-id="01327-117">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="01327-118">I metodi per l'utilizzo di una stringa di connessione variano in base al prodotto.</span><span class="sxs-lookup"><span data-stu-id="01327-118">The methods for using a connection string vary by product.</span></span> <span data-ttu-id="01327-119">[Vedere la documentazione relativa al prodotto Azure](/azure/?product=featured).</span><span class="sxs-lookup"><span data-stu-id="01327-119">[Refer to the documentation for your Azure product](/azure/?product=featured).</span></span>

## <a name="manage-azure-resources"></a><span data-ttu-id="01327-120">Gestire le risorse di Azure</span><span class="sxs-lookup"><span data-stu-id="01327-120">Manage Azure resources</span></span>

[!include[Create service principal](includes/create-sp.md)]

<span data-ttu-id="01327-121">Dopo la creazione dell'entità servizio, sono disponibili due opzioni per l'autenticazione nell'entità servizio per la creazione e la gestione delle risorse.</span><span class="sxs-lookup"><span data-stu-id="01327-121">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="01327-122">Per entrambe le opzioni è necessario aggiungere i pacchetti NuGet seguenti al progetto.</span><span class="sxs-lookup"><span data-stu-id="01327-122">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="01327-123">Eseguire l'autenticazione con le credenziali del token</span><span class="sxs-lookup"><span data-stu-id="01327-123">Authenticate with token credentials</span></span>

<span data-ttu-id="01327-124">Il primo metodo consiste nel creare l'oggetto credenziali del token nel codice.</span><span class="sxs-lookup"><span data-stu-id="01327-124">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="01327-125">È necessario archiviare le credenziali in modo sicuro nel file di configurazione, nel Registro di sistema o in Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="01327-125">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="01327-126">Usare i valori di *clientId*, *clientSecret* e *tenantId* dell'output JSON della creazione dell'entità servizio.</span><span class="sxs-lookup"><span data-stu-id="01327-126">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="01327-127">Creare quindi l'oggetto `Azure` del punto di ingresso per iniziare a usare l'API:</span><span class="sxs-lookup"><span data-stu-id="01327-127">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="01327-128">Autenticazione basata su file</span><span class="sxs-lookup"><span data-stu-id="01327-128">File-based authentication</span></span>

<span data-ttu-id="01327-129">L'autenticazione basata su file consente di inserire le credenziali dell'entità servizio in un file di testo normale e di proteggerlo nel file system.</span><span class="sxs-lookup"><span data-stu-id="01327-129">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](includes/file-based-auth.md)]

<span data-ttu-id="01327-130">Leggere i contenuti del file e creare l'oggetto `Azure` del punto di ingresso per iniziare a usare l'API:</span><span class="sxs-lookup"><span data-stu-id="01327-130">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
