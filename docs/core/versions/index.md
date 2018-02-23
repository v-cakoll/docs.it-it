---
title: Controllo delle versioni di .NET Core
description: Informazioni sul funzionamento del controllo delle versioni di .NET Core.
author: bleroy
ms.author: mairaw
ms.date: 02/13/2018
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: f6f684b1-1d2c-4105-8376-7c1959e23803
ms.workload:
- dotnetcore
ms.openlocfilehash: 70c7f179f3451e51d5ab383cde80959a69f959a1
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2018
---
# <a name="net-core-versioning"></a>Controllo delle versioni di .NET Core

.NET core è costituito da [pacchetti NuGet](../packages.md), strumenti e framework che vengono distribuiti come un'unità. Ciascuno di questi livelli di piattaforma può essere sottoposto a controllo delle versioni separatamente, consentendo una maggiore flessibilità. Anche se esiste una notevole flessibilità nel controllo delle versioni in questo contesto, è tuttavia presente la tendenza a definire una versione della piattaforma come unità per rendere il prodotto più facile da comprendere.

Questo articolo intende chiarire come avviene il controllo delle versioni dell'SDK. di NET Core e di runtime.

Esistono numerose parti mobili che eseguono il controllo delle versioni in modo indipendente in .NET Core. Tuttavia, a partire da .NET Core 2.0, è semplice comprendere il numero di versione principale che tutti gli utenti sono in grado di comprendere come *la* versione di ".NET Core" nel suo complesso. Il resto di questo documento viene inserito nei dettagli del controllo delle versioni di tutte le parti. Questi dettagli possono essere importanti se non si ha una gestore di pacchetti, ad esempio.

> [!IMPORTANT]
> I dettagli sul controllo delle versioni illustrati in questo argomento non si applicano alla versione corrente di .NET Core SDK e del relativo runtime.
> Lo schema della versione cambierà nelle versioni future. La proposta attuale è disponibile nel repository [dotnet/designs](https://github.com/dotnet/designs/pull/29).

## <a name="versioning-details"></a>Dettagli del controllo delle versioni

Con .NET Core 2.0, i download mostrano un solo numero di versione nel nome del file. I numeri di versione seguenti sono stati unificati:

* Il framework condiviso e il runtime associato.
* L'SDK di .NET Core e l'interfaccia della riga di comando di .NET Core associata.
* Il metapacchetto `Microsoft.NETCore.App`.

L'uso di un numero di versione singolo rende più semplice per gli utenti scoprire quale versione dell'SDK installare nei propri computer di sviluppo e quale dovrebbe essere la versione corrispondente del framework condiviso al momento di eseguire il provisioning di un ambiente di produzione. Quando si scarica un SDK o un runtime, il numero di versione che viene visualizzato deve essere lo stesso.

### <a name="installers"></a>Programmi di installazione

Con .NET Core 2.0, i download per le [build giornaliere](https://github.com/dotnet/core-setup#daily-builds) e le [versioni](https://www.microsoft.com/net/download/core) sono conformi a un nuovo schema di denominazione più facile da comprendere.
Anche l'interfaccia utente del programma di installazione in questi download è stata modificata per presentare chiaramente i nomi e le versioni dei componenti da installare. In particolare, i titoli mostrano ora lo stesso numero di versione che è nel nome del file del download.

#### <a name="file-name-format"></a>Formato del nome del file

`[product]-[component]-[major].[minor].[patch]-[previewN]-[optional build #]-[rid].[file ext]`

Ecco alcuni esempi di tale formato:

```
dotnet-runtime-2.0.4-macos.10.12-x64.pkg            # Mac runtime installer
dotnet-sdk-2.0.4-win10-x64.exe                      # Windows SDK installer
dotnet-sdk-2.0.4-fedora.24-x64.tar.gz               # Fedora 24 binary archive

#Ubuntu file set needed for the SDK
dotnet-host-2.0.4-ubuntu.16.04-x64.deb              # Host / muxer and host policy
dotnet-runtime-2.0.4-ubuntu.16.04-x64.deb           # runtime
dotnet-sdk-2.0.4-ubuntu.16.04-x64.deb               # SDK tools
```

Il formato è leggibile e mostra chiaramente il materiale di cui si sta eseguendo il download, di quale versione si tratta e dove è possibile usarlo. Il nome del pacchetto di runtime include `runtime` e l'SDK include `SDK`.

#### <a name="ui-string-format"></a>Formato della stringa dell'interfaccia utente

Tutte le descrizioni del sito Web e le stringhe dell'interfaccia utente nei programmi di installazione vengono mantenute coerenti, semplici e accurate. La tabella seguente mostra alcuni esempi:

| Installer | Titolo finestra                          | Altri contenuti nel programma di installazione | Cosa è installato                               |
| :--       | :--                                   | :--                        | :--                                             |
| SDK       | Programma di installazione dell'SDK di .NET Core 2.0 (x64)     | SDK di .NET Core 2.0.4        | .NET Core 2.0.4 Tools + .NET Core 2.0.4 Runtime |
| Runtime   | Programma di installazione di .NET Core 2.0 Runtime (x64) | .NET Core 2.0.4 Runtime    | .NET Core 2.0.4 Runtime                         |

Le versioni di anteprima presentano solo piccole differenze:

| Installer | Titolo finestra                                    | Altri contenuti nel programma di installazione        | Cosa è installato                                                   |
| :--       | :--                                             | :--                               | :--                                                                 |
| SDK       | Programma di installazione dell'SDK di .NET Core 2.0 Preview 1 (x64)     | SDK di .NET Core 2.0.0 Preview 1     | .NET Core 2.0.0 Preview 1 Tools + .NET Core 2.0.0 Preview 1 Runtime |
| Runtime   | Programma di installazione di .NET Core 2.0 Preview 1 Runtime (x64) | .NET Core 2.0.0 Preview 1 Runtime | .NET Core 2.0.0 Preview 1 Runtime                                   |

Può capitare che una versione dell'SDK contenga più di una versione del runtime. In questo caso, il programma di installazione UX è simile al seguente (solo la versione dell'SDK viene visualizzata e le versioni installate di Runtime vengono visualizzate nella pagina di riepilogo alla fine del processo di installazione su Windows e Mac):

| Installer | Titolo finestra                      | Altri contenuti nel programma di installazione                                   | Cosa è installato                                                         |
| :--       | :--                               | :--                                                          | :--                                                                       |
| SDK       | Programma di installazione dell'SDK di .NET Core 2.1 (x64) | SDK di .NET Core 2.1.1 <br> .NET Core 2.1.1 Runtime <br> .NET Core 2.0.6 Runtime | .NET Core 2.1.1 Tools + .NET Core 2.1.1 Runtime + .NET Core 2.0.6 Runtime |

È anche possibile che gli strumenti di .NET Core debbano essere aggiornati, senza modifiche al runtime. In tal caso, la versione dell'SDK viene aumentata (ad esempio, a 2.1.2) e quindi Runtime rileva la volta successiva in cui aumenta (ad esempio, sia Runtime che l'SDK passano la volta successiva a 2.1.3).

