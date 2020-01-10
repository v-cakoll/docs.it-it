---
title: Come viene specificata la versione del runtime di .NET Core e di .NET Core SDK
description: Questo articolo illustra come viene specificata la versione di .NET Core SDK e del runtime di .NET Core (simile al Versionamento Semantico).
ms.date: 07/26/2018
ms.openlocfilehash: c85a2112b439768068663688947960ac814de824
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777326"
---
# <a name="overview-of-how-net-core-is-versioned"></a>Panoramica di come viene specificata la versione di .NET Core

.NET Core indica il runtime di .NET Core e .NET Core SDK, contenente gli strumenti necessari per lo sviluppo di applicazioni. .NET Core SDK è progettato per funzionare con qualsiasi versione precedente del runtime di .NET Core. Questo articolo illustra il runtime e la strategia delle versioni del SDK. La spiegazione dei numeri di versione di .NET Standard è disponibile nell'articolo di presentazione di [.NET Standard](../../standard/net-standard.md#net-implementation-support).

Il runtime di .NET Core e .NET Core SDK aggiungono le nuove funzionalità con frequenze diverse: in generale .NET Core SDK fornisce strumenti aggiornati più rapidamente rispetto all'aggiornamento dell'ambiente di produzione da parte del runtime di .NET Core.

## <a name="versioning-details"></a>Dettagli del controllo delle versioni

