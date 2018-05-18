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
---
# <a name="storing-application-secrets-safely-during-development"></a>Archiviazione sicura dei segreti dell'applicazione durante lo sviluppo

Per connettersi a risorse protette e ad altri servizi, le applicazioni ASP.NET Core in genere usano stringhe di connessione, password o altre credenziali che contengono informazioni sensibili. Queste informazioni sensibili sono chiamate *segreti*. È consigliabile non includere i segreti nel codice sorgente e non archiviarli nel controllo del codice sorgente. È invece necessario usare il modello di configurazione di ASP.NET Core per eseguire la lettura dei segreti da posizioni più sicure.

È opportuno separare i segreti per accedere alle risorse di sviluppo e di staging da quelli usati per accedere alle risorse di produzione, perché utenti diversi dovranno accedere a quei set di segreti differenti. Per archiviare i segreti usati per lo sviluppo, gli approcci comuni ne prevedono che vengano archiviati in variabili di ambiente o usando lo strumento Secret Manager di ASP.NET Core. Per l'archiviazione sicura negli ambienti di produzione, i microservizi possono archiviare i segreti in un'istanza del servizio Azure Key Vault.

## <a name="storing-secrets-in-environment-variables"></a>Archiviazione dei segreti nelle variabili di ambiente

Un modo per mantenere i segreti al di fuori del codice sorgente è impostare i segreti basati su stringa come [variabili di ambiente](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) nei computer di sviluppo. Quando si usano le variabili di ambiente per archiviare i segreti con nomi gerarchici (annidati nelle sezioni di configurazione), creare un nome per le variabili di ambiente che includa l'intera gerarchia del nome del segreto, separata dai due punti (:).

Ad esempio, se si imposta la variabile di ambiente Logging:LogLevel:Default su Debug, questo equivale a un valore di configurazione del file JSON seguente:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

Per accedere ai valori delle variabili di ambiente, l'applicazione deve semplicemente chiamare AddEnvironmentVariables in ConfigurationBuilder durante la creazione di un oggetto IConfigurationRoot.

Si noti che le variabili di ambiente vengono generalmente archiviate come testo normale, quindi se il computer o il processo con le variabili di ambiente è compromesso, i valori delle variabili di ambiente saranno visibili.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>Archiviazione dei segreti tramite lo strumento Secret Manager di ASP.NET Core

Lo strumento [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) di ASP.NET Core fornisce un altro metodo per mantenere i segreti al di fuori del codice sorgente. Per usare lo strumento Secret Manager, includere un riferimento agli strumenti (DotNetCliToolReference) nel pacchetto Microsoft.Extensions.SecretManager.Tools del file di progetto. Non appena la dipendenza è presente ed è stata ripristinata, è possibile usare il comando dotnet user-secrets per impostare il valore dei segreti dalla riga di comando. I segreti verranno archiviati in un file JSON nella directory del profilo dell'utente (i dettagli variano in base al sistema operativo), lontano dal codice sorgente.

I segreti impostati dallo strumento Secret Manager sono organizzati dalla proprietà UserSecretsId del progetto che usa i segreti. Di conseguenza, è necessario accertarsi di impostare la proprietà UserSecretsId nel file di progetto, come mostrato nel frammento di codice seguente. La stringa effettiva usata come ID non è importante, purché sia univoca nel progetto.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

I segreti archiviati con Secret Manager vengono usati in un'applicazione chiamando AddUserSecrets&lt;T&gt; nell'istanza di ConfigurationBuilder per includere i segreti per l'applicazione nella relativa configurazione. Il parametro generico T deve essere un tipo dell'assembly a cui la proprietà UserSecretId è stata applicata. In generale, l'uso di AddUserSecrets&lt;Startup&gt; funziona correttamente.


>[!div class="step-by-step"]
[Indietro] (authorization-net-microservices-web-applications.md) [Avanti] (azure-key-vault-protects-secrets.md)