### <a name="package-managers"></a>Gestione pacchetti

.NET Core può essere distribuito da altre entità diverse da Microsoft. In particolare, i proprietari della distribuzione di Linux e i responsabili della manutenzione dei pacchetti possono aggiungere pacchetti .NET Core alla gestione dei pacchetti. Per consigli su come questi pacchetti devono essere denominati e su come deve essere eseguito il controllo delle versioni, vedere [.NET Core distribution packaging](../build/distribution-packaging.md) (Pacchetti di distribuzione di .NET Core).

#### <a name="minimum-package-set"></a>Set minimo del pacchetto

* `dotnet-runtime-[major].[minor]`: un runtime con la versione specificata (nel sistema di gestione pacchetti deve essere disponibile solo l'ultima versione di patch per una determinata combinazione di versione principale+secondaria). Le nuove versioni di patch aggiornano il pacchetto, ma le nuove versioni principali o secondarie sono pacchetti separati.

  **Dipendenze**:`dotnet-host`

* `dotnet-sdk`: l'SDK più recente. `update`: esegue il roll forward delle versioni principale, secondaria e di patch.

  **Dipendenze**: la versione più recente di `dotnet-sdk-[major].[minor]`.

* `dotnet-sdk-[major].[minor]`: l'SDK con la versione specificata. La versione specificata è la versione maggiore inclusa dei framework condivisi inclusi, in modo che gli utenti possano abbinare facilmente un SDK a un framework condiviso. Le nuove versioni di patch aggiornano il pacchetto, ma le nuove versioni principali o secondarie sono pacchetti separati.

  **Dipendenze**: `dotnet-host`, uno o più `dotnet-runtime-[major].[minor]` (uno di quelli viene usato dal codice dell'SDK stesso, gli altri sono disponibili per gli utenti per la compilazione e l'esecuzione).

* `dotnet-host`: l'host più recente.

##### <a name="preview-versions"></a>Versioni di anteprima

I responsabili della manutenzione dei pacchetti possono decidere di includere versioni di anteprima del runtime e dell'SDK. Non includere queste versioni di anteprima nel pacchetto `dotnet-sdk` senza controllo delle versioni, ma è possibile rilasciarle come pacchetti sottoposti a controllo delle versioni, aggiungendo un indicatore di anteprima nelle sezioni della versione principale e secondaria del nome. Ad esempio, potrebbe esistere un pacchetto `dotnet-sdk-2.0-preview1-final`.

### <a name="docker"></a>Docker

Una convenzione di denominazione di tag Docker generale consiste nell'inserire il numero di versione prima del nome del componente. Questa convenzione può continuare a essere utilizzata. I tag correnti includono solo la versione di Runtime come indicato di seguito.

* 1.0.8-runtime
* 1.0.8-sdk
* 2.0.4-runtime
* 2.0.4-sdk
* 2.1.1-runtime
* 2.1.1-sdk

I tag di SDK devono essere aggiornati per rappresentare la versione dell'SDK invece che di Runtime.

È anche possibile che gli strumenti dell'interfaccia della riga di comando di .NET Core (inclusi nell'SDK) vengano corretti ma che il runtime rimanga quello esistente. In tal caso, la versione dell'SDK viene aumentata (ad esempio a 2.1.2) e il Runtime viene aggiornato al successivo rilascio (ad esempio, la volta successiva sia il Runtime che l'SDK vengono rilasciati con la versione 2.1.3).

