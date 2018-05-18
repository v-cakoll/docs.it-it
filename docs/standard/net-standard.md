---
title: .NET Standard
description: Informazioni su .NET Standard, sulle relative versioni e sulle implementazioni di .NET che le supportano.
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.technology: dotnet-standard
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: 832efe566aaab1e0add687cdb474bacdf5b5d829
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="net-standard"></a>.NET Standard

[.NET Standard](https://github.com/dotnet/standard) è una specifica formale delle API .NET che devono essere disponibili in tutte le implementazioni di .NET. La motivazione alla base di .NET Standard è l'esigenza di creare maggiore uniformità nell'ecosistema .NET. Lo standard [ECMA 335](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) continua ad assicurare uniformità riguardo al comportamento delle implementazioni di .NET, ma non esiste una specifica simile per le librerie di classi base .NET per le implementazioni delle librerie .NET. 

.NET Standard abilita gli scenari chiave seguenti: 

- Definisce un set uniforme di API BCL per tutte le implementazioni di .NET da implementare, indipendentemente dal carico di lavoro.
- Consente agli sviluppatori di creare librerie portabili utilizzabili in più implementazioni di .NET usando questo stesso set di API.
- Riduce o addirittura elimina la compilazione condizionale del codice sorgente condiviso a causa di API .NET (solo per API del sistema operativo).

Le diverse implementazioni di .NET specificano come destinazione determinate versioni di .NET Standard. Ogni versione dell'implementazione di .NET annuncia la versione .NET Standard più recente supportata, implicando che sono supportate anche le versioni precedenti. NET Framework 4.6, ad esempio, implementa .NET Standard 1.3: questo significa che espone tutte le API definite nelle versioni di .NET Standard da 1.0 a 1.3. Analogamente, .NET Framework 4.6.1 implementa .NET Standard 1.4, mentre .NET Core 1.0 implementa .NET Standard 1.6.

## <a name="net-implementation-support"></a>Supporto per le implementazioni di .NET

La tabella seguente elenca tutte le versioni di .NET Standard e le piattaforme supportate:

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

Per trovare la versione più recente di .NET Standard che è possibile definire come destinazione, eseguire le operazioni seguenti:
1. Individuare la riga che indica l'implementazione di .NET usata per l'esecuzione.
2. All'interno della riga, individuare la colonna che indica la versione in uso a partire da destra verso sinistra.
3. L'intestazione di colonna indica la versione di .NET Standard supportata dall'attuale destinazione (e le eventuali versioni precedenti di .NET Standard ugualmente supportate).
4. Ripetere questo processo per ogni piattaforma da definire come destinazione. Se si hanno più piattaforme di destinazione, usare la versione inferiore tra quelle disponibili. Ad esempio, se si vuole procedere all'esecuzione in .NET Framework 4.5 e .NET Core 1.0, la versione .NET Standard superiore che è possibile usare è .NET Standard 1.1.

### <a name="which-net-standard-version-to-target"></a>Quale versione di .NET Standard definire come destinazione

Quando si sceglie una versione di .NET Standard, è necessario prendere in considerazione il seguente compromesso:

- Quanto più alto è il numero di versione, maggiore sarà il numero delle API disponibili.
- Quanto più basso è il numero di versione, maggiore sarà il numero delle piattaforme che la implementano.

In generale, è consigliabile avere come destinazione la versione di .NET Standard *più bassa* possibile. Pertanto, dopo avere individuato la versione di .NET Standard più alta che è possibile avere come destinazione, seguire questi passaggi:
1. Definire come destinazione la versione immediatamente precedente di .NET Standard e compilare il progetto.
2. Se il progetto viene compilato correttamente, ripetere il passaggio 1. In caso contrario, definire come destinazione la versione immediatamente successiva che sarà la versione da usare.

### <a name="net-standard-versioning-rules"></a>Regole per il controllo delle versioni di .NET standard

Esistono due regole principali per il controllo delle versioni:

- Additive: le versioni di .NET Standard sono cerchi concentrici da un punto di vista logico, ovvero le versioni successive includono tutte le API delle versioni precedenti. Non vengono apportate modifiche importanti tra una versione e l'altra.
- Non modificabili: una volta fornite, le versioni di .NET Standard sono bloccate. Le nuove API saranno rese prima disponibili in implementazioni di .NET specifiche, ad esempio .NET Core. Se la commissione di esame di .NET Standard ritiene che le nuove API debbano essere rese disponibili universalmente, verranno aggiunte in una nuova versione di .NET Standard.

## <a name="comparison-to-portable-class-libraries"></a>Confronto con le librerie di classi portabili

.NET Standard sostituisce le [librerie di classi portabili](./cross-platform/cross-platform-development-with-the-portable-class-library.md). .NET Standard migliora l'esperienza di creazione delle librerie portabili curando una BCL standard e assicurando di conseguenza una maggiore uniformità tra le implementazioni di .NET. Una libreria che ha come destinazione .NET Standard è una libreria di classi portabile o una "libreria di classi portabile basata su .NET Standard". Le librerie di classi portabili esistenti sono "librerie di classi portabili basate sul profilo".

.NET Standard e i profili delle librerie di classi portabili sono stati creati per scopi simili, ma presentano differenze significative.

Analogie:

- Definisce le API che possono essere usate per la condivisione di codice binario.

Differenze:

- .NET Standard è un set curato di API, mentre i profili delle librerie di classi portabili sono definiti da intersezioni delle piattaforme esistenti.
- La definizione delle versioni di .NET Standard è lineare, mentre quella dei profili delle librerie di classi portabili non lo è.
- I profili delle librerie di classi portabili rappresentano piattaforme Microsoft, mentre .NET Standard è indipendente dalla piattaforma.

## <a name="specification"></a>Specifica

La specifica di .NET Standard è un set standardizzato di API. La specifica viene gestita dagli implementatori di .NET, in particolare Microsoft (sono inclusi .NET Framework, .NET Core e Mono) e Unity. Un processo pubblico di commenti e suggerimenti è parte integrante della creazione di nuove versioni di .NET Standard tramite [GitHub](https://github.com/dotnet/standard).

### <a name="official-artifacts"></a>Elementi ufficiali

La specifica ufficiale è un insieme di file con estensione cs che definiscono le API che sono parte dello standard. La [directory ref](https://github.com/dotnet/standard/tree/master/netstandard/ref) nel [repository dotnet/standard](https://github.com/dotnet/standard) definisce le API di .NET Standard.

Il metapacchetto [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([origine](https://github.com/dotnet/standard/blob/master/netstandard/pkg/NETStandard.Library.dependencies.props)) descrive il set di librerie che definiscono (in parte) una o più versioni di .NET Standard.

Un componente specifico, ad esempio System.Runtime, descrive quanto segue:

- Parte di .NET Standard (solo il relativo ambito).
- Diverse versioni di .NET Standard per tale ambito.

Vengono forniti elementi derivati per facilitare le operazioni di lettura e abilitare alcuni scenari di sviluppo (ad esempio l'uso di un compilatore).

- [Elenco di API in markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Assembly di riferimento, distribuiti come [pacchetti NuGet](../core/packages.md) e utilizzati come riferimento dal metapacchetto [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Rappresentazione dei pacchetti

Il principale veicolo di distribuzione degli assembly di riferimento di .NET Standard sono i [pacchetti NuGet](../core/packages.md). Le implementazioni vengono fornite in molti modi diversi, appropriati per ogni implementazione di .NET.

I pacchetti NuGet hanno come destinazione uno o più [framework](frameworks.md). I pacchetti di .NET Standard hanno come destinazione il framework ".NET Standard". È possibile definire come destinazione il framework .NET Standard usando il `netstandard` [TFM (Target Framework Moniker) compatto](frameworks.md) (ad esempio `netstandard1.4`). Le librerie da eseguire su più runtime devono avere come destinazione questo framework. 

Il metapacchetto `NETStandard.Library` fa riferimento al set completo di pacchetti NuGet che definiscono .NET Standard.  Il modo più comune di definire `netstandard` come destinazione è fare riferimento a questo metapacchetto. Questo metapacchetto descrive e fornisce l'accesso alle circa 40 librerie .NET e alle API associate che definiscono .NET Standard. Per accedere ad API aggiuntive, è possibile fare riferimento ad altri pacchetti che hanno come destinazione `netstandard`. 

### <a name="versioning"></a>Controllo delle versioni

La specifica non è singola, ma costituisce un set di API a crescita incrementale e con definizione lineare delle versioni. La prima versione dello standard definisce un set di dati di riferimento delle API. Le versioni successive aggiungono nuove API ed ereditano quelle definite dalle versioni precedenti. Non esiste alcuna norma stabilita per la rimozione di API dallo standard.

.NET Standard non è specifico di alcuna implementazione di .NET e non corrisponde allo schema di numerazione delle versioni di nessuno di questi runtime.

Le API aggiunte a una delle implementazioni (ad esempio, .NET Framework, .NET Core e Mono) possono essere prese in considerazione per l'aggiunta alla specifica, in particolare se sono state progettate per essere API fondamentali. Le nuove [versioni di .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md) vengono create sulla base delle versioni delle implementazioni di .NET, consentendo di definire come destinazione nuove API da una libreria di classi portabile .NET Standard. I meccanismi di versionamento sono descritti in modo più dettagliato nell'articolo [.NET Core Versioning](../core/versions/index.md) (Versionamento di .NET Core).

Il controllo delle versioni di .NET Standard è importante per l'uso. Data una versione di .NET Standard, è possibile usare librerie che hanno come destinazione la stessa versione o versioni precedenti. L'approccio seguente descrive il flusso di lavoro per l'uso di librerie di classi portabili di .NET Standard, in particolare per la definizione di .NET Standard come destinazione.

- Selezionare una versione di .NET Standard da usare per la libreria di classi portabile.
- Usare librerie che dipendono dalla stessa versione di .NET Standard o da versioni precedenti.
- Se viene individuata una libreria che dipende da una versione successiva di .NET Standard, è necessario adottare la stessa versione oppure decidere di non usare tale libreria.

### <a name="pcl-compatibility"></a>Compatibilità della libreria di classi portabile

.NET Standard è compatibile con un sottoinsieme di profili delle librerie di classi portabili. Le versioni 1.0, 1.1 e 1.2 di .NET Standard si sovrappongono a un set di profili delle librerie di classi portabili. Questa sovrapposizione è stata creata per due motivi:

- Consentire alle librerie di classi portabili basate su .NET Standard di fare riferimento a librerie di classi portabili basate sul profilo.
- Consentire alle librerie di classi portabili basate sul profilo di essere incluse in un pacchetto come librerie di classi portabili basate su .NET Standard.

La compatibilità delle librerie di classi portabili basate sul profilo è fornita dal pacchetto NuGet [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility). Questa dipendenza è obbligatoria quando si fa riferimento a pacchetti NuGet contenenti librerie di classi portabili basate sul profilo.

Le librerie di classi portabili basate sul profilo inserite in un pacchetto come `netstandard` sono più semplici da usare rispetto alle librerie di classi portabili basate sul profilo in pacchetti generici. `netstandard` è un pacchetto compatibile con gli utenti esistenti.

Di seguito è riportato il set di profili delle librerie di classi portabili compatibili con .NET Standard: 

| Profilo PCL | .NET Standard | Piattaforme PCL
|:-----------:|:-------------:|------------------------------------------------------------------------------
| Profile7    | 1.1           | .NET Framework 4.5, Windows 8
| Profile31   | 1.0           | Windows 8.1, Silverlight per Windows Phone 8.1
| Profile32   | 1.2           | Windows 8.1, Windows Phone 8.1
| Profile44   | 1.2           | .NET Framework 4.5.1, Windows 8.1
| Profile49   | 1.0           | .NET Framework 4.5, Silverlight per Windows Phone 8
| Profile78   | 1.0           | .NET Framework 4.5, Windows 8, Silverlight per Windows Phone 8
| Profile84   | 1.0           | Windows Phone 8.1, Silverlight per Windows Phone 8.1
| Profile111  | 1.1           | .NET framework 4.5, Windows 8, Windows Phone 8.1
| Profile151  | 1.2           | .NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1
| Profile157  | 1.0           | Windows 8.1, Windows Phone 8.1, Silverlight per Windows Phone 8.1
| Profile259  | 1.0           | .NET Framework 4.5, Windows 8, Windows Phone 8.1, Silverlight per Windows Phone 8


## <a name="targeting-net-standard"></a>Definizione di .NET Standard come destinazione

È possibile [creare librerie .NET Standard](../core/tutorials/libraries.md) usando una combinazione del framework `netstandard` e del metapacchetto NETStandard.Library. Sono disponibili esempi della [definizione di .NET Standard come destinazione con strumenti .NET Core](../core/packages.md).

## <a name="see-also"></a>Vedere anche
[.NET Standard Versions](https://github.com/dotnet/standard/blob/master/docs/versions.md) (Versioni di .NET Standard)
