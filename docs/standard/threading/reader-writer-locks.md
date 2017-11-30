---
title: Blocchi in lettura/scrittura
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a>Blocchi in lettura/scrittura
La <xref:System.Threading.ReaderWriterLockSlim> classe consente la lettura di una risorsa contemporaneamente più thread, ma richiede un thread rimanga in attesa di un blocco esclusivo per scrivere la risorsa.  
  
 È possibile utilizzare un <xref:System.Threading.ReaderWriterLockSlim> nell'applicazione per la sincronizzazione cooperativa tra i thread che accedono a una risorsa condivisa. Cui vengono acquisiti blocchi di <xref:System.Threading.ReaderWriterLockSlim> stesso.  
  
 Come con qualsiasi meccanismo di sincronizzazione di thread, è necessario assicurarsi che nessun thread ignori il blocco causato da <xref:System.Threading.ReaderWriterLockSlim>. Un modo per assicurare ciò consiste nel progettare una classe che incapsula la risorsa condivisa. Questa classe fornisce membri che accedono alla risorsa condivisa privata e che utilizzano un oggetto privato <xref:System.Threading.ReaderWriterLockSlim> per la sincronizzazione. Per un esempio, vedere l'esempio di codice per la <xref:System.Threading.ReaderWriterLockSlim> classe. <xref:System.Threading.ReaderWriterLockSlim>è abbastanza efficace da utilizzare per sincronizzare i singoli oggetti.  
  
 Strutturare l'applicazione per ridurre al minimo la durata di lettura e operazioni di scrittura. Le operazioni di scrittura lungo influiscono sulla velocità effettiva direttamente perché il blocco di scrittura è esclusivo. Writer in attesa di blocco operazioni di lettura lunghe e almeno un thread è in attesa per l'accesso in scrittura, verranno bloccati anche i thread che richiedono l'accesso in lettura.  
  
> [!NOTE]
>  Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] presenta due blocchi di lettura / scrittura, <xref:System.Threading.ReaderWriterLockSlim> e <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim>è consigliato per lo sviluppo di nuovo. <xref:System.Threading.ReaderWriterLockSlim>è simile a <xref:System.Threading.ReaderWriterLock>, ma ha regole per la ricorsione e per l'aggiornamento e il downgrade dello stato del blocco semplificate. <xref:System.Threading.ReaderWriterLockSlim>evita molti casi di potenziale deadlock. Inoltre, le prestazioni di <xref:System.Threading.ReaderWriterLockSlim> è significativamente migliore di <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md) (Oggetti e funzionalità del threading)
