---
title: "Procedura: abilitare la modalità di rilevamento thread in SpinLock"
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Procedura: abilitare la modalità di rilevamento thread in SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType>è un blocco a esclusione reciproca di basso livello che è possibile utilizzare per gli scenari con tempi di attesa molto brevi. <xref:System.Threading.SpinLock>non è rientrante. Dopo che un thread viene inserito il blocco, è necessario uscirne correttamente prima di potervi accedere nuovamente. In genere, qualsiasi tentativo di immettere di nuovo il blocco causerebbe un deadlock e deadlock possono essere molto difficili eseguire il debug. Come ausilio per lo sviluppo, di <xref:System.Threading.SpinLock?displayProperty=nameWithType> supporta una modalità di rilevamento thread che genera un'eccezione generata quando un thread tenta di immettere nuovamente un blocco che contiene già. Ciò consente di che individuare più facilmente il punto in cui il blocco non è stato terminato correttamente. È possibile attivare la modalità di rilevamento thread usando il <xref:System.Threading.SpinLock> costruttore che accetta un valore booleano di input e passando un argomento di `true`. Dopo aver completato le fasi di sviluppo e test, disattivare la modalità di rilevamento thread per ottenere prestazioni migliori.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente illustra la modalità di rilevamento thread. Sono impostate come commento le righe che uscirne correttamente per simulare un errore di codifica che causa uno dei risultati seguenti:  
  
-   Viene generata un'eccezione se il <xref:System.Threading.SpinLock> è stato creato utilizzando un argomento di `true` (`True` in Visual Basic).  
  
-   Un deadlock se la <xref:System.Threading.SpinLock> è stato creato utilizzando un argomento di `false` (`False` in Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Vedere anche  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
