---
title: .NET Standard
description: Informazioni su .NET Standard, sulle relative versioni e sulle implementazioni di .NET che le supportano.
author: mairaw
ms.author: mairaw
ms.date: 09/23/2019
ms.technology: dotnet-standard
ms.custom: updateeachrelease
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: 6a4406775056b76dfa789911b8bb14e84dbc8eea
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75738656"
---
# <a name="net-standard"></a>.NET Standard

[.NET standard](https://github.com/dotnet/standard) è una specifica formale delle API .NET che devono essere disponibili in tutte le implementazioni di .NET. La motivazione alla base .NET Standard è la definizione di una maggiore uniformità nell'ecosistema .NET. Lo standard [ECMA 335](https://github.com/dotnet/runtime/blob/master/docs/project/dotnet-standards.md) continua ad assicurare uniformità riguardo al comportamento delle implementazioni di .NET, ma non esiste una specifica simile per le librerie di classi base .NET per le implementazioni delle librerie .NET.

.NET Standard Abilita gli scenari principali seguenti:

- Definisce un set uniforme di API BCL per tutte le implementazioni di .NET da implementare, indipendentemente dal carico di lavoro.
- Consente agli sviluppatori di creare librerie portabili utilizzabili in più implementazioni di .NET usando questo stesso set di API.
- Riduce o addirittura elimina la compilazione condizionale del codice sorgente condiviso a causa di API .NET (solo per API del sistema operativo).

Le diverse implementazioni di .NET specificano come destinazione determinate versioni di .NET Standard. Ogni versione dell'implementazione di .NET annuncia la versione .NET Standard più recente supportata, implicando che sono supportate anche le versioni precedenti. Ad esempio, .NET Framework 4,6 implementa .NET Standard 1,3, il che significa che espone tutte le API definite in .NET Standard versioni da 1,0 a 1,3. Analogamente, .NET Framework 4.6.1 implementa .NET Standard 1,4, mentre .NET Core 1,0 implementa .NET Standard 1,6.

## <a name="net-implementation-support"></a>Supporto per le implementazioni di .NET

Nella tabella seguente sono riportate le versioni **minime** della piattaforma che supportano ogni versione di .NET Standard. Ciò significa che le versioni successive di una piattaforma elencata supportano anche la versione di .NET Standard corrispondente. Ad esempio, .NET Core 2.2 supporta .NET Standard 2.0 e versioni precedenti.

[!INCLUDE [net-standard-table](../../includes/net-standard-table.md)]

Per trovare la versione più recente di .NET Standard che è possibile definire come destinazione, eseguire le operazioni seguenti:

1. Individuare la riga che indica l'implementazione di .NET usata per l'esecuzione.
2. All'interno della riga, individuare la colonna che indica la versione in uso a partire da destra verso sinistra.
3. L'intestazione colonna indica la versione di .NET Standard supportata dall'attuale destinazione. È anche possibile impostare il supporto di qualsiasi versione di .NET Standard inferiore. Anche le versioni di .NET Standard superiori supporteranno l'implementazione.
4. Ripetere questo processo per ogni piattaforma da definire come destinazione. Se si hanno più piattaforme di destinazione, usare la versione inferiore tra quelle disponibili. Ad esempio, se si vuole procedere all'esecuzione in .NET Framework 4.5 e .NET Core 1.0, la versione .NET Standard superiore che è possibile usare è .NET Standard 1.1.

### <a name="which-net-standard-version-to-target"></a>Quale versione di .NET Standard definire come destinazione

Quando si sceglie una versione di .NET Standard, è necessario prendere in considerazione il seguente compromesso:

- Quanto più alto è il numero di versione, maggiore sarà il numero delle API disponibili.
- Quanto più basso è il numero di versione, maggiore sarà il numero delle piattaforme che la implementano.

In generale, è consigliabile avere come destinazione la versione di .NET Standard *più bassa* possibile. Pertanto, dopo avere individuato la versione di .NET Standard più alta che è possibile avere come destinazione, seguire questi passaggi:

1. Definire come destinazione la versione immediatamente precedente di .NET Standard e compilare il progetto.
2. Se il progetto viene compilato correttamente, ripetere il passaggio 1. In caso contrario, definire come destinazione la versione immediatamente successiva che sarà la versione da usare.

Tuttavia, la definizione di versioni precedenti di .NET Standard come destinazione introduce un numero di dipendenze di supporto. Se il progetto è destinato a .NET Standard 1.x, è consigliabile definire *anche* .NET Standard 2.0 come destinazione. Questo semplifica il grafico delle dipendenze per gli utenti della libreria che usano come ambiente di esecuzione framework compatibili con .NET Standard 2.0 e riduce il numero dei pacchetti da scaricare.

### <a name="net-standard-versioning-rules"></a>Regole per il controllo delle versioni di .NET standard

Esistono due regole principali per il controllo delle versioni:

- Additive: le versioni di .NET Standard sono cerchi concentrici da un punto di vista logico, ovvero le versioni successive includono tutte le API delle versioni precedenti. Non vengono apportate modifiche importanti tra una versione e l'altra.
- Non modificabili: dopo essere state rilasciate, le versioni di .NET Standard sono bloccate. Le nuove API vengono prima rese disponibili in implementazioni di .NET specifiche, ad esempio .NET Core. Se la commissione di esame di .NET Standard ritiene che le nuove API debbano essere disponibili per tutte le implementazioni di .NET, vengono aggiunte in una nuova versione di .NET Standard.

## <a name="specification"></a>Specifica

La specifica di .NET Standard è un set standardizzato di API. La specifica viene gestita dagli implementatori di .NET, in particolare Microsoft (sono inclusi .NET Framework, .NET Core e Mono) e Unity. Un processo pubblico di commenti e suggerimenti è parte integrante della creazione di nuove versioni di .NET Standard tramite [GitHub](https://github.com/dotnet/standard).

### <a name="official-artifacts"></a>Elementi ufficiali

La specifica ufficiale è un insieme di file con estensione cs che definiscono le API che sono parte dello standard. La [directory ref](https://github.com/dotnet/standard/tree/master/src/netstandard/ref) nel [repository dotnet/standard](https://github.com/dotnet/standard) definisce le API di .NET Standard.

Il metapacchetto [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library) ([origine](https://github.com/dotnet/standard/blob/master/src/netstandard/pkg/NETStandard.Library.dependencies.props)) descrive il set di librerie che definiscono (in parte) una o più versioni di .NET Standard.

Un componente specifico, ad esempio `System.Runtime`, descrive quanto segue:

- Parte di .NET Standard (solo il relativo ambito).
- Diverse versioni di .NET Standard per tale ambito.

Vengono forniti elementi derivati per facilitare le operazioni di lettura e abilitare alcuni scenari di sviluppo (ad esempio l'uso di un compilatore).

- [Elenco di API in markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Assembly di riferimento, distribuiti come [pacchetti NuGet](../core/packages.md) e utilizzati come riferimento dal metapacchetto [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/).

### <a name="package-representation"></a>Rappresentazione dei pacchetti

Il principale veicolo di distribuzione degli assembly di riferimento di .NET Standard sono i [pacchetti NuGet](../core/packages.md). Le implementazioni vengono distribuite con modalità diverse, appropriate per ogni implementazione di .NET.

I pacchetti NuGet hanno come destinazione uno o più [framework](frameworks.md). I pacchetti di .NET Standard hanno come destinazione il framework ".NET Standard". È possibile fare riferimento a .NET Standard Framework usando il `netstandard` [Compact TFM](frameworks.md) , ad esempio `netstandard1.4`. Le librerie che devono essere eseguite in più runtime devono avere come destinazione questo framework. Per il set più ampio di API, indicare `netstandard2.0` come destinazione poiché il numero di API è più che raddoppiato tra .NET Standard 1.6 e 2.0.

Il metapacchetto [`NETStandard.Library`](https://www.nuget.org/packages/NETStandard.Library/) fa riferimento al set completo di pacchetti NuGet che definiscono .NET Standard.  Il modo più comune per definire `netstandard` come destinazione consiste nel fare riferimento a questo metapacchetto. Questo metapacchetto descrive e fornisce l'accesso alle circa 40 librerie .NET e alle API associate che definiscono .NET Standard. Per accedere ad API aggiuntive, è possibile fare riferimento ad altri pacchetti che hanno come destinazione `netstandard`.

### <a name="versioning"></a>Versionamento

La specifica non è singola, ma costituisce un set di API a crescita incrementale e con definizione lineare delle versioni. La prima versione dello standard definisce un set di dati di riferimento delle API. Le versioni successive aggiungono nuove API ed ereditano quelle definite dalle versioni precedenti. Non esiste alcuna norma stabilita per la rimozione di API dallo standard.

.NET Standard non è specifico di alcuna implementazione di .NET e non corrisponde allo schema di numerazione delle versioni di nessuno di questi runtime.

Le API aggiunte a una delle implementazioni (ad esempio, .NET Framework, .NET Core e Mono) possono essere prese in considerazione per l'aggiunta alla specifica, in particolare se sono state progettate per essere API fondamentali. Le nuove [versioni di .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md) vengono create sulla base delle versioni delle implementazioni di .NET, consentendo di definire come destinazione nuove API da una libreria di classi portabile .NET Standard. I meccanismi di versionamento sono descritti in modo più dettagliato nell'articolo [.NET Core Versioning](../core/versions/index.md) (Versionamento di .NET Core).

Il controllo delle versioni di .NET Standard è importante per l'uso. Data una versione di .NET Standard, è possibile usare librerie che hanno come destinazione la stessa versione o versioni precedenti. L'approccio seguente descrive il flusso di lavoro per l'uso di librerie di classi portabili di .NET Standard, in particolare per la definizione di .NET Standard come destinazione.

- Selezionare una versione di .NET Standard da usare per la libreria di classi portabile.
- Usare librerie che dipendono dalla stessa versione di .NET Standard o da versioni precedenti.
- Se viene individuata una libreria che dipende da una versione successiva di .NET Standard, è necessario adottare la stessa versione oppure decidere di non usare tale libreria.

## <a name="targeting-net-standard"></a>Definizione di .NET Standard come destinazione

È possibile [creare librerie .NET Standard](../core/tutorials/libraries.md) usando una combinazione del framework `netstandard` e del metapacchetto NETStandard.Library. Sono disponibili esempi della [definizione di .NET Standard come destinazione con strumenti .NET Core](../core/packages.md).

## <a name="net-framework-compatibility-mode"></a>Modalità di compatibilità di .NET Framework

A partire da .NET Standard 2.0 è stata introdotta la modalità di compatibilità di .NET Framework. Questa modalità consente ai progetti .NET Standard di fare riferimento a librerie .NET Framework come se fossero compilate per .NET Standard. I riferimenti alle librerie .NET Framework non funzionano per tutti i progetti, ad esempio se la libreria usa API Windows Presentation Foundation (WPF).

Per altre informazioni, vedere [Modalità di compatibilità di .NET Framework](../core/porting/third-party-deps.md#net-framework-compatibility-mode).

## <a name="net-standard-libraries-and-visual-studio"></a>Librerie .NET Standard e Visual Studio

Per compilare librerie .NET Standard in Visual Studio, verificare di avere [Visual Studio 2017 versione 15.3](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) o successiva installato in Windows oppure [Visual Studio per Mac versione 7.1](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) o successiva installato in macOS.

Se si devono usare le librerie .NET Standard 2.0 solo nei propri progetti, è anche possibile usare Visual Studio 2015. Tuttavia, deve essere installato il client NuGet versione 3.6 o successiva. È possibile scaricare il client NuGet per Visual Studio 2015 dalla pagina di [download di NuGet](https://www.nuget.org/downloads).

## <a name="comparison-to-portable-class-libraries"></a>Confronto con le librerie di classi portabili

.NET Standard sostituisce le [librerie di classi portabili](./cross-platform/cross-platform-development-with-the-portable-class-library.md). .NET Standard migliora l'esperienza di creazione delle librerie portabili curando una BCL standard e assicurando di conseguenza una maggiore uniformità tra le implementazioni di .NET. Una libreria che ha come destinazione .NET Standard è una libreria di classi portabile o una "libreria di classi portabile basata su .NET Standard". Le librerie di classi portabili esistenti sono "librerie di classi portabili basate sul profilo".

.NET Standard e i profili delle librerie di classi portabili sono stati creati per scopi simili, ma presentano differenze significative.

Analogie:

- Definiscono le API che possono essere usate per la condivisione di codice binario.

Differenze:

- .NET Standard è un set curato di API, mentre i profili delle librerie di classi portabili sono definiti da intersezioni delle piattaforme esistenti.
- La definizione delle versioni di .NET Standard è lineare, mentre quella dei profili delle librerie di classi portabili non lo è.
- I profili delle librerie di classi portabili rappresentano piattaforme Microsoft, mentre .NET Standard è indipendente dalla piattaforma.

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

## <a name="see-also"></a>Vedere anche

- [.NET Standard Versions](https://github.com/dotnet/standard/blob/master/docs/versions.md) (Versioni di .NET Standard)
- [Compilazione di una libreria di .NET Standard](../core/tutorials/library-with-visual-studio.md)
- [Supporto multipiattaforma](./library-guidance/cross-platform-targeting.md)
