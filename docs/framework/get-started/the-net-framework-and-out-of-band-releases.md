---
title: .NET Framework e rilascio fuori programma
ms.date: 10/10/2018
ms.assetid: 721f10fa-3189-4124-a00d-56ddabd889b3
ms.openlocfilehash: a2dcd011548df857a1399c5bbdfe6ed33927672e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716398"
---
# <a name="the-net-framework-and-out-of-band-releases"></a>.NET Framework e rilascio fuori programma

L'evoluzione di .NET Framework includerà diverse piattaforme, tra cui app Windows Phone e Windows Store, nonché app desktop e Web tradizionali, e consentirà di ottimizzare il riutilizzo del codice. Oltre ai regolari rilasci di .NET Framework, verranno rese disponibili nuove funzionalità fuori banda per migliorare lo sviluppo per più piattaforme o introdurre alcune novità. In questo argomento verrà illustrato l'orientamento futuro di .NET Framework e dei rilasci fuori banda.

## <a name="advantages-of-oob-releases"></a>Vantaggi dei rilasci fuori banda
 La distribuzione di nuovi componenti o aggiornamenti ai componenti fuori banda consente a Microsoft di fornire aggiornamenti più frequenti a .NET Framework. Inoltre, sarà possibile raccogliere e rispondere ai feedback dei clienti più rapidamente.

 Se si usa una funzionalità fuori banda nell'app, gli utenti non devono installare la versione più recente di .NET Framework per eseguirla, poiché gli assembly fuori banda vengono distribuiti con il pacchetto dell'app.

## <a name="how-oob-packages-are-distributed"></a>Modalità di distribuzione dei pacchetti fuori banda
I rilasci fuori banda per i componenti principali di Common Language Runtime (CLR) vengono forniti tramite [NuGet](https://www.nuget.org/), ovvero uno strumento di gestione pacchetti per .NET. NuGet consente di cercare e aggiungere facilmente librerie ai progetti .NET Framework da Esplora soluzioni in Visual Studio. NuGet è incluso in tutte le edizioni di Visual Studio a partire da Visual Studio 2012. Per verificare se NuGet è installato, cercare **Gestione pacchetti NuGet** nel menu **Strumenti** di Visual Studio. Se non è installato:

1. Nella barra dei menu di Visual Studio scegliere **Strumenti**, **Estensioni e aggiornamenti** (in Visual Studio 2010, scegliere **Gestione estensioni**).

     Verrà visualizzata la finestra di dialogo **Estensioni e aggiornamenti**.

2. Scegliere **Online** e **Gestione pacchetti NuGet**, quindi fare clic su **Scarica**.

3. Al termine del download, riavviare Visual Studio.

 Per istruzioni di installazione dettagliate, vedere [Installazione di NuGet](/nuget/install-nuget-client-tools) nel sito Web NuGet Docs. Per altre informazioni su NuGet, vedere la [documentazione di NuGet](/nuget).

## <a name="using-a-nuget-oob-package"></a>Utilizzo di un pacchetto NuGet fuori banda
 Dopo aver installato NuGet, sarà possibile cercare e aggiungere riferimenti ai pacchetti NuGet utilizzando Esplora soluzioni di Visual Studio:

1. Aprire il menu di scelta rapida per il progetto in Visual Studio, quindi scegliere **Gestisci pacchetti NuGet**. Questa opzione è disponibile anche nel menu **Progetto**.

2. Nel riquadro sinistro scegliere **Online**.

3. Se si desidera usare i pacchetti della versione provvisoria, nell'elenco a discesa del riquadro centrale scegliere **Includi versione provvisoria** anziché **Solo stabile**.

4. Nel riquadro di destra usare la casella **Cerca** per individuare il pacchetto che si desidera usare. Alcuni pacchetti Microsoft sono identificati dal logo Microsoft .NET Framework e in tutti Microsoft viene identificato come editore.

 ![Screenshot che illustra la gestione dei pacchetti NuGet.](./media/the-net-framework-and-out-of-band-releases/nuget-package-manager-dialog.png)

 Come accennato in precedenza, quando si distribuisce un'app che utilizza un pacchetto fuori banda, all'interno di quest'ultimo verranno forniti gli assembly fuori banda.

## <a name="types-of-oob-releases"></a>Tipi di rilasci fuori banda
 In genere, un pacchetto fuori banda contiene una o più versioni preliminari e una versione stabile. La licenza fornita con una versione preliminare non consente in genere la ridistribuzione, ma permette di provare un pacchetto e fornire feedback. Il feedback è incorporato in qualsiasi aggiornamento apportato al pacchetto. Una versione finale viene distribuita come pacchetto stabile con NuGet e include una licenza che consente di ridistribuire il pacchetto NuGet con l'app. I pacchetti stabili sono supportati da Microsoft. Microsoft fornisce il supporto IntelliSense insieme ad altri tipi di documentazione come i post di blog e le risposte dei forum per tutti i pacchetti. Inoltre, il codice sorgente può essere disponibile solo con alcuni pacchetti. Per ricevere annunci relativi ai pacchetti nuovi e aggiornati, è possibile sottoscrivere il [blog di .NET Framework](https://devblogs.microsoft.com/dotnet/).

 Per trovare sia i pacchetti provvisori che quelli stabili, scegliere **Includi versione provvisoria** in Gestisci pacchetti NuGet.

## <a name="see-also"></a>Vedere anche

- [Introduzione](index.md)
