---
title: Eccezioni di runtime in app .NET
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f050181-8fdd-4a4e-9d16-f84c22a88a97
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cea4901eca45a4b02e3eeb9fa8a3ac2a9efa3484
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="runtime-exceptions-in-net-native-apps"></a>Eccezioni di runtime in app .NET
È importante testare le build di versione dell'app della piattaforma UWP (Universal Windows Platform) nelle rispettive piattaforme di destinazione, perché le configurazioni di tipo Debug e di tipo Versione sono completamente diverse. Per impostazione predefinita, la configurazione di tipo Debug usa il runtime di .NET Core per compilare l'app, mentre quella di tipo Versione usa .NET Native per compilare l'app nel codice nativo.  
  
> [!IMPORTANT]
>  Per informazioni sulla gestione delle eccezioni [MissingMetadataException](../../../docs/framework/net-native/missingmetadataexception-class-net-native.md), [MissingInteropDataException](../../../docs/framework/net-native/missinginteropdataexception-class-net-native.md) e [MissingRuntimeArtifactException](../../../docs/framework/net-native/missingruntimeartifactexception-class-net-native.md) che possono verificarsi durante il test delle versioni finali dell'app, vedere il passaggio 4 relativo alla risoluzione manuale dei metadati mancanti nell'argomento [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md), oltre che [Reflection e .NET Native](../../../docs/framework/net-native/reflection-and-net-native.md) e [Informazioni di riferimento sul file di configurazione delle direttive di runtime (rd.xml)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
## <a name="debug-and-release-builds"></a>Build di tipo Debug e Versione  
 La build di tipo Debug eseguita nel runtime .NET Core non è stata compilata nel codice nativo. In questo modo tutti i servizi normalmente forniti dal runtime sono disponibili per l'app.  
  
 La build di versione viene invece compilata nel codice nativo per le rispettive piattaforme di destinazione, rimuove la maggior parte delle dipendenze da librerie e runtime esterni, oltre a ottimizzare notevolmente il codice garantendo prestazioni ottimali.  
  
 Quando si esegue il debug di build di tipo Versione compilate con .NET Native:  
  
-   Si usa il motore di debug di .NET Native, che è diverso rispetto ai normali strumenti di debug di .NET.  
  
-   Le dimensioni del file eseguibile vengono ridotte il più possibile. Uno dei modi in cui .NET Native riesce a ridurre le dimensioni del file eseguibile consiste nel tagliare significativamente i messaggi di eccezione di runtime, come descritto in maggiore dettaglio nella sezione [Runtime exception messages](#Messages) .  
  
-   Il codice viene notevolmente ottimizzato. Questo significa che laddove possibile viene usato l'incorporamento, che sposta il codice dalle routine esterne in quella chiamante.   Il fatto che .NET Native fornisca un runtime specializzato e implementi massicciamente l'incorporamento influisce sullo stack di chiamate visualizzato durante il debug.  Per altre informazioni, vedere la sezione [Runtime call stack](#CallStack) .  
  
> [!NOTE]
>  Per controllare se le build di tipo Debug e Versione sono compilate con la catena di strumenti .NET Native, selezionare o deselezionare la casella **Compilare con la catena di strumenti .NET Native** .   Notare però che per la compilazione della versione di produzione dell'app, Windows Store userà sempre la catena di strumenti .NET Native.  
  
<a name="Messages"></a>   
## <a name="runtime-exception-messages"></a>Runtime exception messages  
 Per ridurre al minimo le dimensioni dei file eseguibili delle applicazioni, .NET Native non include il testo completo dei messaggi di eccezione. Di conseguenza, è possibile che i messaggi delle eccezioni di runtime generate nelle build di tipo Versione non includano il testo completo, ma solo una sottostringa e un collegamento da aprire per visualizzare altre informazioni. Le informazioni visualizzate sull'eccezione possono ad esempio essere simili a:  
  
```  
Exception thrown: '$16_System.AggregateException' in Unknown Module.  
  
Additional information: AggregateException_ctor_DefaultMessage  
  
If there is a handler for this exception, the program may be safely continued.  
```  
  
 Per visualizzare il messaggio di eccezione completo, eseguire la build di tipo Debug. Ad esempio le informazioni sull'eccezione precedente della build di tipo Versione sono simili alle seguenti nella build di tipo Debug:  
  
```  
Exception thrown: 'System.AggregateException' in NativeApp.exe.  
  
Additional information: Value does not fall within the expected range.  
```  
  
<a name="CallStack"></a>   
## <a name="runtime-call-stack"></a>Runtime call stack  
 A causa dell'incorporamento e di altre ottimizzazioni, lo stack di chiamate visualizzato da un'app compilata con la catena di strumenti .NET Native potrebbe risultare poco utile per identificare chiaramente il percorso di un'eccezione di runtime.  
  
 Per ottenere lo stack completo, eseguire la build di tipo Debug.  
  
## <a name="see-also"></a>Vedere anche  
 [Debug di App Universal Windows Native .NET](http://blogs.msdn.com/b/visualstudioalm/archive/2015/07/29/debugging-net-native-windows-universal-apps.aspx)  
 [Introduzione](../../../docs/framework/net-native/getting-started-with-net-native.md)
