---
title: Archiviare in modo sicuro i segreti dell'applicazione durante lo sviluppo
description: Architettura di Microservizi .NET per le applicazioni nei contenitori .NET | Archiviare in modo sicuro i segreti dell'applicazione durante lo sviluppo
keywords: Docker, microservizi, ASP.NET, contenitore
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="dfc54-104">Archiviare in modo sicuro i segreti dell'applicazione durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="dfc54-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="dfc54-105">Per connettersi con le risorse protette e altri servizi, applicazioni ASP.NET Core in genere necessario utilizzare stringhe di connessione, le password o altre credenziali contenenti informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="dfc54-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="dfc54-106">Questi tipi di informazioni riservati vengono chiamati *segreti*.</span><span class="sxs-lookup"><span data-stu-id="dfc54-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="dfc54-107">È consigliabile non includere informazioni riservate nel codice sorgente e sicuramente non per archiviare i segreti nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="dfc54-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="dfc54-108">In alternativa, utilizzare il modello di configurazione di ASP.NET Core per i segreti di lettura da posizioni più sicuri.</span><span class="sxs-lookup"><span data-stu-id="dfc54-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="dfc54-109">È necessario separare i segreti per l'accesso di sviluppo e gestione temporanea di risorse da quelli utilizzati per accedere alle risorse di produzione, poiché utenti diversi saranno necessario accedere a tali set diversi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="dfc54-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="dfc54-110">Per archiviare i segreti utilizzati durante lo sviluppo, gli approcci comuni sono per l'archiviazione di segreti nelle variabili di ambiente o tramite lo strumento di gestione di ASP.NET Core segreto.</span><span class="sxs-lookup"><span data-stu-id="dfc54-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="dfc54-111">Per l'archiviazione più sicura in ambienti di produzione, microservizi possono archiviare i segreti in un insieme di credenziali chiave di Azure.</span><span class="sxs-lookup"><span data-stu-id="dfc54-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="dfc54-112">L'archiviazione di segreti nelle variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="dfc54-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="dfc54-113">Un modo per proteggere le informazioni riservate da codice sorgente è destinata agli sviluppatori impostare i segreti basato su stringa come [le variabili di ambiente](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) sul proprio computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="dfc54-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="dfc54-114">Quando si utilizzano variabili di ambiente per l'archiviazione di segreti con nomi gerarchici (quelli annidati in sezioni di configurazione), creare un nome per le variabili di ambiente che include la gerarchia completa del nome del segreto, delimitati da punti (:).</span><span class="sxs-lookup"><span data-stu-id="dfc54-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="dfc54-115">Ad esempio, l'impostazione di una variabile di ambiente: LogLevel:Default di registrazione di Debug sarà equivalente a un valore di configurazione dal file JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="dfc54-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="dfc54-116">Per accedere a questi valori dalle variabili di ambiente, l'applicazione deve semplicemente chiamare AddEnvironmentVariables nel relativo ConfigurationBuilder quando si crea un oggetto IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="dfc54-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="dfc54-117">Si noti che le variabili di ambiente sono in genere archiviate come testo normale, pertanto se il computer o i processi con le variabili di ambiente sono compromesso, i valori delle variabili di ambiente saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="dfc54-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="dfc54-118">L'archiviazione di segreti usando gestione ASP.NET Core segreto</span><span class="sxs-lookup"><span data-stu-id="dfc54-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="dfc54-119">ASP.NET Core [Manager segreto](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) strumento fornisce un altro metodo di protezione delle informazioni riservate da codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="dfc54-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="dfc54-120">Per utilizzare lo strumento di gestione di segreto, includere un riferimento di strumenti (DotNetCliToolReference) per il pacchetto Microsoft.Extensions.SecretManager.Tools nel file di progetto.</span><span class="sxs-lookup"><span data-stu-id="dfc54-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="dfc54-121">Una volta che tale dipendenza è presente ed è stato ripristinato, il comando di informazioni riservate dell'utente dotnet può essere utilizzato per impostare il valore di segreti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="dfc54-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="dfc54-122">Questi segreti verranno archiviati in un file JSON nella directory del profilo dell'utente (dettagli variano a seconda del sistema operativo), dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="dfc54-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="dfc54-123">I segreti impostati dallo strumento di gestione segreto sono organizzati per la proprietà UserSecretsId del progetto che usa i segreti.</span><span class="sxs-lookup"><span data-stu-id="dfc54-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="dfc54-124">Pertanto, è necessario assicurarsi di impostare la proprietà UserSecretsId nel file di progetto (come illustrato nel frammento riportato di seguito).</span><span class="sxs-lookup"><span data-stu-id="dfc54-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="dfc54-125">La stringa effettiva utilizzata come l'ID non è importante, purché sia univoco nel progetto.</span><span class="sxs-lookup"><span data-stu-id="dfc54-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="dfc54-126">Utilizzo di segreti archiviati con segreto Manager in un'applicazione viene eseguita chiamando AddUserSecrets&lt;T&gt; nell'istanza ConfigurationBuilder per includere informazioni riservate per l'applicazione nella configurazione.</span><span class="sxs-lookup"><span data-stu-id="dfc54-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="dfc54-127">Il parametro generico T deve essere un tipo di assembly che è stato applicato il UserSecretId a.</span><span class="sxs-lookup"><span data-stu-id="dfc54-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="dfc54-128">In genere utilizzando AddUserSecrets&lt;avvio&gt; funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="dfc54-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="dfc54-129">[Precedente] (autorizzazione-net-microservizi-web-applications.md) [Avanti] (azure-key-insieme di credenziali-protegge-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="dfc54-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
