---
title: Creazione di thread e passaggio di dati all'avvio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Creazione di thread e passaggio di dati all'avvio
Quando viene creato un processo del sistema operativo, il sistema operativo inserisce un thread per eseguire codice in tale processo, inclusi qualsiasi dominio dell'applicazione originale. Da quel momento, i domini applicazione possono essere creati e distrutti senza necessariamente creato o eliminato qualsiasi thread del sistema operativo. Se viene gestito il codice eseguito codice, quindi un <xref:System.Threading.Thread> dell'oggetto per il thread in esecuzione nel dominio applicazione corrente può essere ottenuto tramite il recupero statica <xref:System.Threading.Thread.CurrentThread%2A> proprietà di tipo <xref:System.Threading.Thread>. In questo argomento viene descritta la creazione di thread e vengono illustrate le alternative per passare dati alla routine del thread.  
  
## <a name="creating-a-thread"></a>Creazione di un Thread  
 Creazione di un nuovo <xref:System.Threading.Thread> oggetto crea un nuovo thread gestito. Il <xref:System.Threading.Thread> classe dispone di costruttori che accettano un <xref:System.Threading.ThreadStart> delegato o un <xref:System.Threading.ParameterizedThreadStart> delegare; il delegato il wrapping del metodo che viene richiamato dal nuovo thread quando si chiama il <xref:System.Threading.Thread.Start%2A> metodo. La chiamata <xref:System.Threading.Thread.Start%2A> più volte un <xref:System.Threading.ThreadStateException> generata.  
  
 Il <xref:System.Threading.Thread.Start%2A> restituisce immediatamente, spesso prima dell'avvio effettivo il nuovo thread. È possibile utilizzare il <xref:System.Threading.Thread.ThreadState%2A> e <xref:System.Threading.Thread.IsAlive%2A> le proprietà per determinare lo stato del thread in qualsiasi momento, ma queste proprietà mai da utilizzare per la sincronizzazione delle attività di thread.  
  
> [!NOTE]
>  Una volta avviato un thread, non è necessario mantenere un riferimento al <xref:System.Threading.Thread> oggetto. Il thread continua l'esecuzione fino al termine della procedura di thread.  
  
 Esempio di codice seguente crea due nuovi thread per chiamare i metodi statici e istanza su un altro oggetto.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a>Passaggio di dati ai thread e il recupero dei dati da thread  
 In .NET Framework versione 2.0, il <xref:System.Threading.ParameterizedThreadStart> delegato fornisce un modo semplice per passare un oggetto contenente i dati da un thread quando si chiama il <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> overload del metodo. Per un esempio di codice, vedere <xref:System.Threading.ParameterizedThreadStart>.  
  
 Utilizzo di <xref:System.Threading.ParameterizedThreadStart> delegato non è un modo indipendente dai tipi per passare i dati, perché il <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> overload del metodo accetta qualsiasi oggetto. In alternativa è possibile incapsulare la procedura del thread e i dati in una classe helper e utilizzare il <xref:System.Threading.ThreadStart> delegato per eseguire la procedura del thread. Questa tecnica è illustrata negli esempi di due codice che seguono.  
  
 Nessuno di questi delegati è un valore restituito, perché non è possibile restituire i dati da una chiamata asincrona. Per recuperare i risultati di un metodo di thread, è possibile utilizzare un metodo di callback, come illustrato nel secondo esempio di codice.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a>Recupero dei dati con i metodi di Callback  
 Nell'esempio seguente viene illustrato un metodo di callback che recupera dati da un thread. Il costruttore per la classe che contiene i dati e il metodo di thread accetta inoltre un delegato che rappresenta il metodo di callback. prima che il metodo di thread termina, viene richiamato il delegato di callback.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Utilizzo di thread e threading](../../../docs/standard/threading/using-threads-and-threading.md)
