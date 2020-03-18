---
title: 'Archiviazione locale del thread: slot di dati e campi statici relativi ai thread'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
ms.openlocfilehash: b5a7c4b78f8599f64aa11f1c98c033866e582933
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127517"
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Archiviazione locale del thread: slot di dati e campi statici relativi ai thread
È possibile usare l'archiviazione locale dei thread gestiti per archiviare dati univoci relativi a un thread e un dominio dell'applicazione. In .NET Framework sono disponibili due strumenti per usare l'archiviazione locale dei thread gestiti: i campi statici relativi ai thread e gli slot di dati.  
  
- Usare i campi statici relativi ai thread (campi `Shared` relativi ai thread in Visual Basic) se è possibile prevedere con esattezza le esigenze in fase di compilazione. I campi statici relativi ai thread forniscono infatti prestazioni ottimali. Offrono inoltre il vantaggio di poter controllare il tipo in fase di compilazione.  
  
- Se i requisiti effettivi possono essere individuati solo in fase di runtime, usare gli slot di dati. Gli slot di dati sono più lenti e scomodi da usare rispetto ai campi statici relativi ai thread e i dati vengono archiviati come tipo <xref:System.Object>. Prima di usarli, quindi, è necessario eseguirne il cast al tipo corretto.  
  
 In C++ non gestito si usa `TlsAlloc` per allocare gli slot dinamicamente e `__declspec(thread)` per dichiarare che una variabile deve essere allocata in una risorsa di archiviazione relativa ai thread. I campi statici relativi ai thread e gli slot di dati forniscono la versione gestita di questo comportamento.  
  
 In .NET Framework 4 è possibile usare la classe <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> per creare oggetti locali di thread inizializzati in modo differito quando l'oggetto viene usato per la prima volta. Per altre informazioni, vedere [Inizializzazione differita](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>Unicità dei dati nell'archiviazione locale dei thread gestiti  
 Indipendentemente dal fatto che si usino i campi statici relativi ai thread o gli slot di dati, i dati presenti nell'archiviazione locale dei thread gestiti sono univoci per la combinazione di thread e dominio dell'applicazione.  
  
- All'interno di un dominio dell'applicazione, un thread non può modificare dati provenienti da un altro thread, anche se usano entrambi lo stesso campo o slot.  
  
- Quando un thread accede allo stesso campo o slot da più domini dell'applicazione, viene mantenuto un valore separato in ogni dominio dell'applicazione.  
  
 Se, ad esempio, un thread imposta il valore di un campo statico relativo al thread, immette un altro dominio dell'applicazione e quindi recupera il valore del campo, il valore recuperato nel secondo dominio dell'applicazione differisce dal valore presente nel primo dominio dell'applicazione. L'impostazione di un nuovo valore per il campo nel secondo dominio dell'applicazione non influisce sul valore del campo nel primo dominio dell'applicazione.  
  
 Analogamente, se un thread ottiene lo stesso slot di dati denominato in due domini dell'applicazione diversi, i dati nel primo dominio dell'applicazione restano indipendenti dai dati presenti nel secondo dominio dell'applicazione.  
  
## <a name="thread-relative-static-fields"></a>Campi statici relativi ai thread  
 Se si è certi che i dati sono sempre univoci in una combinazione di thread e dominio dell'applicazione, applicare l'attributo <xref:System.ThreadStaticAttribute> al campo statico. Usare il campo come qualsiasi altro campo statico. I dati nel campo sono univoci di ogni thread che li usa.  
  
 I campi statici relativi ai thread garantiscono prestazioni migliori rispetto agli slot di dati e offrono il vantaggio di poter controllare il tipo in fase di compilazione.  
  
 Tenere presente che qualsiasi codice del costruttore di classe verrà eseguito sul primo thread nel primo contesto che accede al campo. In tutti gli altri thread o contesti nello stesso dominio dell'applicazione i campi verranno inizializzati su `null` (`Nothing` in Visual Basic) se sono tipi di riferimento o sui valori predefiniti se sono tipi valore. Di conseguenza, non è consigliabile basarsi sui costruttori delle classi per inizializzare i campi statici relativi ai thread. Al contrario, è opportuno evitare l'inizializzazione di campi statici relativi ai thread e supporre che vengano inizializzati su `null` (`Nothing`) o sui valori predefiniti.  
  
## <a name="data-slots"></a>Slot dei dati  
 .NET Framework fornisce slot di dati dinamici univoci per ogni combinazione di thread e dominio dell'applicazione. Esistono due tipi di slot di dati: con e senza nome. Entrambi vengono implementati usando la struttura <xref:System.LocalDataStoreSlot>.  
  
- Per creare uno slot di dati con nome, usare il metodo <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> o <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>. Per ottenere un riferimento a uno slot con nome esistente, passare il nome al metodo <xref:System.Threading.Thread.GetNamedDataSlot%2A>.  
  
- Per creare uno slot di dati senza nome, usare il metodo <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType>.  
  
 Per entrambi i tipo di slot, con e senza nome, usare i metodi <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> e <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> per impostare e recuperare le informazioni nello slot. Si tratta di metodi statici che agiscono sempre sui dati per il thread che li sta eseguendo.  
  
 Gli slot con nome offrono la comodità di poter essere recuperati in qualsiasi momento passandone il nome al metodo <xref:System.Threading.Thread.GetNamedDataSlot%2A>, anziché mantenere un riferimento a uno slot senza nome. Se, tuttavia, un altro componente usa lo stesso nome per la risorsa di archiviazione relativa ai thread e un thread esegue codice sia dal componente in uso che dall'altro componente, i due componenti possono danneggiare l'uno i dati dell'altro. Questo scenario presuppone che entrambi i componenti siano in esecuzione nello stesso dominio dell'applicazione e che non siano progettati per condividere gli stessi dati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ContextStaticAttribute>
- <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>
- <xref:System.ThreadStaticAttribute>
- <xref:System.Runtime.Remoting.Messaging.CallContext>
- [Threading](../../../docs/standard/threading/index.md)
