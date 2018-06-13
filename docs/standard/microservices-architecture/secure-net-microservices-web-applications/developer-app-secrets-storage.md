---
title: Archiviazione sicura dei segreti dell'applicazione durante lo sviluppo
description: Architettura di microservizi .NET per applicazioni .NET in contenitori | Archiviazione sicura dei segreti dell'applicazione durante lo sviluppo
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: d8dd2da07104d6461d4eec0cb3fccd61c4db71c1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580114"
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="1cea4-103">Archiviazione sicura dei segreti dell'applicazione durante lo sviluppo</span><span class="sxs-lookup"><span data-stu-id="1cea4-103">Storing application secrets safely during development</span></span>

<span data-ttu-id="1cea4-104">Per connettersi a risorse protette e ad altri servizi, le applicazioni ASP.NET Core in genere usano stringhe di connessione, password o altre credenziali che contengono informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="1cea4-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="1cea4-105">Queste informazioni sensibili sono chiamate *segreti*.</span><span class="sxs-lookup"><span data-stu-id="1cea4-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="1cea4-106">È consigliabile non includere i segreti nel codice sorgente e non archiviarli nel controllo del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="1cea4-106">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="1cea4-107">È invece necessario usare il modello di configurazione di ASP.NET Core per eseguire la lettura dei segreti da posizioni più sicure.</span><span class="sxs-lookup"><span data-stu-id="1cea4-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="1cea4-108">È opportuno separare i segreti per accedere alle risorse di sviluppo e di staging da quelli usati per accedere alle risorse di produzione, perché utenti diversi dovranno accedere a quei set di segreti differenti.</span><span class="sxs-lookup"><span data-stu-id="1cea4-108">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="1cea4-109">Per archiviare i segreti usati per lo sviluppo, gli approcci comuni ne prevedono che vengano archiviati in variabili di ambiente o usando lo strumento Secret Manager di ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1cea4-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="1cea4-110">Per l'archiviazione sicura negli ambienti di produzione, i microservizi possono archiviare i segreti in un'istanza del servizio Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="1cea4-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="1cea4-111">Archiviazione dei segreti nelle variabili di ambiente</span><span class="sxs-lookup"><span data-stu-id="1cea4-111">Storing secrets in environment variables</span></span>

<span data-ttu-id="1cea4-112">Un modo per mantenere i segreti al di fuori del codice sorgente è impostare i segreti basati su stringa come [variabili di ambiente](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) nei computer di sviluppo.</span><span class="sxs-lookup"><span data-stu-id="1cea4-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="1cea4-113">Quando si usano le variabili di ambiente per archiviare i segreti con nomi gerarchici (annidati nelle sezioni di configurazione), creare un nome per le variabili di ambiente che includa l'intera gerarchia del nome del segreto, separata dai due punti (:).</span><span class="sxs-lookup"><span data-stu-id="1cea4-113">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="1cea4-114">Ad esempio, se si imposta la variabile di ambiente Logging:LogLevel:Default su Debug, questo equivale a un valore di configurazione del file JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="1cea4-114">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="1cea4-115">Per accedere ai valori delle variabili di ambiente, l'applicazione deve semplicemente chiamare AddEnvironmentVariables in ConfigurationBuilder durante la creazione di un oggetto IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="1cea4-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="1cea4-116">Si noti che le variabili di ambiente vengono generalmente archiviate come testo normale, quindi se il computer o il processo con le variabili di ambiente è compromesso, i valori delle variabili di ambiente saranno visibili.</span><span class="sxs-lookup"><span data-stu-id="1cea4-116">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="1cea4-117">Archiviazione dei segreti tramite lo strumento Secret Manager di ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1cea4-117">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="1cea4-118">Lo strumento [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) di ASP.NET Core fornisce un altro metodo per mantenere i segreti al di fuori del codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="1cea4-118">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="1cea4-119">Per usare lo strumento Secret Manager, includere un riferimento agli strumenti (DotNetCliToolReference) nel pacchetto Microsoft.Extensions.SecretManager.Tools del file di progetto.</span><span class="sxs-lookup"><span data-stu-id="1cea4-119">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="1cea4-120">Non appena la dipendenza è presente ed è stata ripristinata, è possibile usare il comando dotnet user-secrets per impostare il valore dei segreti dalla riga di comando.</span><span class="sxs-lookup"><span data-stu-id="1cea4-120">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="1cea4-121">I segreti verranno archiviati in un file JSON nella directory del profilo dell'utente (i dettagli variano in base al sistema operativo), lontano dal codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="1cea4-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="1cea4-122">I segreti impostati dallo strumento Secret Manager sono organizzati dalla proprietà UserSecretsId del progetto che usa i segreti.</span><span class="sxs-lookup"><span data-stu-id="1cea4-122">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="1cea4-123">Di conseguenza, è necessario accertarsi di impostare la proprietà UserSecretsId nel file di progetto, come mostrato nel frammento di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="1cea4-123">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="1cea4-124">La stringa effettiva usata come ID non è importante, purché sia univoca nel progetto.</span><span class="sxs-lookup"><span data-stu-id="1cea4-124">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="1cea4-125">I segreti archiviati con Secret Manager vengono usati in un'applicazione chiamando AddUserSecrets&lt;T&gt; nell'istanza di ConfigurationBuilder per includere i segreti per l'applicazione nella relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="1cea4-125">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="1cea4-126">Il parametro generico T deve essere un tipo dell'assembly a cui la proprietà UserSecretId è stata applicata.</span><span class="sxs-lookup"><span data-stu-id="1cea4-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="1cea4-127">In generale, l'uso di AddUserSecrets&lt;Startup&gt; funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="1cea4-127">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="1cea4-128">[Indietro] (authorization-net-microservices-web-applications.md) [Avanti] (azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="1cea4-128">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
