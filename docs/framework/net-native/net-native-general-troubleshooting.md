---
title: Risoluzione dei problemi generale per .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9599ee25e77bf6f44e5c6733deed8dc23fc0d022
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67662331"
---
# <a name="net-native-general-troubleshooting"></a>Risoluzione dei problemi generale per .NET Native

Questo argomento descrive come risolvere i problemi potenziali che potrebbero verificarsi durante lo sviluppo di App con .NET Native.

- **Problema:** La finestra di output di compilazione non viene aggiornata correttamente.

  **Soluzione:** La finestra di output di compilazione non viene aggiornata finché non viene completata la compilazione. La compilazione può richiedere qualche minuto, quindi è possibile che si verifichi un ritardo nella visualizzazione degli aggiornamenti.

- **Problema:** Fase di compilazione delle vendite al dettaglio dell'app per ARM è aumentato.

  **Soluzione:** Quando si distribuisce un'app nel dispositivo ARM, viene richiamata l'infrastruttura di .NET Native. Questa compilazione esegue diverse ottimizzazioni, assicurando al tempo stesso il corretto funzionamento della semantica non statica, ad esempio la reflection. Inoltre, la parte di .NET Framework usata dall'app è collegata staticamente per assicurare prestazioni ottimizzate e deve essere compilata anch'essa in codice nativo. Ecco perché la compilazione richiede più tempo.

  Tuttavia, i tempi di compilazione sono ancora compresi nell'intervallo di un minuto rispetto alla compilazione standard della maggior parte delle app in un computer di sviluppo standard.  In genere la semplice generazione di immagini native per .NET Framework in un computer di sviluppo standard richiede alcuni minuti.  Anche considerando tutte le ottimizzazioni per il miglioramento del codice generato e includendo .NET Framework, i tempi di compilazione dell'app corrispondono solitamente a un minuto o due.

  Il processo di miglioramento delle prestazioni di compilazione è costante e viene eseguito analizzando la compilazione multithread e altre ottimizzazioni.

- **Problema:** Non si sa se l'app è stata compilata con .NET Native.

  **Soluzione:** Se viene richiamato il compilatore .NET Native, si noterà che più lunghi tempi di compilazione e Gestione attività visualizzerà diversi processi dei componenti .NET Native, ad esempio ILC.exe e nutc_driver.exe.

  Dopo aver compilato correttamente il progetto con .NET Native, è possibile trovare l'output è disponibile in obj\\*config*\ *arch*\\*NomeProgetto*. ilc\out.  I contenuti del pacchetto nativo finale sono disponibili in bin\\*arch*\\*config*\AppX. I contenuti del pacchetto nativo finale sono disponibili in \bin\\*arch*\\*config*\AppX se l'app è stata distribuita.

- **Problema:** L'app compilata in .NET Native sta generando eccezioni di runtime (in genere [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md) oppure [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) eccezioni) che non sono state generate quando compilato senza. NET nativo.

  **Soluzione:** Le eccezioni vengono generate perché .NET Native non ha fornito metadati o il codice di implementazione altrimenti disponibile attraverso la reflection. Per altre informazioni, vedere [Compilazione e .NET Native](../../../docs/framework/net-native/net-native-and-compilation.md). Per eliminare l'eccezione, si deve aggiungere una voce al proprio [file di direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md) in modo che la catena di strumenti di .NET Native possa rendere i metadati o il codice di implementazione disponibile in fase di esecuzione. Sono disponibili due strumenti di risoluzione dei problemi che genereranno la voce necessaria per l'aggiunta del file di direttive di runtime:

  - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.

  - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.

  Per altre informazioni, vedere [Reflection e .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md).

## <a name="see-also"></a>Vedere anche

- [Migrazione dell'app di Windows Store a .NET Native](../../../docs/framework/net-native/migrating-your-windows-store-app-to-net-native.md)
