---
title: 'Durata degli oggetti: come creare e distruggere oggetti'
ms.date: 07/20/2015
f1_keywords:
- vb.Constructor
helpviewer_keywords:
- destructors, object lifetime
- Sub Finalize destructor
- objects [Visual Basic], destroying
- lifetime [Visual Basic], objects
- Sub New constructor, object lifetime
- Finalize method [Visual Basic], object lifetime
- objects [Visual Basic], creating
- Class_Terminate
- Dispose method [Visual Basic], object lifetime
- Class_Initialize
- object creation [Visual Basic], object lifetime
- parameterized constructors
- objects [Visual Basic], lifetime
- objects [Visual Basic], garbage collection
- constructors [Visual Basic], object lifetime
- Sub Dispose destructor
- garbage collection [Visual Basic], Visual Basic
ms.assetid: f1ee8458-b156-44e0-9a8a-5dd171648cd8
ms.openlocfilehash: e81e131933e0997756ed4185a3ceb12ad19b78de
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392883"
---
# <a name="object-lifetime-how-objects-are-created-and-destroyed-visual-basic"></a>Durata degli oggetti: come creare ed eliminare definitivamente oggetti (Visual Basic)

È stata creata un'istanza di una classe, un oggetto, mediante la parola chiave `New`. Prima di usare i nuovi oggetti per la prima volta, è spesso necessario eseguire attività di inizializzazione. Tra le attività di inizializzazione più comuni vi sono l'apertura dei file, la connessione a un database e la lettura dei valori delle chiavi del Registro di sistema. Visual Basic controlla l'inizializzazione di nuovi oggetti usando routine denominate *costruttori* (metodi speciali che consentono il controllo dell'inizializzazione).

Dopo aver abbandona un ambito, un oggetto viene rilasciato da Common Language Runtime (CLR). Visual Basic controlla il rilascio delle risorse di sistema mediante procedure denominate *distruttori*. Sia i costruttori che i distruttori supportano la creazione di librerie di classi prevedibili e affidabili.

## <a name="using-constructors-and-destructors"></a>Uso di costruttori e distruttori

È possibile usare costruttori e distruttori per controllare la creazione e l'eliminazione di oggetti. Le `Sub New` `Sub Finalize` routine e in Visual Basic inizializzano ed eliminano oggetti; sostituiscono i `Class_Initialize` `Class_Terminate` metodi e usati in Visual Basic 6,0 e versioni precedenti.

### <a name="sub-new"></a>Sub New

Il costruttore `Sub New` può essere eseguito solo una volta dopo la creazione di una classe. Non può essere chiamato in modo esplicito in alcun punto che non sia la prima riga di codice di un altro costruttore, dalla stessa classe o da una classe derivata. Inoltre, il codice nel metodo `Sub New` viene sempre eseguito prima di qualsiasi altro codice in una classe. Visual Basic crea in modo implicito un `Sub New` costruttore in fase di esecuzione se non si definisce in modo esplicito una `Sub New` routine per una classe.

Per creare un costruttore per una classe, creare una routine denominata `Sub New` in qualsiasi punto della definizione della classe. Per creare un costruttore con parametri, specificare i nomi e i tipi di dati degli argomenti su `Sub New` analogamente a come si specificano argomenti per qualsiasi altra routine, come illustrato nel codice seguente:

