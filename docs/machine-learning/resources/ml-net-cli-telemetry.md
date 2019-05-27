---
title: Raccolta di dati di telemetria dall'interfaccia della riga di comando di ML.NET
description: Informazioni sulle funzionalità di telemetria dell'interfaccia della riga di comando di ML.NET che raccolgono dati di utilizzo per l'analisi, su come disabilitare le funzionalità e sui dati raccolti. Sono inoltre disponibili collegamenti al contratto di licenza di .NET e informazioni sulla conformità a GDPR di Microsoft.
ms.topic: conceptual
ms.date: 05/05/2019
ms.custom: ''
ms.openlocfilehash: 49ebd6c9e1b77c85d891b8c9fb8cbd5c66b478a9
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065544"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a>Raccolta di dati di telemetria dall'interfaccia della riga di comando di ML.NET

L'[interfaccia della riga di comando di ML.NET](http://aka.ms/mlnet-cli) include una funzionalità di telemetria che raccoglie dati di utilizzo anonimi che vengono aggregati per l'uso da Microsoft.

## <a name="how-microsoft-uses-the-data"></a>Come Microsoft usa i dati

Il team di prodotto usa i dati di telemetria dell'interfaccia della riga di comando di ML.NET per capire come migliorare gli strumenti che propone. Se i clienti utilizzano raramente una particolare attività di Machine Learning, ad esempio, il team di prodotto indaga sul motivo e usa i risultati per stabilire le priorità delle funzionalità da sviluppare in futuro. I dati di telemetria dell'interfaccia della riga di comando di ML.NET sono utili anche per il debug dei problemi, ad esempio gli arresti anomali del sistema e le anomalie di codice. 

Nonostante il team di prodotto gradisca disporre di questo tipo di informazioni, Microsoft è consapevole che non tutti gli utenti sono disposti a inviare i dati. [Informazioni su come disabilitare i dati di telemetria.](#opt-out-of-data-collection)

## <a name="scope"></a>Ambito

Il comando `mlnet` avvia l'interfaccia della riga di comando di ML.NET, ma non raccoglie i dati di telemetria.

La funzionalità di telemetria *non è abilitata* quando si esegue il comando `mlnet` con nessun altro comando collegato. Ad esempio:

- `mlnet`
- `mlnet --help`

La funzionalità di telemetria *è abilitata* quando si esegue un [comando dell'interfaccia della riga di comando di ML.NET](../reference/ml-net-cli-reference.md), ad esempio `mlnet auto-train`.

## <a name="opt-out-of-data-collection"></a>Rifiutare esplicitamente la raccolta dei dati

La funzionalità di telemetria dell'interfaccia della riga di comando di ML.NET è abilitata per impostazione predefinita.

Rifiutare esplicitamente la funzionalità di telemetria impostando la variabile di ambiente `DOTNET_CLI_TELEMETRY_OPTOUT` su `1` o `true`. Questa variabile di ambiente viene applicata a livello globale allo strumento dell'interfaccia della riga di comando di .NET.

## <a name="data-points-collected"></a>Punti dati raccolti

La funzionalità raccoglie i dati seguenti:

- Quale comando è stato richiamato, ad esempio `auto-train`
- Indirizzo MAC con hash: ID univoco e anonimo dal punto di vista crittografico (SHA256) per un computer
- Il timestamp di una chiamata
- Indirizzo IP a tre ottetti usato solo per determinare la posizione geografica
- Nome di tutti gli argomenti e dei parametri usati. Non i valori del cliente, ad esempio le stringhe
- Sistema operativo e versione
- Valore del parametro --ml-task: Valori di categorie, ad esempio `regression`, `binary-classification` e `multiclass-classification`
- Dimensione del set di dati [con arrotondamento logaritmico](https://en.wikipedia.org/wiki/Rounding#Rounding_to_a_specified_power) (potenza di 2 più vicina)
- `ExitCode` del comando

I dati vengono inviati ai server Microsoft in modalità protetta grazie alla tecnologia [Azure Application Insights](https://azure.microsoft.com/services/application-insights/), conservati con accesso limitato e usati in base a severi controlli di sicurezza da parte di sistemi di [archiviazione di Azure](https://azure.microsoft.com/services/storage/).

### <a name="data-points-not-collected"></a>Punti dati non raccolti
La funzionalità di telemetria *non* raccoglie:
- dati personali, ad esempio i nomi utente
- nomi dei set di dati
- dati dei set di dati

Se si sospetta che la funzionalità di telemetria dell'interfaccia della riga di comando di ML.NET raccolga dati sensibili o che i dati raccolti siano gestiti in modo inappropriato o non sicuro, segnalare un problema nel repository di [ML.NET](https://github.com/dotnet/machinelearning).

## <a name="license"></a>Licenza

La distribuzione dell'interfaccia della riga di comando di ML.NET da parte di Microsoft è concessa secondo le [Condizioni di licenza software Microsoft: Microsoft .NET Library](https://aka.ms/dotnet-core-eula). Per informazioni dettagliate sulla raccolta e l'elaborazione dei dati, vedere la sezione intitolata "DATA".

## <a name="disclosure"></a>Divulgazione

Quando si esegue un [comando dell'interfaccia della riga di comando di ML.NET](../reference/ml-net-cli-reference.md) per la prima volta, ad esempio `mlnet auto-train`, lo strumento dell'interfaccia della riga di comando di ML.NET visualizza un avviso sulla divulgazione di informazioni che spiega come rifiutare esplicitamente la funzionalità di telemetria. Il testo potrebbe variare lievemente in funzione della versione dell'interfaccia della riga di comando in esecuzione.

## <a name="see-also"></a>Vedere anche
- [Riferimento interfaccia della riga di comando](../reference/ml-net-cli-reference.md)
- [Condizioni di licenza software Microsoft: Microsoft .NET Library](https://aka.ms/dotnet-core-eula)
- [Privacy at Microsoft](https://www.microsoft.com/en-us/trustcenter/privacy/) (La privacy in Microsoft)
- [Informativa sulla privacy di Microsoft](https://privacy.microsoft.com/en-us/privacystatement)
