---
title: Miglioramenti apportati alle prestazioni socket nella versione 3.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 225aa5f9-c54b-4620-ab64-5cd100cfd54c
caps.latest.revision: 9
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3e0e648fb14e07b62f70c614af84a98a256f6095
ms.contentlocale: it-it
ms.lasthandoff: 08/21/2017

---
# <a name="socket-performance-enhancements-in-version-35"></a>Miglioramenti apportati alle prestazioni socket nella versione 3.5
La classe <xref:System.Net.Sockets.Socket?displayProperty=fullName> è stata migliorata nella versione 3.5 per l'uso da applicazioni che usano I/O di rete asincrono per ottenere le massime prestazioni. È stata aggiunta una serie di nuove classi nell'ambito di una serie di miglioramenti apportati alla classe <xref:System.Net.Sockets.Socket> che forniscono un modello asincrono alternativo che può essere usato da applicazioni socket ad alte prestazioni specializzate. Questi miglioramenti sono stati progettati in modo specifico per le applicazioni server di rete che richiedono prestazioni elevate. Un'applicazione può usare il modello asincrono migliorato in modo esclusivo o solo nelle aree dell'applicazione con esigenze particolari individuate, ad esempio per la ricezione di grandi quantità di dati.  
  
## <a name="class-enhancements"></a>Miglioramenti della classe  
 La funzionalità principale di questi miglioramenti è evitare l'allocazione ripetuta e la sincronizzazione degli oggetti durante operazioni di I/O su socket asincrone con volumi elevati di dati. Lo schema progettuale basato su inizio/fine attualmente implementato dalla classe <xref:System.Net.Sockets.Socket> per le operazioni di I/O su socket asincrone richiede l'allocazione di un oggetto <xref:System.IAsyncResult?displayProperty=fullName> per ogni operazione su socket asincrona.  
  
 Nei nuovi miglioramenti per la classe <xref:System.Net.Sockets.Socket>, le operazioni su socket asincrone sono descritte da oggetti classe <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName> riutilizzabili, allocati e gestiti dall'applicazione. Le applicazioni ad alte prestazioni che usano socket conoscono bene la quantità di operazioni su socket sovrapposte che occorre supportare. L'applicazione può creare il numero di oggetti <xref:System.Net.Sockets.SocketAsyncEventArgs> necessari. Ad esempio, se un'applicazione server deve disporre di 15 operazioni di accettazione socket in sospeso in qualsiasi momento per supportare le velocità di connessione client in ingresso, può allocare 15 oggetti <xref:System.Net.Sockets.SocketAsyncEventArgs> riutilizzabili in anticipo a tale scopo.  
  
 Il modello per l'esecuzione di un'operazione socket asincrona con questa classe è costituito dai passaggi seguenti:  
  
1.  Allocare un nuovo oggetto contesto <xref:System.Net.Sockets.SocketAsyncEventArgs> oppure ottenerne uno libero da un pool di applicazioni.  
  
2.  Impostare le proprietà nell'oggetto contesto per l'operazione da eseguire, ad esempio il metodo delegato di callback e il buffer di dati.  
  
3.  Chiamare il metodo socket appropriato (xxxAsync) per avviare l'operazione asincrona.  
  
4.  Se il metodo socket asincrono (xxxAsync) restituisce true nel callback, recuperare lo stato di completamento dalle proprietà di contesto.  
  
5.  Se il metodo socket asincrono (xxxAsync) restituisce false nel callback, l'operazione è stata completata in modo sincrono. È possibile recuperare il risultato dell'operazione dalle proprietà di contesto.  
  
6.  Riutilizzare il contesto per un'altra operazione, inserirlo nuovamente nel pool o rimuoverlo.  
  
 La durata del nuovo oggetto di contesto dell'operazione socket asincrona è determinata dai riferimenti nel codice dell'applicazione e dai riferimenti di I/O asincroni. Non è necessario che l'applicazione mantenga un riferimento a un oggetto di contesto dell'operazione socket asincrona dopo l'invio come parametro a uno dei metodi per operazioni socket asincrone. Il riferimento verrà mantenuto attivo fino a quando il callback di completamento non restituisce il controllo. È tuttavia vantaggioso che l'applicazione mantenga un riferimento all'oggetto di contesto, in modo da poterlo riutilizzare per un'operazione socket asincrona futura.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.Sockets.Socket?displayProperty=fullName>   
 <xref:System.Net.Sockets.SendPacketsElement?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncEventArgs?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketAsyncOperation?displayProperty=fullName>   
 [Esempi di programmazione di rete](../../../docs/framework/network-programming/network-programming-samples.md)   
 [Socket Performance Technology Sample](http://go.microsoft.com/fwlink/?LinkID=179570) (Esempio di tecnologia per le prestazioni del socket)