## <a name="semantic-versioning"></a>Versionamento Semantico

.NET Core usa [Versionamento Semantico (SemVer)](http://semver.org/), adottando l'uso del controllo delle versioni `MAJOR.MINOR.PATCH`, usando le diverse parti del numero di versione per descrivere il grado e il tipo di modifica.

```
MAJOR.MINOR.PATCH[-PRERELEASE-BUILDNUMBER]
```

Le parti facoltative `PRERELEASE` e `BUILDNUMBER` non fanno mai parte delle versioni supportate e sono disponibili solo nelle compilazioni notturne, nelle build locali compilate da destinazioni di origine e nelle versioni in anteprima non supportate.

### <a name="how-version-numbers-are-incremented"></a>In che modo vengono incrementati i numeri di versione?

`MAJOR` viene incrementato quando:

- Una versione precedente non è più supportata.
- Viene adottata una versione `MAJOR` più recente di una dipendenza esistente.
- L'impostazione predefinita di un dettaglio di compatibilità viene modificato passando a "off".

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

### <a name="preview-versions"></a>Versioni di anteprima

Le versioni di anteprima hanno un `-preview[number]-([build]|"final")` aggiunto alla versione. Ad esempio `2.0.0-preview1-final`.

### <a name="servicing-versions"></a>Versioni di manutenzione

Dopo l'uscita di una versione, i rami generalmente interrompono la produzione di build giornaliere e avviano la produzione di build di manutenzione. Nelle versioni di manutenzione c'è l'aggiunta di `-servicing-[number]`. Ad esempio `2.0.1-servicing-006924`.

### <a name="lts-vs-current"></a>LTS e Current

Esistono due training delle versioni per .NET Core: supporto a lungo termine (LTS) e Current. Ciò consente agli utenti di selezionare il livello di stabilità e le nuove funzionalità desiderate, mentre sono ancora supportati.

- LTS significa che si ottengono nuove funzionalità meno frequentemente, ma si dispone di una piattaforma più matura. LTS ha anche un periodo più lungo di supporto.
- Current indica che si ottengono nuove funzionalità e API più frequentemente, ma lo svantaggio è che si dispone di un intervallo di tempo minore per installare aggiornamenti, e gli aggiornamenti si verificano più frequentemente. Current è anche completamente supportato, ma il periodo di supporto è inferiore a LTS.

Una versione "Current" può alzarsi di livello a LTS.

"LTS" e "Current" devono essere considerate come etichette che si inseriscono in versioni specifiche per eseguire un'istruzione sul livello di supporto associato.

Per altre informazioni, vedere [.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support) (Scheda informativa sul ciclo di supporto per .NET Core).

## <a name="versioning-scheme-details"></a>Dettagli relativi allo schema del controllo delle versioni

.NET Core è costituito dalle parti seguenti:

- Un host: *dotnet.exe* per le applicazioni dipendenti dal framework o *\<nomeapp>.exe* per le applicazioni indipendenti.
- Un SDK (il set di strumenti necessari sul computer dello sviluppatore, ma non nell'ambiente di produzione).
- Un runtime.
- Un'implementazione di framework condivisa, distribuita sotto forma di pacchetti. La definizione delle versioni avviene in modo indipendente per ciascun pacchetto, in particolare per quanto riguarda le versioni patch.
- Facoltativamente, un set di [metapacchetti](../packages.md) che fa riferimento a pacchetti con granularità fine come unità di cui vengono definite diverse versioni. I metapacchetti possono subire il controllo delle versioni separatamente rispetto a quelle dei pacchetti.

.NET core include anche un set di framework di destinazione (ad esempio, `netstandard` o `netcoreapp`) che rappresentano un set di API progressivamente più ampio, a mano a mano che i numeri della versione vengono incrementati.

### <a name="net-standard"></a>.NET Standard

.NET Standard ha usato uno schema di controllo delle versioni `MAJOR.MINOR`. Il livello `PATCH` non è utile per .NET Standard perché esprime un set di contratti su cui viene eseguita l'iterazione meno frequentemente e che non presenta gli stessi requisiti per il controllo delle versioni di un'implementazione effettiva.

Non vi è alcun accoppiamento reale tra le versioni .NET Standard e le versioni di .NET Core: .NET Core 2.0 implementa .NET 2.0 Standard, ma non c'è garanzia che sulle versioni future di .NET Core verrà eseguito il mapping sulla stessa versione di .NET Standard. .NET Core può spedire le API che non vengono definite da .NET Standard e, di conseguenza, potrebbe spedire nuove versioni senza richiedere un nuovo .NET Standard. .NET standard è anche un concetto che si applica ad altre destinazioni, ad esempio .NET Framework o Mono, anche se il suo inizio coincide con quello di .NET Core.

### <a name="packages"></a>Pacchetti

I pacchetti di libreria hanno un'evoluzione indipendente e anche le relative versioni vengono definite in modo separato. I pacchetti che si sovrappongono ad assembly .NET Framework System\* usano in genere versioni 4.x, in linea con il versionamento di .NET Framework 4.x. Si tratta di una scelta storica. I pacchetti che non si sovrappongono a librerie di .NET Framework, (ad esempio [`System.Reflection.Metadata`](https://www.nuget.org/packages/System.Reflection.Metadata)) partono in genere da 1.0 e incrementano da quest'ultimo il numero di versione.

I pacchetti descritti dalla [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) vengono trattati in modo speciale in quanto costituiscono la base della piattaforma.

Le versioni dei pacchetti di `NETStandard.Library` verranno definite sotto forma di set, dal momento che tra tali pacchetti sono presenti dipendenze a livello di implementazione.

### <a name="metapackages"></a>Metapacchetti

Il controllo delle versioni dei metapacchetti .NET Core è basato sulla versione di .NET Core di cui fanno parte.

Ad esempio, i metapacchetti in .NET Core 2.1.3 devono tutti avere 2.1 come numero di versione `MAJOR` e `MINOR`.

La versione patch per il metapacchetto viene incrementata ogni volta che viene aggiornato un pacchetto di riferimento. Le versioni patch non includeranno una versione aggiornata del framework. Di conseguenza, i metapacchetti non sono strettamente conformi al Versionamento Semantico perché il loro schema di controllo delle versioni non rappresenta il grado di cambiamento dei pacchetti sottostanti, ma principalmente del livello API.

Per .NET Core sono presenti attualmente due metapacchetti principali:

**Microsoft.NETCore.App**

- Versione 1.0 a partire da .NET Core 1.0 (queste versioni corrispondono).
- Viene mappato al framework `netcoreapp`.
- Descrive i pacchetti presenti nella distribuzione .NET Core.

Nota: [`Microsoft.NETCore.Portable.Compatibility`](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) è un altro metapacchetto .NET Core esistente per abilitare la compatibilità con l'implementazione pre-.NET Standard di .NET. Non viene mappato a un framework particolare, motivo per cui le relative versioni vengono definite come quelle di un pacchetto.

**NETStandard.Library**

[`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library) descrive le librerie che fanno parte di [.NET Standard](../../standard/library.md). Si applica a tutte le implementazioni .NET che supportano .NET Standard, ad esempio .NET Framework, .NET Core e Mono.

### <a name="target-frameworks"></a>Framework di destinazione

Le versioni del framework d destinazione vengono aggiornate quando si aggiungono nuove API. Non includono alcun concetto della versione patch, poiché rappresentano la forma dell'API e non problemi di implementazione. Il controllo delle versioni principali e secondarie segue le regole di SemVer specificate in precedenza, e coincide con i numeri `MAJOR` e `MINOR` delle distribuzioni .NET Core che lo implementano.

## <a name="versioning-in-practice"></a>Controllo delle versioni in pratica

Quando si esegue il download di .NET Core, il nome del file scaricato contiene il numero di versione, ad esempio `dotnet-sdk-2.0.4-win10-x64.exe`.

Ogni giorno in GitHub vengono inseriti commit e richieste pull nei repository relativi a .NET Core, con la conseguente generazione di nuove build di diverse librerie. Non è pratico creare nuove versioni pubbliche di .NET Core per ogni modifica. Le modifiche vengono invece aggregate nel corso di un periodo di tempo non determinato (ad esempio mesi o settimane) prima di creare una nuova versione pubblica stabile di .NET Core.

Una nuova versione di .NET Core può implicare quanto segue:

- Nuove versioni dei pacchetti e dei metapacchetti.
- Nuove versioni di diversi framework, presupponendo l'aggiunta di nuove API.
- Nuova versione della distribuzione .NET Core.

### <a name="shipping-a-patch-release"></a>Rilascio di una versione patch

Dopo il rilascio di una versione principale di .NET Core, come la versione 2.0.0, alle librerie .NET Core vengono apportate modifiche a livello di patch per correggere i bug e migliorare le prestazioni e l'affidabilità. Ciò significa che non sono state introdotte nuove API. I diversi metapacchetti vengono aggiornati in modo che facciano riferimento ai pacchetti della libreria .NET Core aggiornati. Le versioni dei metapacchetti vengono definite come aggiornamenti patch (`MAJOR.MINOR.PATCH`). I framework di destinazione non sono mai aggiornati come parte delle versioni di patch. Viene rilasciata una nuova distribuzione di .NET Core con un numero di versione che corrisponde con quello del metapacchetto `Microsoft.NETCore.App`.

### <a name="shipping-a-minor-release"></a>Rilascio di una versione secondaria

Dopo il rilascio di una versione .NET Core con un numero incrementato della versione `MAJOR`, alle librerie .NET Core vengono aggiunte nuove API per abilitare nuovi scenari. I diversi metapacchetti vengono aggiornati in modo che facciano riferimento ai pacchetti della libreria .NET Core aggiornati. Sui metapacchetti viene eseguito il controllo delle versioni come gli aggiornamenti di patch con i numeri delle versioni `MAJOR` e `MINOR` che corrispondono alla nuova versione di framework. Vengono aggiunti nuovi nomi di framework di destinazione con la nuova versione `MAJOR.MINOR` per descrivere le nuove API (ad esempio, `netcoreapp2.1`). Viene rilasciata una nuova distribuzione di .NET Core con un numero di versione corrispondente al metapacchetto `Microsoft.NETCore.App`.

### <a name="shipping-a-major-release"></a>Rilascio di una versione principale

Ogni volta che viene fornita una nuova versione principale di .NET Core, viene incrementato il numero della versione `MAJOR`, e il numero della versione `MINOR` viene reimpostato a zero. La nuova versione principale contiene almeno tutte le API che sono state aggiunte da versioni secondarie dopo la precedente versione principale. Una nuova versione principale deve abilitare nuovi scenari importanti, e può anche rilasciare il supporto per una piattaforma meno recente.

I diversi metapacchetti vengono aggiornati in modo che facciano riferimento ai pacchetti della libreria .NET Core aggiornati. Sul metapacchetto [`Microsoft.NETCore.App`](https://www.nuget.org/packages/Microsoft.NETCore.App) e sul framework di destinazione `netcore` viene eseguito il controllo delle versioni in un aggiornamento principale corrispondente al numero della versione `MAJOR` della nuova versione.

## <a name="see-also"></a>Vedere anche

[Framework di destinazione](../../standard/frameworks.md)  
[Pacchetti di distribuzione di .NET Core](../build/distribution-packaging.md)  
[.NET Core Support Lifecycle Fact Sheet (Scheda informativa sul ciclo di supporto per .NET Core)](https://www.microsoft.com/net/core/support)  
[Associazione della versione di .NET core 2+](https://github.com/dotnet/designs/issues/3)  
