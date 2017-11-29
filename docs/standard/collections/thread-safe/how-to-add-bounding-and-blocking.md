---
title: "Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: aeba49c31238c62a12dba96d3dc47c3cc8ef1bcb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta
Questo esempio illustra come aggiungere la funzionalità di delimitazione e blocco a una classe di raccolta personalizzata implementando l'interfaccia <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> nella classe e successivamente usando un'istanza della classe come meccanismo di archiviazione interno per un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>. Per altre informazioni su delimitazione e blocco, vedere [Panoramica di BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## <a name="example"></a>Esempio  
 La classe di raccolta personalizzata è una coda di priorità di base in cui i livelli di priorità sono rappresentati come matrice di oggetti <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>. Nessun ordinamento aggiuntivo viene eseguito all'interno di ogni coda.  
  
 Nel codice client vengono avviate tre attività. La prima attività esegue il polling per le sequenze di tasti che abilitano l'annullamento in qualsiasi momento durante l'esecuzione. La seconda attività è il thread producer. Aggiunge nuovi elementi alla raccolta di blocco e assegna a ogni elemento una priorità basata su un valore casuale. La terza attività rimuove gli elementi dalla raccolta appena diventano disponibili.  
  
 È possibile modificare il comportamento dell'applicazione rendendo uno dei thread più veloce rispetto all'altro. Se il producer viene eseguito più velocemente, si noterà la funzionalità di delimitazione perché la raccolta di blocco impedisce l'aggiunta di elementi se contiene già il numero di elementi specificato nel costruttore. Se il consumer viene eseguito più velocemente, si noterà la funzionalità di blocco perché il consumer aspetta che un nuovo elemento venga aggiunto.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 Per impostazione predefinita, l'archiviazione per un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> è <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche  
 [Raccolte thread-safe](../../../../docs/standard/collections/thread-safe/index.md)
