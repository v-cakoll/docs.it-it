---
title: Risoluzione dei problemi generale per .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
ms.openlocfilehash: 2bea81e380fed6c456898e9883658ef874c8dd97
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "73128234"
---
# <a name="net-native-general-troubleshooting"></a>Risoluzione dei problemi generale per .NET Native

Questo argomento descrive come risolvere i potenziali problemi che possono verificarsi durante lo sviluppo di app con .NET Native.

- **Problema:** la finestra di output di compilazione non viene aggiornata correttamente.

  **Risoluzione:** la finestra di output di compilazione non viene aggiornata correttamente finché non viene completata la compilazione. La compilazione può richiedere qualche minuto, quindi è possibile che si verifichi un ritardo nella visualizzazione degli aggiornamenti.

- **Problema:** il tempo di compilazione per la versione finale dell'app per ARM è aumentato.

  **Risoluzione:** Quando si distribuisce un'app nel dispositivo ARM, viene richiamata l'infrastruttura .NET Native. Questa compilazione esegue diverse ottimizzazioni, assicurando al tempo stesso il corretto funzionamento della semantica non statica, ad esempio la reflection. Inoltre, la parte di .NET Framework usata dall'app è collegata staticamente per assicurare prestazioni ottimizzate e deve essere compilata anch'essa in codice nativo. Ecco perché la compilazione richiede più tempo.

  Tuttavia, i tempi di compilazione sono ancora compresi nell'intervallo di un minuto rispetto alla compilazione standard della maggior parte delle app in un computer di sviluppo standard.  In genere la semplice generazione di immagini native per .NET Framework in un computer di sviluppo standard richiede alcuni minuti.  Anche considerando tutte le ottimizzazioni per il miglioramento del codice generato e includendo .NET Framework, i tempi di compilazione dell'app corrispondono solitamente a un minuto o due.

  Il processo di miglioramento delle prestazioni di compilazione è costante e viene eseguito analizzando la compilazione multithread e altre ottimizzazioni.

- **Problema:** Non si sa se l'app è stata compilata con .NET Native.

  **Risoluzione:** Se il compilatore .NET Native viene richiamato, si noterà che i tempi di compilazione sono più lunghi e gestione attività visualizzerà vari processi di .NET Native componente, ad esempio ILC. exe e nutc_driver. exe.

  Dopo aver compilato correttamente il progetto con .NET native, l'output verrà trovato in obj \\ *config* \  *Arch* \\ *NomeProgetto*. ilc\out.  I contenuti del pacchetto nativo finale sono disponibili in bin \\ *Arch* \\ *config*\AppX. Il contenuto del pacchetto nativo finale si trova in \bin \\ *Arch* \\ *config*\AppX se è stata distribuita l'app.

- **Problema:** l'app compilata in .NET Native sta generando eccezioni di runtime (in genere eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) o [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)) che non sono state generate al momento della compilazione senza .NET Native.

  **Risoluzione:** le eccezioni vengono generate perché .NET Native non ha fornito metadati o il codice di implementazione altrimenti disponibile attraverso la reflection. Per ulteriori informazioni, vedere [.NET native e compilazione](net-native-and-compilation.md). Per eliminare l'eccezione, è necessario aggiungere una voce al file di [direttive di runtime (Rd. Xml)](runtime-directives-rd-xml-configuration-file-reference.md) in modo che la catena di strumenti .NET native possa rendere disponibili i metadati o il codice di implementazione in fase di esecuzione. Sono disponibili due strumenti di risoluzione dei problemi che genereranno la voce necessaria per l'aggiunta del file di direttive di runtime:

  - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.

  - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.

  Per altre informazioni, vedere [Reflection e .NET Native](reflection-and-net-native.md).

## <a name="see-also"></a>Vedi anche

- [Migrazione dell'app di Windows Store a .NET Native](migrating-your-windows-store-app-to-net-native.md)
