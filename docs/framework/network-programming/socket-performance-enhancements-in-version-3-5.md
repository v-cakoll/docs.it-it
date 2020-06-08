---
title: Miglioramenti apportati alle prestazioni socket nella versione 3.5
description: Per informazioni sui miglioramenti delle prestazioni della classe System .NET. Sockets. Socket nella versione 3,5, vedere la .NET Framework.
ms.date: 03/30/2017
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
ms.openlocfilehash: 5a640c58e47bf1630a3a551aed72b9bc9d4fd6fe
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502145"
---
# <a name="socket-performance-enhancements-in-version-35"></a>Miglioramenti apportati alle prestazioni socket nella versione 3.5
La classe <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> è stata migliorata nella versione 3.5 per l'uso da applicazioni che usano I/O di rete asincrono per ottenere le massime prestazioni. È stata aggiunta una serie di nuove classi nell'ambito di una serie di miglioramenti apportati alla classe <xref:System.Net.Sockets.Socket> che forniscono un modello asincrono alternativo che può essere usato da applicazioni socket ad alte prestazioni specializzate. Questi miglioramenti sono stati progettati in modo specifico per le applicazioni server di rete che richiedono prestazioni elevate. Un'applicazione può usare il modello asincrono migliorato in modo esclusivo o solo nelle aree dell'applicazione con esigenze particolari individuate, ad esempio per la ricezione di grandi quantità di dati.  
  
## <a name="class-enhancements"></a>Miglioramenti della classe  
 La funzionalità principale di questi miglioramenti è evitare l'allocazione ripetuta e la sincronizzazione degli oggetti durante operazioni di I/O su socket asincrone con volumi elevati di dati. Lo schema progettuale basato su inizio/fine attualmente implementato dalla classe <xref:System.Net.Sockets.Socket> per le operazioni di I/O su socket asincrone richiede l'allocazione di un oggetto <xref:System.IAsyncResult?displayProperty=nameWithType> per ogni operazione su socket asincrona.  
  
 Nei nuovi miglioramenti per la classe <xref:System.Net.Sockets.Socket>, le operazioni su socket asincrone sono descritte da oggetti classe <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType> riutilizzabili, allocati e gestiti dall'applicazione. Le applicazioni ad alte prestazioni che usano socket conoscono bene la quantità di operazioni su socket sovrapposte che occorre supportare. L'applicazione può creare il numero di oggetti <xref:System.Net.Sockets.SocketAsyncEventArgs> necessari. Ad esempio, se un'applicazione server deve disporre di 15 operazioni di accettazione socket in sospeso in qualsiasi momento per supportare le velocità di connessione client in ingresso, può allocare 15 oggetti <xref:System.Net.Sockets.SocketAsyncEventArgs> riutilizzabili in anticipo a tale scopo.  
  
 Il modello per l'esecuzione di un'operazione socket asincrona con questa classe è costituito dai passaggi seguenti:  
  
1. Allocare un nuovo oggetto contesto <xref:System.Net.Sockets.SocketAsyncEventArgs> oppure ottenerne uno libero da un pool di applicazioni.  
  
2. Impostare le proprietà nell'oggetto contesto per l'operazione da eseguire, ad esempio il metodo delegato di callback e il buffer di dati.  
  
3. Chiamare il metodo socket appropriato (xxxAsync) per avviare l'operazione asincrona.  
  
4. Se il metodo socket asincrono (xxxAsync) restituisce true nel callback, recuperare lo stato di completamento dalle proprietà di contesto.  
  
5. Se il metodo socket asincrono (xxxAsync) restituisce false nel callback, l'operazione è stata completata in modo sincrono. È possibile recuperare il risultato dell'operazione dalle proprietà di contesto.  
  
6. Riutilizzare il contesto per un'altra operazione, inserirlo nuovamente nel pool o rimuoverlo.  
  
 La durata del nuovo oggetto di contesto dell'operazione socket asincrona è determinata dai riferimenti nel codice dell'applicazione e dai riferimenti di I/O asincroni. Non è necessario che l'applicazione mantenga un riferimento a un oggetto di contesto dell'operazione socket asincrona dopo l'invio come parametro a uno dei metodi per operazioni socket asincrone. Il riferimento verrà mantenuto attivo fino a quando il callback di completamento non restituisce il controllo. È tuttavia vantaggioso che l'applicazione mantenga un riferimento all'oggetto di contesto, in modo da poterlo riutilizzare per un'operazione socket asincrona futura.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net.Sockets.Socket?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SendPacketsElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=nameWithType>
- [Esempi di programmazione di rete](network-programming-samples.md)
- [Esempi di codice socket](socket-code-examples.md)
