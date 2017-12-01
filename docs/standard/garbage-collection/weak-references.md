---
title: Riferimenti deboli
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a>Riferimenti deboli
Il Garbage Collector non può raccogliere un oggetto usato da un'applicazione finché il codice dell'applicazione è in grado raggiungere tale oggetto. Si dice che l'applicazione ha un riferimento sicuro all'oggetto.  
  
 Un riferimento debole consente al Garbage Collector di raccogliere l'oggetto, pur senza impedire all'applicazione di accedervi. Un riferimento debole è valido solo durante il periodo di tempo indeterminato fino a quando l'oggetto viene raccolto, se non è presente nessun riferimento sicuro. Quando si usa un riferimento debole, l'applicazione può comunque ottenere un riferimento sicuro all'oggetto, che ne impedirà la raccolta. Tuttavia esiste sempre il rischio che il Garbage Collector raggiunga l'oggetto prima che venga ristabilito un riferimento sicuro.  
  
 I riferimenti deboli sono utili per gli oggetti che usano grandi quantità di memoria ma possono essere ricreati facilmente se vengono raccolti dall'operazione di Garbage Collection.  
  
 Si supponga che una visualizzazione albero in un'applicazione Windows Form visualizza una scelta complessa gerarchica delle opzioni all'utente. Se i dati sottostanti sono di grandi dimensioni, non è efficiente mantenere la struttura in memoria mentre l'utente esegue altre operazioni nell'applicazione.  
  
 Quando l'utente passa a un'altra parte dell'applicazione, è possibile utilizzare la <xref:System.WeakReference> classe per creare un riferimento debole all'albero e distruggere tutti i riferimenti forti. Quando l'utente torna alla struttura, l'applicazione cerca di ottenere un riferimento sicuro alla struttura ad albero e, se vi riesce, evita la ricostruzione della struttura.  
  
 Per stabilire un riferimento debole a un oggetto, è necessario creare un <xref:System.WeakReference> utilizzando l'istanza dell'oggetto da rilevare. È quindi necessario impostare la proprietà <xref:System.WeakReference.Target%2A> su questo oggetto e impostare il riferimento originale all'oggetto su `null`. Per un esempio di codice, vedere <xref:System.WeakReference> nella libreria di classi.  
  
## <a name="short-and-long-weak-references"></a>Riferimenti deboli brevi e lunghi  
 È possibile creare un riferimento debole breve o lungo:  
  
-   Short  
  
     La destinazione di un riferimento debole breve diventa `null` quando l'oggetto viene raccolto dall'operazione di Garbage Collection. Il riferimento debole è in sé un oggetto gestito ed è soggetto a Garbage Collection come qualsiasi altro oggetto gestito.  Un riferimento debole breve è il costruttore predefinito per <xref:System.WeakReference>.  
  
-   Long  
  
     Un riferimento debole lungo viene mantenuto dopo l'oggetto <xref:System.Object.Finalize%2A> metodo è stato chiamato. Ciò consente che l'oggetto venga ricreato, ma lo stato dell'oggetto non è prevedibile. Per utilizzare un riferimento lungo, specificare `true` nel <xref:System.WeakReference> costruttore.  
  
     Se il tipo di oggetto non ha un <xref:System.Object.Finalize%2A> (metodo), il riferimento debole breve funzionalità si applica e il riferimento debole è valido solo fino a quando non verrà raccolti la destinazione, che può verificarsi in qualsiasi momento dopo il finalizzatore viene eseguito.  
  
 Per stabilire un riferimento forte e utilizzare nuovamente l'oggetto, eseguire il cast di <xref:System.WeakReference.Target%2A> proprietà di un <xref:System.WeakReference> per il tipo dell'oggetto. Se il <xref:System.WeakReference.Target%2A> restituisce proprietà `null`, l'oggetto è stato raccolto; in caso contrario, è possibile continuare a utilizzare l'oggetto perché l'applicazione ha recuperato un riferimento forte ad esso.  
  
## <a name="guidelines-for-using-weak-references"></a>Linee guida per l'uso dei riferimenti deboli  
 Usare i riferimenti deboli lunghi solo in caso di necessità, perché dopo la finalizzazione lo stato dell'oggetto è imprevedibile.  
  
 Evitare di usare riferimenti deboli a oggetti di piccole dimensioni, poiché il puntatore può avere dimensioni equivalenti o superiori.  
  
 Evitare di usare i riferimenti deboli come soluzione automatica per i problemi di gestione della memoria. In alternativa, sviluppare un criterio di memorizzazione nella cache efficiente per gestire gli oggetti dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