[!code-vb[VbVbalrOOP#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/WhidbeyStuff.vb#42)]

I costruttori sono spesso in overload, come nell'esempio seguente:

[!code-vb[VbVbalrOOP#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/WhidbeyStuff.vb#116)]

Quando si definisce una classe derivata da un'altra classe, la prima riga di un costruttore deve essere una chiamata al costruttore della classe base, a meno che questa disponga di un costruttore accessibile che non accetta parametri. Una chiamata della classe base che contiene questo costruttore sarebbe ad esempio `MyBase.New(s)`. In caso contrario, `MyBase.New` è facoltativo e il runtime di Visual Basic lo chiama in modo implicito.

Dopo aver scritto il codice per chiamare il costruttore di un oggetto padre, è possibile aggiungere un codice di inizializzazione alla routine `Sub New`. La routine `Sub New` può accettare gli argomenti quando viene chiamata come costruttore con parametri. Tali parametri vengono passati dalla routine che chiama il costruttore, ad esempio, `Dim AnObject As New ThisClass(X)`.

### <a name="sub-finalize"></a>Sub Finalize

Prima di rilasciare oggetti, CLR richiede automaticamente al metodo `Finalize` gli oggetti che definiscono una routine `Sub Finalize`. È possibile che il metodo `Finalize` contenga codice che è necessario eseguire subito prima dell'eliminazione definitiva di un oggetto, ad esempio codice relativo alla chiusura di file e al salvataggio delle informazioni sullo stato. L'esecuzione di `Sub Finalize` comporta una lieve riduzione delle prestazioni. Si consiglia quindi di definire un metodo `Sub Finalize` solo quando è necessario rilasciare in modo esplicito gli oggetti.

> [!NOTE]
> Il Garbage Collector in CLR non (e non può) eliminare gli *oggetti non gestiti*, ovvero gli oggetti eseguiti direttamente dal sistema operativo, all'esterno dell'ambiente CLR. Questo perché i diversi oggetti non gestiti devono essere eliminati in modi differenti. Le informazioni non sono direttamente associate all'oggetto non gestito e devono quindi essere identificate nella documentazione relativa all'oggetto. Se una classe usa oggetti non gestiti, è necessario eliminarli nel relativo metodo `Finalize`.

Il distruttore `Finalize` è un metodo protetto che può essere chiamato solo dalla classe a cui appartiene o dalle classi derivate. Poiché `Finalize` viene chiamato automaticamente dal sistema quando viene eliminato definitivamente un oggetto, si consiglia di non chiamare `Finalize` in modo esplicito dall'esterno dell'implementazione `Finalize` di una classe derivata.

A differenza del metodo `Class_Terminate` che viene eseguito subito dopo aver impostato un oggetto su Nothing, tra l'abbandono dell'ambito da parte di un oggetto e la chiamata del distruttore `Finalize` da parte di Visual Basic si verifica generalmente un ritardo. Visual Basic .NET consente un secondo tipo di distruttore, <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> , che può essere chiamato in modo esplicito in qualsiasi momento per rilasciare immediatamente le risorse.

> [!NOTE]
> Un distruttore `Finalize` non deve generare eccezioni, perché queste non possono essere gestite dall'applicazione e possono provocarne l'interruzione.

### <a name="how-new-and-finalize-methods-work-in-a-class-hierarchy"></a>Uso dei metodi New e Finalize in una gerarchia di classi

Ogni volta che viene creata un'istanza di una classe, nel Common Language Runtime (CLR) viene effettuato un tentativo di eseguire una routine denominata `New`, se esiste in quell'oggetto. `New` è un tipo di routine chiamato `constructor` che consente di inizializzare nuovi oggetti prima che venga eseguito qualsiasi altro codice in un oggetto. Un costruttore `New` consente di aprire file, collegarsi a database, inizializzare variabili e svolgere ogni altra attività necessaria prima che un oggetto possa essere usato.

Quando viene creata un'istanza di una classe derivata, viene eseguito innanzitutto il costruttore `Sub New` della classe base, seguito dai costruttori delle classi derivate. Nella prima riga del codice di un costruttore `Sub New`, infatti, viene usata la sintassi `MyBase.New()` per chiamare il costruttore della classe immediatamente superiore nella gerarchia delle classi. Viene quindi eseguita la chiamata al costruttore `Sub New` di ogni classe della gerarchia fino al raggiungimento del costruttore della classe base. A quel punto viene eseguito il codice del costruttore della classe base, seguito dal codice del costruttore di tutte le classi derivate. In ultimo viene eseguito il codice delle classi derivate di livello più basso.

![Screenshot che mostra i costruttori e l'ereditarietà della gerarchia di classi.](./media/object-lifetime-how-objects-are-created-and-destroyed/subnew-constructor-inheritance.gif)

Quando un oggetto non è più necessario, prima di liberare la memoria corrispondente viene chiamato il metodo <xref:System.Object.Finalize%2A> relativo a quell'oggetto. Il metodo <xref:System.Object.Finalize%2A> è denominato `destructor`, perché consente di eseguire attività di pulizia, quali il salvataggio delle informazioni sullo stato, la chiusura dei file e delle connessioni ai database e altre attività necessarie prima del rilascio dell'oggetto.

![Screenshot che illustra il distruttore del metodo Finalize.](./media/object-lifetime-how-objects-are-created-and-destroyed/finalize-method-destructor.gif)

## <a name="idisposable-interface"></a>Interfaccia IDisposable

Le istanze di classe controllano spesso risorse non gestite da CLR, quali gli handle di Windows e le connessioni al database. È necessario eliminare definitivamente queste risorse nel metodo `Finalize` della classe per consentirne il rilascio quando il Garbage Collector elimina definitivamente l'oggetto. Tuttavia, poiché il Garbage Collector elimina definitivamente gli oggetti solo quando CLR richiede la disponibilità di maggiore memoria, è possibile che le risorse vengano rilasciate solo molto tempo dopo l'abbandono dell'ambito da parte dell'oggetto.

A supporto del Garbage Collector, le classi possono implementare l'interfaccia <xref:System.IDisposable> per fornire un sistema di gestione attiva delle risorse di sistema. <xref:System.IDisposable> dispone di un metodo, <xref:System.IDisposable.Dispose%2A> che i client chiamano dopo aver usato un oggetto. È possibile usare il metodo <xref:System.IDisposable.Dispose%2A> per rilasciare immediatamente risorse ed eseguire attività quali la chiusura di file e le connessioni al database. A differenza del distruttore `Finalize`, il metodo <xref:System.IDisposable.Dispose%2A> non viene chiamato automaticamente. Quando si vogliono rilasciare immediatamente risorse, è necessario che i client di una classe chiamino in modo esplicito il metodo <xref:System.IDisposable.Dispose%2A>.

### <a name="implementing-idisposable"></a>Implementazione di IDisposable

Una classe che implementa l'interfaccia <xref:System.IDisposable> deve includere il codice seguente:

- Campo che consente di controllare se l'oggetto è stato eliminato in modo permanente:

  ```vb
  Protected disposed As Boolean = False
  ```

- Overload del metodo <xref:System.IDisposable.Dispose%2A> che consente di liberare le risorse della classe. Questo metodo deve essere chiamato dai metodi <xref:System.IDisposable.Dispose%2A> e `Finalize` della classe base:

  ```vb
  Protected Overridable Sub Dispose(ByVal disposing As Boolean)
      If Not Me.disposed Then
          If disposing Then
              ' Insert code to free managed resources.
          End If
          ' Insert code to free unmanaged resources.
      End If
      Me.disposed = True
  End Sub
  ```

- Implementazione di <xref:System.IDisposable.Dispose%2A> che contiene solo il codice seguente:

  ```vb
  Public Sub Dispose() Implements IDisposable.Dispose
      Dispose(True)
      GC.SuppressFinalize(Me)
  End Sub
  ```

- Override del metodo `Finalize` che contiene solo il codice seguente:

  ```vb
  Protected Overrides Sub Finalize()
      Dispose(False)
      MyBase.Finalize()
  End Sub
  ```

### <a name="deriving-from-a-class-that-implements-idisposable"></a>Derivazione da una classe che implementa IDisposable

Non è necessario eseguire l'override di tutti i metodi di base in una classe derivata da una classe base che implementa l'interfaccia <xref:System.IDisposable>, a meno che tale classe non usi risorse aggiuntive che devono essere eliminate in modo permanente. In questo caso, la classe derivata deve eseguire l'override del metodo `Dispose(disposing)` della classe base per eliminare in modo permanente le risorse della classe derivata. Inoltre, tale override deve chiamare il metodo `Dispose(disposing)` della classe base.

```vb
Protected Overrides Sub Dispose(ByVal disposing As Boolean)
    If Not Me.disposed Then
        If disposing Then
            ' Insert code to free managed resources.
        End If
        ' Insert code to free unmanaged resources.
    End If
    MyBase.Dispose(disposing)
End Sub
```

Una classe derivata non deve eseguire l'override del metodi <xref:System.IDisposable.Dispose%2A> e `Finalize` della classe base. Infatti, quando questi metodi vengono chiamati da un'istanza della classe derivata, la relativa implementazione della classe base chiama l'override del metodo `Dispose(disposing)` della classe derivata.

## <a name="garbage-collection-and-the-finalize-destructor"></a>Garbage Collection e il distruttore Finalize

Il .NET Framework usa il sistema di *Garbage Collection di traccia di riferimento* per rilasciare periodicamente le risorse inutilizzate. Visual Basic 6,0 e versioni precedenti usavano un sistema diverso denominato *conteggio dei riferimenti* per gestire le risorse. Anche se in entrambi i casi viene eseguita automaticamente la stessa funzione, vi sono alcune importanti differenze.

Mediante il metodo CLR gli oggetti vengono eliminati definitivamente con cadenza periodica quando il sistema stabilisce che non sono più necessari. Gli oggetti vengono rilasciati più rapidamente quando le risorse di sistema sono insufficienti e con una frequenza minore in caso contrario. Il ritardo tra il momento in cui un oggetto abbandona l'ambito e il relativo rilascio da parte di CLR indica che, a differenza di quanto avveniva in Visual Basic 6.0 e nelle versioni precedenti, non è possibile stabilire esattamente quando l'oggetto verrà eliminato in modo permanente. In una situazione di questo tipo, si dice che gli oggetti hanno una *durata non deterministica*. Nella maggior parte dei casi la durata non deterministica non influisce sulla modalità di scrittura delle applicazioni, purché si ricordi che è possibile che il distruttore `Finalize` non venga eseguito immediatamente dopo la perdita di ambito di un oggetto.

Un'altra differenza tra i sistemi di Garbage Collection riguarda l'uso di `Nothing`. Per poter usare il conteggio dei riferimenti, in Visual Basic 6.0 e nelle versioni precedenti, a volte veniva assegnato `Nothing` alle variabili oggetto in modo da rilasciare i riferimenti contenuti in tali variabili. Se la variabile conteneva l'ultimo riferimento all'oggetto, le risorse dell'oggetto venivano rilasciate immediatamente. Anche se in alcuni casi questa routine può risultare ancora utile, la sua esecuzione nelle versioni successive di Visual Basic non risulta mai nel rilascio immediato delle risorse da parte dell'oggetto a cui si fa riferimento. Per rilasciare subito le risorse, usare il metodo <xref:System.IDisposable.Dispose%2A> dell'oggetto, se disponibile. Si consiglia di impostare una variabile su `Nothing` solo nel caso in cui la durata della variabile risulti lunga in relazione al tempo necessario per l'individuazione degli oggetti isolati tramite le operazioni del Garbage Collector.

## <a name="see-also"></a>Vedere anche

- <xref:System.IDisposable.Dispose%2A>
- [Inizializzazione e terminazione di componenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ws9dc6t6(v=vs.120))
- [Operatore New](../../../language-reference/operators/new-operator.md)
- [Pulizia delle risorse non gestite](../../../../standard/garbage-collection/unmanaged.md)
- [Nothing](../../../language-reference/nothing.md)
