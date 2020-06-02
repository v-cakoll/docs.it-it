---
title: 'Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
ms.openlocfilehash: 57a01726e897f4ddbf8df5ede53609c198012d80
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287874"
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Procedura: Aggiungere funzionalità di delimitazione e blocco a una raccolta
Questo esempio illustra come aggiungere la funzionalità di delimitazione e blocco a una classe di raccolta personalizzata implementando l'interfaccia <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType> nella classe e successivamente usando un'istanza della classe come meccanismo di archiviazione interno per un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>. Per altre informazioni su delimitazione e blocco, vedere [Panoramica di BlockingCollection](blockingcollection-overview.md).  
  
## <a name="example"></a>Esempio  
 La classe di raccolta personalizzata è una coda di priorità di base in cui i livelli di priorità sono rappresentati come matrice di oggetti <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>. Nessun ordinamento aggiuntivo viene eseguito all'interno di ogni coda.  
  
 Nel codice client vengono avviate tre attività. La prima attività esegue il polling per le sequenze di tasti che abilitano l'annullamento in qualsiasi momento durante l'esecuzione. La seconda attività è il thread producer. Aggiunge nuovi elementi alla raccolta di blocco e assegna a ogni elemento una priorità basata su un valore casuale. La terza attività rimuove gli elementi dalla raccolta appena diventano disponibili.  
  
 È possibile modificare il comportamento dell'applicazione rendendo uno dei thread più veloce rispetto all'altro. Se il producer viene eseguito più velocemente, si noterà la funzionalità di delimitazione perché la raccolta di blocco impedisce l'aggiunta di elementi se contiene già il numero di elementi specificato nel costruttore. Se il consumer viene eseguito più velocemente, si noterà la funzionalità di blocco perché il consumer aspetta che un nuovo elemento venga aggiunto.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 Per impostazione predefinita, l'archiviazione per un oggetto <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType> è <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vedere anche

- [Raccolte thread-safe](index.md)
