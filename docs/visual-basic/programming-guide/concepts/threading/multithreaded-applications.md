---
title: Applicazioni multithreading (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 02b0444b-2e68-4f2c-bc28-28c046004017
ms.openlocfilehash: ab4b8d1c77ae75aee6f2cf459258766f88d86abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650478"
---
# <a name="multithreaded-applications-visual-basic"></a>Applicazioni multithreading (Visual Basic)
Con Visual Basic, è possibile scrivere applicazioni che eseguono più attività contemporaneamente. Le attività potenzialmente in grado di compromettere altre attività possono essere eseguite su thread separati, un processo noto con il nome di *multithreading* o *threading Free*.  
  
 Le applicazioni che usano il multithreading sono più reattive all'input dell'utente poiché l'interfaccia utente rimane attiva mentre le attività che richiedono un uso intensivo del processore vengono eseguite su thread separati. Il multithreading è utile anche durante la creazione di applicazioni scalabili poiché consente di aggiungere thread man mano che aumenta il carico di lavoro.  
  
## <a name="creating-and-using-threads"></a>Creazione e uso dei thread  
 Nel caso sia necessario un maggiore controllo sul comportamento dei thread dell'applicazione, è possibile gestirli personalmente. È tuttavia necessario tenere presente che la scrittura di applicazioni multithreading complesse può essere difficile: l'applicazione potrebbe non rispondere o essere soggetta a errori temporanei dovuti a race condition. Per altre informazioni, vedere [Componenti thread-safe](http://msdn.microsoft.com/library/4f7c7377-a782-4bd0-aaa3-9db8c12945ee).  
  
 Per creare un nuovo thread è necessario dichiarare una variabile di tipo <xref:System.Threading.Thread> e chiamare il costruttore, specificando il nome della routine o del metodo che si vuole eseguire nel nuovo thread. Nel codice seguente ne viene illustrato un esempio.  
  
```vb  
Dim newThread As New System.Threading.Thread(AddressOf AMethod)  
```  
  
### <a name="starting-and-stopping-threads"></a>Avvio e arresto dei thread  
 Per avviare l'esecuzione di un nuovo thread, usare il metodo <xref:System.Threading.Thread.Start%2A> come illustrato nel codice seguente.  
  
```vb  
newThread.Start()  
```  
  
 Per arrestare l'esecuzione di un thread, usare il metodo <xref:System.Threading.Thread.Abort%2A> come illustrato nel codice seguente.  
  
```vb  
newThread.Abort()  
```  
  
 Oltre a eseguire le operazioni di avvio e interruzione, è possibile anche sospendere un thread chiamando il metodo <xref:System.Threading.Thread.Sleep%2A> o <xref:System.Threading.Thread.Suspend%2A>, riprendere un thread sospeso usando il metodo <xref:System.Threading.Thread.Resume%2A> o eliminare un thread usando il metodo <xref:System.Threading.Thread.Abort%2A>.  
  
### <a name="thread-methods"></a>Metodi di thread  
 La tabella seguente descrive alcuni metodi che è possibile usare per controllare i singoli thread.  
  
|Metodo|Operazione|  
|------------|------------|  
|<xref:System.Threading.Thread.Start%2A>|Avvia l'esecuzione di un thread.|  
|<xref:System.Threading.Thread.Sleep%2A>|Sospende un thread per un determinato periodo.|  
|<xref:System.Threading.Thread.Suspend%2A>|Sospende un thread quando raggiunge un punto sicuro.|  
|<xref:System.Threading.Thread.Abort%2A>|Arresta un thread quando raggiunge un punto sicuro.|  
|<xref:System.Threading.Thread.Resume%2A>|Riavvia un thread sospeso.|  
|<xref:System.Threading.Thread.Join%2A>|Fa in modo che il thread corrente attenda il completamento di un altro thread. Se usato con un valore di timeout, questo metodo restituisce `True` se il thread viene completato nel tempo allocato.|  
  
### <a name="safe-points"></a>Punti sicuri  
 La maggior parte di questi metodi non necessita di descrizione, ma il concetto di *punto sicuro* potrebbe risultare nuovo. I punti sicuri sono posizioni nel codice in cui Common Language Runtime può eseguire in sicurezza il processo di *Garbage Collection* automatico, il rilascio delle variabili inutilizzate e la richiesta di memoria. Quando viene eseguita una chiamata al metodo <xref:System.Threading.Thread.Abort%2A> o <xref:System.Threading.Thread.Suspend%2A> di un thread, Common Language Runtime analizza il codice e determina una posizione appropriata in cui arrestare l'esecuzione del thread.  
  
### <a name="thread-properties"></a>Proprietà thread  
 I thread includono anche diverse proprietà utili, come illustrato nella tabella seguente:  
  
|Proprietà|Valore|  
|--------------|-----------|  
|<xref:System.Threading.Thread.IsAlive%2A>|Contiene il valore `True` se il thread è attivo.|  
|<xref:System.Threading.Thread.IsBackground%2A>|Ottiene o imposta un valore booleano che indica se un thread è o deve essere un thread in background. I thread in background sono simili ai thread in primo piano, ma un thread in background non impedisce l'arresto di un processo. Dopo l'arresto di tutti i thread in primo piano che appartengono a un processo, Common Language Runtime termina il processo chiamando il metodo <xref:System.Threading.Thread.Abort%2A> nei thread in background ancora attivi.|  
|<xref:System.Threading.Thread.Name%2A>|Ottiene o imposta il nome del thread. Usato in genere per individuare i singoli thread durante il debug.|  
|<xref:System.Threading.Thread.Priority%2A>|Ottiene o imposta un valore che viene usato dal sistema operativo per definire le priorità di pianificazione dei thread.|  
|<xref:System.Threading.Thread.ThreadState%2A>|Contiene un valore che descrive lo stato o gli stati di un thread.|  
  
## <a name="thread-priorities"></a>Priorità dei thread  
 Ogni thread ha una proprietà di priorità che determina il periodo di tempo del processore disponibile per la sua esecuzione. Il sistema operativo alloca periodi più lunghi ai thread ad alta priorità e periodi più brevi ai thread a bassa priorità. I nuovi thread vengono creati con il valore `Normal`, ma è possibile modificare la proprietà <xref:System.Threading.Thread.Priority%2A> impostandola su qualsiasi valore nell'enumerazione <xref:System.Threading.ThreadPriority>.  
  
 Per una descrizione dettagliata delle diverse priorità dei thread, vedere <xref:System.Threading.ThreadPriority>.  
  
## <a name="foreground-and-background-threads"></a>Thread in primo piano e in background  
 I *thread in primo piano* vengono eseguiti a oltranza, mentre i *thread in background* vengono arrestati non appena l'ultimo thread in primo piano è stato arrestato. È possibile usare la proprietà <xref:System.Threading.Thread.IsBackground%2A> per determinare o modificare lo stato di background di un thread.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Threading.Thread>  
 [Sincronizzazione di thread (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)  
 [Parametri e valori restituiti per routine multithreading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)  
 [Threading (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/index.md)
