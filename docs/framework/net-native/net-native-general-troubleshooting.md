---
title: Risoluzione dei problemi generale per .NET Native
ms.date: 03/30/2017
ms.assetid: ee8c5e17-35ea-48a1-8767-83298caac1e8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ea5f61b0e250c4f51a966bc60959f7559d8e2fe2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049393"
---
# <a name="net-native-general-troubleshooting"></a>Risoluzione dei problemi generale per .NET Native

Questo argomento descrive come risolvere i potenziali problemi che possono verificarsi durante lo sviluppo di app con .NET Native.

- **Problema** La finestra di output di compilazione non viene aggiornata correttamente.

  **Risoluzione** La finestra di output di compilazione non viene aggiornata fino al completamento della compilazione. La compilazione può richiedere qualche minuto, quindi è possibile che si verifichi un ritardo nella visualizzazione degli aggiornamenti.

- **Problema** Il tempo di compilazione della versione finale dell'app per ARM è aumentato.

  **Risoluzione** Quando si distribuisce un'app nel dispositivo ARM, viene richiamata l'infrastruttura .NET Native. Questa compilazione esegue diverse ottimizzazioni, assicurando al tempo stesso il corretto funzionamento della semantica non statica, ad esempio la reflection. Inoltre, la parte di .NET Framework usata dall'app è collegata staticamente per assicurare prestazioni ottimizzate e deve essere compilata anch'essa in codice nativo. Ecco perché la compilazione richiede più tempo.

  Tuttavia, i tempi di compilazione sono ancora compresi nell'intervallo di un minuto rispetto alla compilazione standard della maggior parte delle app in un computer di sviluppo standard.  In genere la semplice generazione di immagini native per .NET Framework in un computer di sviluppo standard richiede alcuni minuti.  Anche considerando tutte le ottimizzazioni per il miglioramento del codice generato e includendo .NET Framework, i tempi di compilazione dell'app corrispondono solitamente a un minuto o due.

  Il processo di miglioramento delle prestazioni di compilazione è costante e viene eseguito analizzando la compilazione multithread e altre ottimizzazioni.

- **Problema** Non si sa se l'app è stata compilata con .NET Native.

  **Risoluzione** Se il compilatore .NET Native viene richiamato, si noterà che i tempi di compilazione sono più lunghi e gestione attività visualizzerà vari processi di .NET Native componente, ad esempio ILC. exe e nutc_driver. exe.

  Dopo aver compilato correttamente il progetto con .NET native, l'output verrà trovato in obj\\*config*\ *Arch*\\*NomeProgetto*. ilc\out.  I contenuti del pacchetto nativo finale sono disponibili in bin\\*arch*\\*config*\AppX. I contenuti del pacchetto nativo finale sono disponibili in \bin\\*arch*\\*config*\AppX se l'app è stata distribuita.

- **Problema** L'app compilata .NET Native genera eccezioni di runtime (in genere eccezioni [MissingMetadataException](missingmetadataexception-class-net-native.md) o [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) ) che non sono state generate quando vengono compilate senza .NET native.

  **Risoluzione** Le eccezioni vengono generate perché .NET Native non ha fornito i metadati o il codice di implementazione che altrimenti è disponibile tramite reflection. Per altre informazioni, vedere [Compilazione e .NET Native](net-native-and-compilation.md). Per eliminare l'eccezione, si deve aggiungere una voce al proprio [file di direttive di runtime (rd.xml)](runtime-directives-rd-xml-configuration-file-reference.md) in modo che la catena di strumenti di .NET Native possa rendere i metadati o il codice di implementazione disponibile in fase di esecuzione. Sono disponibili due strumenti di risoluzione dei problemi che genereranno la voce necessaria per l'aggiunta del file di direttive di runtime:

  - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/type.html) per i tipi.

  - Lo [strumento di risoluzione dei problemi MissingMetadataException](https://dotnet.github.io/native/troubleshooter/method.html) per i metodi.

  Per altre informazioni, vedere [Reflection e .NET Native](reflection-and-net-native.md).

## <a name="see-also"></a>Vedere anche

- [Migrazione dell'app di Windows Store a .NET Native](migrating-your-windows-store-app-to-net-native.md)
