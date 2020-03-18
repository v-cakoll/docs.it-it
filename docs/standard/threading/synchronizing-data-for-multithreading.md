---
title: Sincronizzazione dei dati per il multithreading
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization, threads
- threading [.NET], synchronizing threads
- managed threading
ms.assetid: b980eb4c-71d5-4860-864a-6dfe3692430a
ms.openlocfilehash: a70bd3070d8b1dcd06e55d330a01d29071293f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159390"
---
# <a name="synchronizing-data-for-multithreading"></a>Sincronizzazione dei dati per il multithreading

Se più thread sono in grado di effettuare chiamate alle proprietà e ai metodi di un singolo oggetto, è essenziale che tali chiamate siano sincronizzate. In caso contrario un thread potrebbe interrompere le operazioni eseguite da un altro thread e l'oggetto potrebbe rimanere in uno stato non valido. Una classe i cui membri sono protetti da tali interruzioni è detta thread-safe.  
  
.NET offre diverse strategie per sincronizzare l'accesso a membri statici e di istanza:  
  
- Aree di codice sincronizzate. È possibile usare la classe <xref:System.Threading.Monitor> o il supporto del compilatore per questa classe per sincronizzare solo il codice di blocco necessario, migliorando le prestazioni.  
  
- Sincronizzazione manuale. È possibile usare gli oggetti di sincronizzazione della libreria di classi .NET. Vedere la [panoramica sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md), che include una descrizione della classe <xref:System.Threading.Monitor>.  
  
- Contesti sincronizzati. Per le applicazioni .NET Framework e Xamarin, è possibile usare <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> per abilitare la sincronizzazione semplice e automatica per gli oggetti <xref:System.ContextBoundObject>.  
  
- Classi delle raccolte nello spazio dei nomi <xref:System.Collections.Concurrent?displayProperty=nameWithType>. Queste classi consentono di eseguire operazioni di aggiunta e rimozione incorporate sincronizzate. Per altre informazioni, vedere [Raccolte thread-safe](../../../docs/standard/collections/thread-safe/index.md).  
  
 Common Language Runtime offre un modello di thread in cui le classi rientrano in un numero di categorie che possono essere sincronizzate in molti modi in base ai requisiti. La tabella seguente indica il supporto di sincronizzazione disponibile per campi e metodi con una determinata categoria di sincronizzazione.  
  
|Category|Campi globali|Campi statici|Metodi statici|Campi di istanza|Metodi di istanza|Blocchi di codice specifici|  
|--------------|-------------------|-------------------|--------------------|---------------------|----------------------|--------------------------|  
|Nessuna sincronizzazione|No|No|No|No|No|No|  
|Contesto sincronizzato|No|No|No|Sì|Sì|No|  
|Aree di codice sincronizzate|No|No|Solo se contrassegnato|No|Solo se contrassegnato|Solo se contrassegnato|  
|Sincronizzazione manuale|Manuale|Manuale|Manuale|Manuale|Manuale|Manuale|  
  
## <a name="no-synchronization"></a>Nessuna sincronizzazione  
 Questa è l'impostazione predefinita per gli oggetti. Qualsiasi thread può accedere a qualsiasi metodo o campo in qualsiasi momento. Un solo thread alla volta deve accedere a questi oggetti.  
  
## <a name="manual-synchronization"></a>Sincronizzazione manuale  
 La libreria di classi .NET offre diverse classi per la sincronizzazione dei thread. Vedere [Cenni preliminari sulle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
## <a name="synchronized-code-regions"></a>Aree di codice sincronizzate  
 È possibile usare la classe <xref:System.Threading.Monitor> o una parola chiave del compilatore per sincronizzare aree di codice, metodi di istanza e metodi statici. Non esiste un supporto per i campi statici sincronizzati.  
  
 Sia Visual Basic che C# supportano il contrassegno delle aree di codice con una parola chiave del linguaggio specifico, l'istruzione `lock` in C# o l'istruzione `SyncLock` in Visual Basic. Quando il codice viene eseguito da un thread, viene effettuato un tentativo di acquisire il blocco. Se il blocco è già stato acquisito da un altro thread, il thread si blocca finché il blocco non diventa disponibile. Quando il thread esce dall'area di codice sincronizzata, il blocco viene rilasciato, indipendentemente dal modo in cui il thread esce dall'area.  
  
> [!NOTE]
> Le istruzioni `lock` e `SyncLock` vengono implementate usando <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType>. Pertanto gli altri metodi di <xref:System.Threading.Monitor> possono essere usati in combinazione all'interno dell'area sincronizzata.  
  
 È anche possibile decorare un metodo con <xref:System.Runtime.CompilerServices.MethodImplAttribute> con un valore <xref:System.Runtime.CompilerServices.MethodImplOptions.Synchronized?displayProperty=nameWithType>, ottenendo lo stesso effetto dell'uso di <xref:System.Threading.Monitor> o di una delle parole chiave del compilatore per bloccare l'intero corpo del metodo.  
  
 <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> può essere usato per interrompere le operazioni di blocco di un thread, ad esempio in attesa dell'accesso a un'area di codice sincronizzata di un thread. **Thread.Interrupt** viene usato anche per interrompere l'esecuzione dei thread, ad esempio <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>.  
  
> [!IMPORTANT]
> Non bloccare il tipo, ovvero `typeof(MyType)` in C#, `GetType(MyType)` in Visual Basic o `MyType::typeid` in C++, per proteggere i metodi `static` (metodi `Shared` in Visual Basic). Usare invece un oggetto statico privato. Analogamente, non usare `this` in C# (`Me` in Visual Basic) per bloccare i metodi di istanza. Usare invece un oggetto privato. Una classe o istanza può essere bloccata da un codice diverso dal proprio, causando potenzialmente deadlock o problemi di prestazioni.  
  
### <a name="compiler-support"></a>Supporto del compilatore  
 Visual Basic e C# supportano una parola chiave del linguaggio che usa <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> e <xref:System.Threading.Monitor.Exit%2A?displayProperty=nameWithType> per bloccare l'oggetto. Visual Basic supporta l'istruzione [SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md), C# supporta l'istruzione [lock](../../csharp/language-reference/keywords/lock-statement.md).  
  
 In entrambi i casi, se viene generata un'eccezione nell'area di codice, il blocco acquisito da **lock** o **SyncLock** viene rilasciato automaticamente. I compilatori di C e Visual Basic generano un blocco **finally try**/**finally** con **Monitor.Enter** all'inizio di try e **Monitor.Exit** nel blocco **finally.** Se viene generata un'eccezione all'interno del blocco **lock** o **SyncLock**, viene eseguito il gestore **finally** per consentire l'esecuzione di operazioni di pulizia.  
  
## <a name="synchronized-context"></a>Contesto sincronizzato  

Solo nelle applicazioni .NET Framework e Xamarin è possibile usare <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> in qualsiasi <xref:System.ContextBoundObject> per sincronizzare tutti i campi e i metodi di istanza. Tutti gli oggetti nello stesso dominio di contesto condividono lo stesso blocco. Più thread possono accedere ai metodi e ai campi, ma è consentito un singolo thread alla volta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute>
- [Thread e threading](../../../docs/standard/threading/threads-and-threading.md)
- [Panoramica delle primitive di sincronizzazione](../../../docs/standard/threading/overview-of-synchronization-primitives.md)
- [Istruzione SyncLock](../../visual-basic/language-reference/statements/synclock-statement.md)
- [Istruzione lock](../../csharp/language-reference/keywords/lock-statement.md)
