---
title: Riferimenti deboli
description: Informazioni sui riferimenti vulnerabili, che consentono a .NET Garbage Collector di raccogliere un oggetto pur continuando a consentire all'applicazione di accedere all'oggetto.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
ms.openlocfilehash: 1c18b4fa979058893e0683620ec6cff8e7b15b9b
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768183"
---
# <a name="weak-references"></a>Riferimenti deboli
Il Garbage Collector non può raccogliere un oggetto usato da un'applicazione finché il codice dell'applicazione è in grado raggiungere tale oggetto. Si dice che l'applicazione ha un riferimento sicuro all'oggetto.  
  
 Un riferimento debole consente al Garbage Collector di raccogliere l'oggetto, pur senza impedire all'applicazione di accedervi. Un riferimento debole è valido solo durante il periodo di tempo indeterminato fino a quando l'oggetto viene raccolto, se non è presente nessun riferimento sicuro. Quando si usa un riferimento debole, l'applicazione può comunque ottenere un riferimento sicuro all'oggetto, che ne impedirà la raccolta. Tuttavia esiste sempre il rischio che il Garbage Collector raggiunga l'oggetto prima che venga ristabilito un riferimento sicuro.  
  
 I riferimenti deboli sono utili per gli oggetti che usano grandi quantità di memoria ma possono essere ricreati facilmente se vengono raccolti dall'operazione di Garbage Collection.  
  
 Si supponga che una visualizzazione struttura ad albero in un'applicazione Windows Forms mostri una gamma gerarchica complessa di opzioni all'utente. Se i dati sottostanti sono di grandi dimensioni, non è efficiente mantenere la struttura in memoria mentre l'utente esegue altre operazioni nell'applicazione.  
  
 Quando l'utente passa a un'altra parte dell'applicazione, è possibile usare la classe <xref:System.WeakReference> per creare un riferimento debole all'albero ed eliminare tutti i riferimenti sicuri. Quando l'utente torna alla struttura, l'applicazione cerca di ottenere un riferimento sicuro alla struttura ad albero e, se vi riesce, evita la ricostruzione della struttura.  
  
 Per stabilire un riferimento debole a un oggetto è necessario creare una classe <xref:System.WeakReference> usando l'istanza dell'oggetto di cui tenere traccia. È quindi necessario impostare la proprietà <xref:System.WeakReference.Target%2A> su questo oggetto e impostare il riferimento originale all'oggetto su `null`. Per un esempio di codice, vedere <xref:System.WeakReference> nella libreria di classi.  
  
## <a name="short-and-long-weak-references"></a>Riferimenti deboli brevi e lunghi  
 È possibile creare un riferimento debole breve o lungo:  
  
- Short  
  
     La destinazione di un riferimento debole breve diventa `null` quando l'oggetto viene raccolto dall'operazione di Garbage Collection. Il riferimento debole è in sé un oggetto gestito ed è soggetto a Garbage Collection come qualsiasi altro oggetto gestito.  Un riferimento debole breve è il costruttore senza parametri per <xref:System.WeakReference>.  
  
- long  
  
     Un riferimento debole lungo viene mantenuto dopo la chiamata al metodo <xref:System.Object.Finalize%2A> dell'oggetto. Ciò consente che l'oggetto venga ricreato, ma lo stato dell'oggetto non è prevedibile. Per usare un riferimento lungo, specificare `true` nel costruttore <xref:System.WeakReference>.  
  
     Se il tipo dell'oggetto non dispone di un metodo <xref:System.Object.Finalize%2A>, viene applicata la funzionalità del riferimento debole breve e il riferimento debole è valido solo fino alla raccolta del target, che può verificarsi in qualsiasi momento dopo l'esecuzione del finalizzatore.  
  
 Per stabilire un riferimento sicuro e usare nuovamente l'oggetto, eseguire il cast della proprietà <xref:System.WeakReference.Target%2A> di un <xref:System.WeakReference> al tipo dell'oggetto. Se la proprietà <xref:System.WeakReference.Target%2A> restituisce `null` l'oggetto è stato raccolto. In caso contrario è possibile continuare a usare l'oggetto, perché l'applicazione ha recuperato un riferimento sicuro all'oggetto stesso.  
  
## <a name="guidelines-for-using-weak-references"></a>Linee guida per l'uso dei riferimenti deboli  
 Usare i riferimenti deboli lunghi solo in caso di necessità, perché dopo la finalizzazione lo stato dell'oggetto è imprevedibile.  
  
 Evitare di usare riferimenti deboli a oggetti di piccole dimensioni, poiché il puntatore può avere dimensioni equivalenti o superiori.  
  
 Evitare di usare i riferimenti deboli come soluzione automatica per i problemi di gestione della memoria. In alternativa, sviluppare un criterio di memorizzazione nella cache efficiente per gestire gli oggetti dell'applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Garbage Collection](index.md)