".NET Core 2.1" corrisponde al numero di versione del runtime di .NET Core. Il runtime di .NET Core ha un approccio di tipo versione principale/versione secondaria/patch per il controllo delle versioni basato sul [versionamento semantico](#semantic-versioning).

.NET Core SDK non segue il versionamento semantico. .NET Core SDK viene rilasciato più rapidamente e le relative versioni trasmettono sia il runtime allineato sia le versioni secondarie e le patch del SDK. Le prime due posizioni del numero di versione di .NET Core SDK sono identiche a quelle del runtime di .NET Core con il quale viene rilasciato il SDK. Ogni versione del SDK può creare applicazioni per questa versione del runtime o per qualsiasi versione precedente.

La terza posizione del numero di versione del SDK comunica la versione secondaria e il numero di patch. La versione secondaria viene moltiplicata per 100. Quindi la versione secondaria 1, versione patch 2 viene rappresentata come 102. Le due cifre finali rappresentano il numero della patch. Ad esempio la versione .NET Core 2.2 può creare versioni come quelle della tabella seguente:

| Modifica                | Runtime di .NET Core | .NET Core SDK (\*) |
|-----------------------|-------------------|-------------------|
| Versione iniziale       | 2.2.0             | 2.2.100           |
| Patch SDK             | 2.2.0             | 2.2.101           |
| Runtime e patch SDK | 2.2.1             | 2.2.102           |
| Modifica di funzionalità nel SDK    | 2.2.1             | 2.2.200           |

(\*) Questo grafico usa il runtime di .NET Core 2,2 come esempio perché un artefatto storico significava il primo SDK per .NET Core 2,1 è 2.1.300. Per altre informazioni, vedere [Scelta della versione di .NET Core](selection.md).

NOTE:

- Se il SDK registra 10 aggiornamenti delle funzionalità prima che sia disponibile un aggiornamento delle funzionalità del runtime, i numeri di versione vengono moltiplicati per 1000 e ad esempio la versione con funzionalità 2.2.900 viene seguita dalla versione 2.2.1000. Non è previsto che si verifichi questa situazione.
- È molto improbabile che vengano rilasciate 99 patch senza il rilascio di una versione con funzionalità. Quando una versione si avvicina a questo numero, forza il rilascio di una versione con funzionalità.

Altri dettagli sono disponibili nella proposta iniziale, nel repository [dotnet/designs](https://github.com/dotnet/designs/pull/29).

## <a name="semantic-versioning"></a>Versionamento semantico

Il *runtime* di .NET Core aderisce a grandi linee allo standard [Semantic Versioning (SemVer)](https://semver.org/) e adotta l'uso del versionamento `MAJOR.MINOR.PATCH`, usando le varie parti del numero di versione per descrivere il grado e il tipo di modifica.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

Le parti facoltative `PRERELEASE` e `BUILDNUMBER` non fanno mai parte delle versioni supportate e sono disponibili solo nelle compilazioni notturne, nelle build locali compilate da destinazioni di origine e nelle versioni in anteprima non supportate.

### <a name="understand-runtime-version-number-changes"></a>Informazioni sulle modifiche al numero di versione del runtime

`MAJOR` viene incrementato quando:

- Si apportano modifiche significative al prodotto o lo sviluppo dello stesso prende una nuova direzione.
- Vengono effettuate modifiche importanti. L'accettazione di modifiche importanti è soggetta a una valutazione approfondita.
- Una versione precedente non è più supportata.
- Viene adottata una versione `MAJOR` più recente di una dipendenza esistente.

`MINOR` viene incrementato quando:

- Viene aggiunta la superficie di attacco dell'API pubblica.
- Viene aggiunto un nuovo comportamento.
- Viene adottata una versione `MINOR` più recente di una dipendenza esistente.
- Viene introdotta una nuova dipendenza.

`PATCH` viene incrementato quando:

- Vengono eseguite correzioni di bug.
- Viene aggiunto il supporto per una piattaforma più recente.
- Viene adottata una versione `PATCH` più recente di una dipendenza esistente.
- Qualsiasi altra modifica non corrisponde a uno dei casi precedenti.

Quando sono presenti più modifiche, viene incrementato l'elemento maggiore interessato da singole modifiche e quelli che seguono vengono reimpostati a zero. Ad esempio, quando `MAJOR` viene incrementato, `MINOR` e `PATCH` vengono reimpostati su zero. Quando `MINOR` viene incrementato, `PATCH` viene reimpostato su zero mentre `MAJOR` viene lasciato invariato.

## <a name="version-numbers-in-file-names"></a>Numeri di versione nei nomi dei file

I file scaricati per .NET Core includono la versione, ad esempio `dotnet-sdk-2.1.300-win10-x64.exe`.

### <a name="preview-versions"></a>Versioni di anteprima

Le versioni di anteprima hanno un `-preview[number]-([build]|"final")` aggiunto alla versione. Ad esempio `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Versioni di manutenzione

Dopo l'uscita di una versione, i rami generalmente interrompono la produzione di build giornaliere e avviano la produzione di build di manutenzione. Nelle versioni di manutenzione c'è l'aggiunta di `-servicing-[number]`. Ad esempio `2.0.1-servicing-006924`.

## <a name="relationship-to-net-standard-versions"></a>Relazione con le versioni di .NET Standard

.NET Standard è un assembly di riferimento .NET. Esistono più implementazioni specifiche per ogni piattaforma. L'assembly di riferimento contiene la definizione delle API .NET che fanno parte di una determinata versione di .NET Standard. Ogni implementazione adempie al contratto .NET Standard nella piattaforma specifica. Per altre informazioni vedere l'articolo su [.NET Standard](../../standard/net-standard.md) nella Guida di .NET.

L'assembly di riferimento .NET Standard usa uno schema di controllo delle versioni `MAJOR.MINOR`. Il livello `PATCH` non è utile per .NET Standard, perché espone solo una specifica di API (nessuna implementazione) e, per definizione, qualsiasi modifica apportata all'API rappresenterebbe una modifica al set di funzionalità e di conseguenza una nuova versione di `MINOR`.

Le implementazioni in ogni piattaforma possono essere aggiornate, in genere nel quadro del rilascio della piattaforma e pertanto in modo non evidente per i programmatori che usano .NET Standard su tale piattaforma.

Ogni versione di .NET Core implementa una versione di .NET Standard. L'implementazione di una versione di .NET Standard implica il supporto delle versioni precedenti di .NET Standard. Le versioni di .NET Standard e .NET Core sono indipendenti tra loro. Il fatto che .NET Core 2.0 implementi .NET Standard 2.0 è una coincidenza. Anche .NET Core 2.1 implementa .NET Standard 2.0. .NET Core supporterà le versioni future di .NET Standard man mano che diventano disponibili.

| .NET Core | .NET Standard |
|-----------|---------------|
| 1.0       | Fino alla 1.6     |
| 2.0       | Fino alla 2.0     |
| 2.1       | Fino alla 2.0     |
| 2.2       | Fino alla 2.0     |
| 3.0       | fino a 2,1     |

## <a name="see-also"></a>Vedere anche

- [Framework di destinazione](../../standard/frameworks.md)
- [Pacchetti di distribuzione di .NET Core](../build/distribution-packaging.md)
- [.NET Core Support Lifecycle Fact Sheet (Scheda informativa sul ciclo di supporto per .NET Core)](https://dotnet.microsoft.com/platform/support/policy)
- [Associazione della versione di .NET core 2+](https://github.com/dotnet/designs/issues/3)
- [Immagini Docker per .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/)
