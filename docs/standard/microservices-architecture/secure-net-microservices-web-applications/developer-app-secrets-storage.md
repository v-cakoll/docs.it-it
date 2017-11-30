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
# <a name="storing-application-secrets-safely-during-development"></a>Archiviare in modo sicuro i segreti dell'applicazione durante lo sviluppo

Per connettersi con le risorse protette e altri servizi, applicazioni ASP.NET Core in genere necessario utilizzare stringhe di connessione, le password o altre credenziali contenenti informazioni riservate. Questi tipi di informazioni riservati vengono chiamati *segreti*. È consigliabile non includere informazioni riservate nel codice sorgente e sicuramente non per archiviare i segreti nel controllo del codice sorgente. In alternativa, utilizzare il modello di configurazione di ASP.NET Core per i segreti di lettura da posizioni più sicuri.

È necessario separare i segreti per l'accesso di sviluppo e gestione temporanea di risorse da quelli utilizzati per accedere alle risorse di produzione, poiché utenti diversi saranno necessario accedere a tali set diversi di informazioni riservate. Per archiviare i segreti utilizzati durante lo sviluppo, gli approcci comuni sono per l'archiviazione di segreti nelle variabili di ambiente o tramite lo strumento di gestione di ASP.NET Core segreto. Per l'archiviazione più sicura in ambienti di produzione, microservizi possono archiviare i segreti in un insieme di credenziali chiave di Azure.

## <a name="storing-secrets-in-environment-variables"></a>L'archiviazione di segreti nelle variabili di ambiente

Un modo per proteggere le informazioni riservate da codice sorgente è destinata agli sviluppatori impostare i segreti basato su stringa come [le variabili di ambiente](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) sul proprio computer di sviluppo. Quando si utilizzano variabili di ambiente per l'archiviazione di segreti con nomi gerarchici (quelli annidati in sezioni di configurazione), creare un nome per le variabili di ambiente che include la gerarchia completa del nome del segreto, delimitati da punti (:).

Ad esempio, l'impostazione di una variabile di ambiente: LogLevel:Default di registrazione di Debug sarà equivalente a un valore di configurazione dal file JSON seguente:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

Per accedere a questi valori dalle variabili di ambiente, l'applicazione deve semplicemente chiamare AddEnvironmentVariables nel relativo ConfigurationBuilder quando si crea un oggetto IConfigurationRoot.

Si noti che le variabili di ambiente sono in genere archiviate come testo normale, pertanto se il computer o i processi con le variabili di ambiente sono compromesso, i valori delle variabili di ambiente saranno visibili.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>L'archiviazione di segreti usando gestione ASP.NET Core segreto

ASP.NET Core [Manager segreto](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) strumento fornisce un altro metodo di protezione delle informazioni riservate da codice sorgente. Per utilizzare lo strumento di gestione di segreto, includere un riferimento di strumenti (DotNetCliToolReference) per il pacchetto Microsoft.Extensions.SecretManager.Tools nel file di progetto. Una volta che tale dipendenza è presente ed è stato ripristinato, il comando di informazioni riservate dell'utente dotnet può essere utilizzato per impostare il valore di segreti dalla riga di comando. Questi segreti verranno archiviati in un file JSON nella directory del profilo dell'utente (dettagli variano a seconda del sistema operativo), dal codice sorgente.

I segreti impostati dallo strumento di gestione segreto sono organizzati per la proprietà UserSecretsId del progetto che usa i segreti. Pertanto, è necessario assicurarsi di impostare la proprietà UserSecretsId nel file di progetto (come illustrato nel frammento riportato di seguito). La stringa effettiva utilizzata come l'ID non è importante, purché sia univoco nel progetto.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Utilizzo di segreti archiviati con segreto Manager in un'applicazione viene eseguita chiamando AddUserSecrets&lt;T&gt; nell'istanza ConfigurationBuilder per includere informazioni riservate per l'applicazione nella configurazione. Il parametro generico T deve essere un tipo di assembly che è stato applicato il UserSecretId a. In genere utilizzando AddUserSecrets&lt;avvio&gt; funziona correttamente.


>[!div class="step-by-step"]
[Precedente] (autorizzazione-net-microservizi-web-applications.md) [Avanti] (azure-key-insieme di credenziali-protegge-secrets.md)
