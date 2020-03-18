---
title: Creazione di thread e passaggio di dati all'avvio
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: a628cbb4c9ec8e1c9ccd9fd73e72a82ecf2b2836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138095"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Creazione di thread e passaggio di dati all'avvio

Quando viene creato un processo del sistema operativo, il sistema operativo inserisce un thread per eseguire il codice in tale processo, inclusi i domini dell'applicazione originali. Da quel momento, i domini dell'applicazione possono essere creati ed eliminati definitivamente senza dover creare o eliminare definitivamente i thread del sistema operativo. Se il codice eseguito è codice gestito, si può ottenere un oggetto <xref:System.Threading.Thread> per il thread in esecuzione nel dominio dell'applicazione corrente recuperando la proprietà statica <xref:System.Threading.Thread.CurrentThread%2A> di tipo <xref:System.Threading.Thread>. Questo argomento descrive la creazione dei thread e illustra le alternative per passare i dati alla routine del thread.  
  
## <a name="creating-a-thread"></a>Creazione di un thread

 La creazione di un nuovo oggetto <xref:System.Threading.Thread> crea un nuovo thread gestito. La classe <xref:System.Threading.Thread> ha costruttori che accettano un delegato <xref:System.Threading.ThreadStart> o un delegato <xref:System.Threading.ParameterizedThreadStart>. Il delegato esegue il wrapping del metodo richiamato dal nuovo thread quando si chiama il metodo <xref:System.Threading.Thread.Start%2A>. Se si chiama <xref:System.Threading.Thread.Start%2A> più di una volta, viene generata un'eccezione <xref:System.Threading.ThreadStateException>.  
  
 Il metodo <xref:System.Threading.Thread.Start%2A> restituisce il controllo immediatamente, spesso prima che il nuovo thread sia stato effettivamente avviato. È possibile usare le proprietà <xref:System.Threading.Thread.ThreadState%2A> e <xref:System.Threading.Thread.IsAlive%2A> per determinare lo stato del thread in qualsiasi momento, ma è consigliabile non usare mai queste proprietà per la sincronizzazione delle attività dei thread.  
  
> [!NOTE]
> Dopo che un thread è stato avviato, non è necessario mantenere un riferimento all'oggetto <xref:System.Threading.Thread>. Il thread continua l'esecuzione fino al termine della routine del thread.  
  
 L'esempio di codice seguente crea due nuovi thread per chiamare metodi di istanza e statici su un altro oggetto.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a>Passaggio di dati ai thread

 In .NET Framework versione 2.0 il delegato <xref:System.Threading.ParameterizedThreadStart> consente di passare facilmente un oggetto contenente dati da un thread quando si chiama l'overload del metodo <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>. Per un esempio di codice, vedere <xref:System.Threading.ParameterizedThreadStart>.  
  
 L'uso del delegato <xref:System.Threading.ParameterizedThreadStart> non è un modo indipendente dai tipi per passare i dati, perché l'overload del metodo <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> accetta qualsiasi oggetto. In alternativa è possibile incapsulare la routine del thread e i dati in una classe helper e usare il delegato <xref:System.Threading.ThreadStart> per eseguire la routine del thread. L'esempio che segue illustra questa tecnica:

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

Nessuno dei due delegati, <xref:System.Threading.ThreadStart> e <xref:System.Threading.ParameterizedThreadStart>, ha un valore restituito, perché non è possibile restituire i dati da una chiamata asincrona. Per recuperare i risultati di un metodo di thread, è possibile usare un metodo di callback, come illustrato nella sezione successiva.
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a>Recupero dei dati dai thread con i metodi di callback

 L'esempio seguente illustra un metodo di callback che recupera i dati da un thread. Il costruttore della classe che contiene i dati e il metodo del thread accetta anche un delegato che rappresenta il metodo di callback. Prima che il metodo del thread termini, richiama il delegato di callback.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [Threading](index.md)
- [Utilizzo di thread e threading](using-threads-and-threading.md)
