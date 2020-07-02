---
title: .NET Framework e versioni fuori banda
description: Informazioni sulle versioni di .NET e fuori banda. Le nuove funzionalità vengono rilasciate fuori banda (OOB) per migliorare lo sviluppo multipiattaforma o introdurre nuove funzionalità.
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: 9653696f46279e0c23418f92030d64839cc20518
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618766"
---
# <a name="net-framework-and-out-of-band-releases"></a>.NET Framework e rilasci fuori programma

.NET Framework si è evoluto per supportare piattaforme diverse, ad esempio app UWP e app desktop e Web tradizionali, e per ottimizzare il riutilizzo del codice. Oltre alle normali versioni di .NET Framework, le nuove funzionalità vengono rilasciate fuori banda (OOB) per migliorare lo sviluppo multipiattaforma o introdurre nuove funzionalità.

## <a name="advantages-of-oob-releases"></a>Vantaggi dei rilasci fuori banda

La distribuzione di nuovi componenti o aggiornamenti ai componenti fuori banda consente a Microsoft di fornire aggiornamenti più frequenti per .NET Framework. Inoltre, sarà possibile raccogliere e rispondere ai feedback dei clienti più rapidamente.

Quando si usa una funzionalità OOB nell'app, gli utenti non devono installare la versione più recente di .NET Framework per eseguire l'app, perché gli assembly OOB vengono distribuiti con il pacchetto dell'app.

## <a name="how-oob-packages-are-distributed"></a>Modalità di distribuzione dei pacchetti fuori banda

Le versioni OOB per i componenti di base Common Language Runtime (CLR) vengono fornite tramite [NuGet](https://www.nuget.org/), ovvero gestione pacchetti per .NET. NuGet consente di cercare e aggiungere facilmente librerie ai progetti .NET Framework da Visual Studio. Gestione pacchetti NuGet è incluso in tutte le edizioni di Visual Studio a partire da Visual Studio 2012. Cercare **Gestione pacchetti NuGet** dal menu **strumenti** in Visual Studio. Se non è installato, seguire le istruzioni riportate in [installazione di NuGet](/nuget/install-nuget-client-tools). Per ulteriori informazioni su NuGet, vedere la [documentazione di NuGet](/nuget).

## <a name="use-a-nuget-oob-package"></a>Usare un pacchetto NuGet OOB

Se è installato Gestione pacchetti NuGet, è possibile cercare e aggiungere riferimenti ai pacchetti NuGet usando Esplora soluzioni in Visual Studio:

1. Aprire il menu di scelta rapida per il progetto in Visual Studio, quindi scegliere **Gestisci pacchetti NuGet**. Questa opzione è disponibile anche nel menu **Progetto**.

2. Nel riquadro sinistro scegliere **Online**.

3. Se si desidera usare i pacchetti della versione provvisoria, nell'elenco a discesa del riquadro centrale scegliere **Includi versione provvisoria** anziché **Solo stabile**.

4. Nel riquadro di destra usare la casella **Cerca** per individuare il pacchetto che si desidera usare. Alcuni pacchetti Microsoft sono identificati dal logo Microsoft .NET Framework e in tutti Microsoft viene identificato come editore.

![Gestione pacchetti NuGet.](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

Come accennato in precedenza, quando si distribuisce un'app che utilizza un pacchetto fuori banda, all'interno di quest'ultimo verranno forniti gli assembly fuori banda.

## <a name="types-of-oob-releases"></a>Tipi di rilasci fuori banda

In genere, un pacchetto fuori banda contiene una o più versioni preliminari e una versione stabile. La licenza fornita con una versione preliminare non consente in genere la ridistribuzione, ma permette di provare un pacchetto e fornire feedback. Il feedback è incorporato in qualsiasi aggiornamento apportato al pacchetto. Una versione finale viene distribuita come pacchetto stabile con NuGet e include una licenza che consente di ridistribuire il pacchetto NuGet con l'app. I pacchetti stabili sono supportati da Microsoft. Microsoft fornisce il supporto IntelliSense insieme ad altri tipi di documentazione come i post di blog e le risposte dei forum per tutti i pacchetti. Inoltre, il codice sorgente può essere disponibile solo con alcuni pacchetti. Per ricevere annunci relativi ai pacchetti nuovi e aggiornati, è possibile sottoscrivere il [blog di .NET Framework](https://devblogs.microsoft.com/dotnet/).

Per trovare sia i pacchetti provvisori che quelli stabili, scegliere **Includi versione preliminare** in Gestione pacchetti NuGet.

## <a name="see-also"></a>Vedere anche

- [Introduzione](index.md)
