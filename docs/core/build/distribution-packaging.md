---
title: Creazione di pacchetti di distribuzione di .NET Core
description: Informazione su come creare pacchetti e assegnare nome e versione ai pacchetti per la distribuzione di .NET Core.
keywords: .NET, .NET Core, codice sorgente, compilazione
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 71b9d722-c5a8-4271-9ce1-d87e7ae2494d
ms.workload: dotnetcore
ms.openlocfilehash: 9f5cd2f7c4fec553dfdfaf1765663b6896b3061d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/23/2017
---
# <a name="net-core-distribution-packaging"></a>Creazione di pacchetti di distribuzione di .NET Core

Dato che .NET Core è disponibile in un numero sempre maggiore di piattaforme, è utile imparare a creare un pacchetto e assegnarvi un nome e una versione. In questo modo, coloro che si occupano della manutenzione dei pacchetti possono garantire un'esperienza coerente indipendentemente dalla piattaforma scelta dagli utenti per l'esecuzione di .NET.

## <a name="net-core-components"></a>Componenti di .NET Core

.NET Core è costituito da tre parti principali che devono essere incluse nel pacchetto:

1. **Host** (noto anche come "muxer") con due ruoli distinti: attivare un runtime per avviare un'applicazione e attivare un SDK per inviare comandi all'applicazione. L'host è costituito da un eseguibile nativo (`dotnet.exe`) e dalle librerie di criteri di supporto (installate in `host/fxr`). È compilato dal codice nel repository [`dotnet/core-setup`](https://github.com/dotnet/core-setup/). Esiste in genere un solo host in un determinato computer, anche se non si tratta di un requisito vincolante.
2. **Il framework** è costituito da un runtime e dalla librerie gestite di supporto. Il framework può essere installato come parte di un'applicazione o come framework condiviso in una posizione centrale, riutilizzabile da più applicazioni. In un determinato computer può essere installato un numero qualsiasi di framework condivisi. I framework condivisi si trovano in `shared/Microsoft.NETCore.App/<version>`. L'host esegue il roll forward tra le versioni di patch. Se un'applicazione è destinata a `Microsoft.NETCore.App` 1.0.0 ed è presente solo la versione 1.0.4, l'app viene avviata per la versione 1.0.4.
3. **L'SDK** (noto anche come "strumenti") è un set di strumenti gestiti che possono essere usati per scrivere e compilare applicazioni e librerie .NET Core. L'SDK include l'interfaccia della riga di comando, MSBuild e le attività e le destinazioni di compilazione associate, NuGet, nuovi modelli di progetto e così via. È possibile avere più SDK in un computer (ad esempio, per compilare progetti che richiedono esplicitamente una versione precedente), ma si consiglia di usare gli strumenti più recenti rilasciati.

## <a name="recommended-package-names"></a>Nomi di pacchetto consigliati

Le linee guida seguenti corrispondono alle raccomandazioni Microsoft per i nomi di pacchetti. Un responsabile della manutenzione dei pacchetti può scegliere soluzioni divergenti per vari motivi, come consuetudini diverse per la distribuzione specifica di destinazione.

### <a name="minimum-package-set"></a>Set minimo del pacchetto

* `dotnet-runtime-[major].[minor]`: un framework condiviso con la versione specificata (nel sistema di gestione pacchetti deve essere disponibile solo l'ultima versione di patch per una determinata combinazione di versione principale+secondaria). **Dipendenze**: `dotnet-host`
* `dotnet-sdk`: l'SDK più recente. **Dipendenze**: la versione più recente di `dotnet-sdk-[major].[minor]`.
* `dotnet-sdk-[major].[minor]`: l'SDK con la versione specificata. La versione specificata è la versione maggiore inclusa dei framework condivisi inclusi, in modo che gli utenti possano abbinare facilmente un SDK a un framework condiviso. **Dipendenze**: `dotnet-host`, uno o più `dotnet-runtime-[major].[minor]` (uno dei runtime viene usato dal codice dell'SDK stesso, gli altri sono disponibili per gli utenti come destinazione per compilazione ed esecuzione).
* `dotnet-host`: l'host più recente.

#### <a name="preview-versions"></a>Versioni di anteprima

I responsabili della manutenzione dei pacchetti possono decidere di includere versioni di anteprima del framework condiviso e dell'SDK. Queste anteprime non dovrebbero mai essere incluse nel pacchetto `dotnet-sdk` senza versione, ma possono essere rilasciate come pacchetti con versione, aggiungendo un indicatore di anteprima nelle sezioni della versione principale e secondaria del nome. Ad esempio, potrebbe esistere un pacchetto `dotnet-sdk-2.0-preview-final`.

### <a name="optional-additional-packages"></a>Pacchetti aggiuntivi facoltativi

Alcuni responsabili potrebbero scegliere di includere pacchetti aggiuntivi, ad esempio:

* `dotnet-lts`: la versione più recente con supporto a lungo termine (LTS, Long-Term Support) del framework condiviso. I [rami di rilascio LTS e Current](~/docs/core/versions/lts-current.md) corrispondono alle diverse cadenze di rilascio di .NET Core. Gli utenti possono scegliere uno dei rami di rilascio, in base alla frequenza con cui intendono eseguire gli aggiornamenti. Questo concetto è correlato anche ai livelli di supporto, quindi potrebbe avere più o meno senso a seconda della distribuzione presa in considerazione.

## <a name="disk-layout"></a>Layout su disco

Quando si installano pacchetti .NET Core, la posizione relativa delle destinazioni su disco è rilevante.
L'host `dotnet.exe` deve essere posizionato a fianco delle cartelle `sdk` e `shared` che contengono il contenuto con versione dei pacchetti dell'SDK `dotnet-sdk` e dei pacchetti dei framework condivisi `dotnet-runtime`.

Il layout su disco dei file e delle directory all'interno dei pacchetti è sottoposto a controllo delle versioni. Questo significa che con l'aggiornamento alla versione più recente di `dotnet-runtime`, la nuova versione viene installata a fianco delle versioni precedenti, con minori possibilità di compromettere il funzionamento delle applicazioni esistenti in seguito all'aggiornamento del pacchetto. Gli aggiornamenti dei pacchetti non devono rimuovere le versioni precedenti.

## <a name="update-policies"></a>Criteri di aggiornamento

Quando si esegue un'operazione `update`, il comportamento di ogni pacchetto è il seguente:

* `dotnet-runtime-[major].[minor]`: le nuove versioni di patch aggiornano il pacchetto, ma le nuove versioni principali o secondarie sono pacchetti separati.
* `dotnet-sdk`: `update` esegue il roll forward delle versioni principale, secondaria e di patch.
* `dotnet-sdk-[major].[minor]`: le nuove versioni di patch aggiornano il pacchetto, ma le nuove versioni principali o secondarie sono pacchetti separati.
* `dotnet-lts`: `update` esegue il roll forward delle versioni principale, secondaria e di patch.

In questo argomento sono state presentate le raccomandazioni di Microsoft per la creazione di pacchetti .NET Core. Per ogni distribuzione è comunque possibile scegliere quali versioni offrire e quando. Ad esempio, per una distribuzione in cui la stabilità è più importante dell'aggiornamento, si potrebbe scegliere di rilasciare solo le versioni associate al ramo di rilascio LTS.