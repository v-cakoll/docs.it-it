---
title: 'Archiviazione locale del thread: slot di dati e campi statici relativi ai thread'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Archiviazione locale del thread: slot di dati e campi statici relativi ai thread
È possibile utilizzare l'archiviazione locale del thread (TLS) per archiviare i dati che è univoco a un dominio applicazione e thread. .NET Framework fornisce due modalità di utilizzo gestito TLS: slot di dati e i campi statici relativi ai thread.  
  
-   Utilizzare i campi statici relativi ai thread (relativi ai thread `Shared` campi in Visual Basic) se è possibile prevedere le esigenze specifiche in fase di compilazione. I campi statici relativi ai thread forniscono prestazioni ottimali. Offrono inoltre i vantaggi del controllo dei tipi in fase di compilazione.  
  
-   Utilizzare gli slot di dati quando i requisiti effettivi possono essere individuati solo in fase di esecuzione. Gli slot di dati sono più lenti e più difficili da utilizzare rispetto ai campi statici relativi ai thread e vengono archiviati come tipo di dati <xref:System.Object>, pertanto è necessario eseguirne il cast del tipo corretto prima di utilizzarlo.  
  
 In C++ gestito, utilizza `TlsAlloc` per allocare gli slot dinamicamente e `__declspec(thread)` per dichiarare che una variabile deve essere allocata nel servizio di archiviazione relativi ai thread. Slot di dati e i campi statici relativi ai thread forniscono la versione gestita di questo comportamento.  
  
 Nel [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], è possibile utilizzare la <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> classe per creare oggetti locali del thread che vengono inizializzati in modo differito quando l'oggetto viene innanzitutto utilizzato. Per altre informazioni, vedere [Inizializzazione differita](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>Univocità dei dati in TLS gestito  
 Se si usano i campi statici relativi ai thread o slot di dati, i dati in TLS gestito sono univoci per la combinazione di thread e un dominio applicazione.  
  
-   All'interno di un dominio applicazione, un thread non è possibile modificare i dati da un altro thread, anche se entrambi i thread usano lo stesso campo o uno slot.  
  
-   Quando un thread accede lo stesso campo o lo slot da più domini applicazione, viene mantenuto un valore distinto in ogni dominio applicazione.  
  
 Ad esempio, se un thread imposta il valore di un campo statico relativi ai thread, entra in un altro dominio applicazione e quindi recupera il valore del campo, il valore recuperato nel secondo dominio applicazione è diverso dal valore nel dominio dell'applicazione prima. L'impostazione di un nuovo valore per il campo del secondo dominio di applicazione non interessa il valore del campo nel primo dominio di applicazione.  
  
 Analogamente, quando un thread ottiene lo stesso slot di dati con nome in due domini applicazione diversi, i dati nel primo dominio di applicazione rimangono indipendenti dai dati del secondo dominio di applicazione.  
  
## <a name="thread-relative-static-fields"></a>Campi statici relativi ai thread  
 Se si è certi che dei dati sono sempre univoci per una combinazione di thread e dominio di applicazione, applicare il <xref:System.ThreadStaticAttribute> attributo per il campo statico. Utilizzare il campo si utilizza qualsiasi altro campo statico. I dati nel campo sono univoci per ogni thread che lo utilizza.  
  
 I campi statici relativi ai thread forniscono prestazioni migliori rispetto agli slot di dati e il vantaggio di controllo dei tipi in fase di compilazione.  
  
 Tenere presente che qualsiasi codice del costruttore di classe verrà eseguito sul primo thread nel primo contesto che accede al campo. In tutti gli altri thread o contesti nello stesso dominio dell'applicazione, i campi verranno inizializzati su `null` (`Nothing` in Visual Basic) se sono tipi di riferimento, o sui valori predefiniti i valori sono i tipi di valore. Pertanto, deve fare affidamento sui costruttori di classe per inizializzare i campi statici relativi ai thread. Al contrario, evitare l'inizializzazione di campi statici relativi ai thread e supporre che vengano inizializzati a `null` (`Nothing`) o i valori predefiniti.  
  
## <a name="data-slots"></a>Slot di dati  
 .NET Framework fornisce gli slot di dati dinamici che sono univoci a una combinazione di thread e dominio di applicazione. Esistono due tipi di slot di dati: denominati e senza. Entrambi vengono implementati utilizzando la <xref:System.LocalDataStoreSlot> struttura.  
  
-   Per creare uno slot di dati denominato, usare il <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> o <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> metodo. Per ottenere un riferimento a uno slot denominato esistente, passare il nome per il <xref:System.Threading.Thread.GetNamedDataSlot%2A> metodo.  
  
-   Per creare uno slot di dati senza nome, utilizzare il <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> metodo.  
  
 Per entrambi denominati e senza nome slot, usare il <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> e <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> metodi per impostare e recuperare le informazioni nello slot. Si tratta di metodi statici che è sempre agiscono sui dati per il thread è in esecuzione.  
  
 Gli slot denominati possono risultare utile, perché è possibile recuperare lo slot quando è necessario passando il nome per il <xref:System.Threading.Thread.GetNamedDataSlot%2A> (metodo), invece di mantenere un riferimento a uno slot senza nome. Tuttavia, se un altro componente utilizza lo stesso nome per lo spazio di archiviazione relativi ai thread e un thread esegue codice dal componente e l'altro componente, i due componenti possono danneggiare i dati. (Questo scenario si presuppone che entrambi i componenti siano in esecuzione nello stesso dominio applicazione e che essi non sono progettati per condividere gli stessi dati)  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [Threading](../../../docs/standard/threading/index.md)
