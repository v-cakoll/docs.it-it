---
title: Archiviazione sicura dei segreti dell'applicazione durante lo sviluppo
description: Sicurezza in microservizi .NET Microservices e applicazioni Web - Evitare di archiviare i segreti dell'applicazione quali password, stringhe di connessione o chiavi API nel controllo del codice sorgente. Esaminare in dettaglio le opzioni usabili in ASP.NET Core, in particolare le modalità di gestione dei "segreti utente".
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 1ef2246746b9165f1564fa7be64ff7eb28eb1d32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501791"
---
# <a name="store-application-secrets-safely-during-development"></a>Archiviare in modo sicuro i segreti dell'applicazione durante lo sviluppo

Per connettersi a risorse protette e ad altri servizi, le applicazioni ASP.NET Core in genere usano stringhe di connessione, password o altre credenziali che contengono informazioni sensibili. Queste informazioni sensibili sono chiamate *segreti*. È consigliabile non includere i segreti nel codice sorgente e verificare di non archiviarli nel controllo del codice sorgente. È invece necessario usare il modello di configurazione di ASP.NET Core per eseguire la lettura dei segreti da posizioni più sicure.

È necessario separare i segreti per accedere alle risorse di sviluppo e di staging da quelli usati per accedere alle risorse di produzione, perché utenti diversi dovranno accedere a set di segreti diversi. Per archiviare i segreti usati per lo sviluppo, gli approcci comuni ne prevedono che vengano archiviati in variabili di ambiente o usando lo strumento Secret Manager di ASP.NET Core. Per l'archiviazione sicura negli ambienti di produzione, i microservizi possono archiviare i segreti in un'istanza del servizio Azure Key Vault.

## <a name="store-secrets-in-environment-variables"></a>Archiviare i segreti in variabili di ambiente

Un modo per mantenere i segreti al di fuori del codice sorgente è impostare i segreti basati su stringa come [variabili di ambiente](/aspnet/core/security/app-secrets#environment-variables) nei computer di sviluppo. Quando si usano le variabili di ambiente per archiviare i segreti con nomi gerarchici (ad esempio quelli annidati nelle sezioni di configurazione), è necessario creare un nome per le variabili che includa l'intera gerarchia delle sezioni, separate dai due punti (:).

Se ad esempio si imposta la variabile di ambiente `Logging:LogLevel:Default` sul valore `Debug`, questo equivale al valore di configurazione del file JSON seguente:

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

Si noti che le variabili di ambiente vengono in genere archiviate come testo normale, quindi se il computer o il processo con le variabili di ambiente viene compromesso, i valori delle variabili di ambiente saranno visibili.

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a>Archiviare i segreti tramite lo strumento Secret Manager di ASP.NET Core

Lo strumento ASP.NET Core [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) fornisce un altro metodo per mantenere i segreti fuori dal codice sorgente durante **lo sviluppo.** Per usare lo strumento Secret Manager, installare il pacchetto **Microsoft.Extensions.Configuration.SecretManager** nel file di progetto. Quando questa dipendenza è presente ed è stata ripristinata, è possibile usare il comando `dotnet user-secrets` per impostare il valore dei segreti dalla riga di comando. I segreti verranno archiviati in un file JSON nella directory del profilo dell'utente (i dettagli variano in base al sistema operativo), lontano dal codice sorgente.

I segreti impostati dallo strumento Secret Manager sono organizzati dalla proprietà `UserSecretsId` del progetto che usa i segreti. Di conseguenza è necessario accertarsi di impostare la proprietà UserSecretsId nel file di progetto, come illustrato nel frammento di codice seguente. Il valore predefinito è un GUID assegnato da Visual Studio, ma la stringa vera e propria non è importante, purché sia univoca nel computer in uso.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

I segreti archiviati con Secret Manager vengono usati in un'applicazione chiamando `AddUserSecrets<T>` nell'istanza di ConfigurationBuilder per includere i segreti per l'applicazione nella relativa configurazione. Il parametro generico T deve essere un tipo dell'assembly a cui la proprietà UserSecretId è stata applicata. In genere l'uso di `AddUserSecrets<Startup>` funziona correttamente.

`AddUserSecrets<Startup>()` è inclusa tra le opzioni predefinite per l'ambiente di sviluppo quando si usa il metodo `CreateDefaultBuilder` in *Program.cs*.

>[!div class="step-by-step"]
>[Successivo](authorization-net-microservices-web-applications.md)
>[precedente](azure-key-vault-protects-secrets.md)
