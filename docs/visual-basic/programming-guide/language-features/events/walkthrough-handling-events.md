---
title: Gestione degli eventi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: 2af8fe5557e452db1ef3a72de35582b18117cc30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54553737"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Procedura dettagliata: Gestione degli eventi (Visual Basic)
Questo è il secondo di due argomenti che illustrano come usare gli eventi. Il primo argomento, [procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), viene illustrato come dichiarare e generare eventi. Questa sezione Usa il form e classi da tale procedura dettagliata descrive come gestire gli eventi quando si verificano.  
  
 Il `Widget` esempio di classe vengono utilizzate istruzioni di gestione degli eventi tradizionale. Visual Basic fornisce altre tecniche per l'utilizzo di eventi. Come esercizio, è possibile modificare questo esempio usare il `AddHandler` e `Handles` istruzioni.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Per gestire l'evento PercentDone della classe Widget  
  
1.  Inserire il codice seguente in `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     Il `WithEvents` parola chiave specifica che la variabile `mWidget` viene utilizzata per gestire gli eventi di un oggetto. Per specificare il tipo dell'oggetto fornendo il nome della classe da cui verrà creato l'oggetto.  
  
     La variabile `mWidget` viene dichiarato in `Form1` perché `WithEvents` variabili devono essere a livello di classe. Questo vale indipendentemente dal tipo di classe in cui vengono inserite.  
  
     La variabile `mblnCancel` viene utilizzato per annullare il `LongTask` (metodo).  
  
## <a name="writing-code-to-handle-an-event"></a>Scrittura di codice per gestire un evento  
 Non appena si dichiara una variabile utilizzando `WithEvents`, il nome della variabile viene visualizzato nell'elenco di riepilogo a discesa a sinistra della classe **Editor di codice**. Quando si seleziona `mWidget`, il `Widget` gli eventi della classe vengono visualizzati nell'elenco a discesa a destra. Se si seleziona un evento consente di visualizzare la routine evento corrispondente, con il prefisso `mWidget` e un carattere di sottolineatura. Tutte le procedure di evento associate a un `WithEvents` variabile viene assegnato il nome della variabile come prefisso.  
  
#### <a name="to-handle-an-event"></a>Per gestire un evento  
  
1.  Selezionare `mWidget` dall'elenco nell'elenco a discesa a sinistra di **Editor di codice**.  
  
2.  Selezionare il `PercentDone` evento dall'elenco a discesa a destra. Il **Editor di codice** apre il `mWidget_PercentDone` routine evento.  
  
    > [!NOTE]
    >  Il **Editor di codice** è utile, ma non obbligatorio per l'inserimento di nuovi gestori di eventi. In questa procedura dettagliata, è più diretto per copiare solo i gestori di eventi direttamente nel codice.  
  
3.  Aggiungere il codice seguente al gestore eventi `mWidget_PercentDone` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Ogni volta che il `PercentDone` viene generato l'evento, la routine evento Visualizza la percentuale di completamento in un `Label` controllo. Il `DoEvents` metodo consente di ridisegnare l'etichetta e inoltre fornisce all'utente la possibilità di scegliere il **annullare** pulsante.  
  
4.  Aggiungere il codice seguente per il `Button2_Click` gestore dell'evento:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Se l'utente fa clic il **annullare** pulsante durante `LongTask` è in esecuzione, il `Button2_Click` viene eseguito l'evento, non appena il `DoEvents` istruzione consente l'elaborazione degli eventi. La variabile a livello di classe `mblnCancel` è impostata su `True`e il `mWidget_PercentDone` evento quindi ne esegue il test e imposta il `ByRef Cancel` argomento `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>La connessione di una variabile WithEvents a un oggetto  
 `Form1` è ora configurato per gestire un `Widget` eventi dell'oggetto. Questo punto, è trovare un `Widget` da qualche parte.  
  
 Quando si dichiara una variabile `WithEvents` in fase di progettazione non è associato alcun oggetto. Oggetto `WithEvents` variabile è proprio come qualsiasi altra variabile oggetto. È necessario creare un oggetto e assegnare un riferimento a esso con il `WithEvents` variabile.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Per creare un oggetto e assegnare un riferimento a esso  
  
1.  Selezionare **(eventi di Form1)** dall'elenco nell'elenco a discesa a sinistra il **Editor di codice**.  
  
2.  Selezionare il `Load` evento dall'elenco a discesa a destra. Il **Editor di codice** apre il `Form1_Load` routine evento.  
  
3.  Aggiungere il codice seguente per il `Form1_Load` routine evento per creare il `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Quando si esegue questo codice, Visual Basic crea un `Widget` dell'oggetto e si connette gli eventi per le procedure di evento associate `mWidget`. Da quel momento, ogni volta che il `Widget` genera relativi `PercentDone` evento, il `mWidget_PercentDone` evento procedure viene eseguita.  
  
#### <a name="to-call-the-longtask-method"></a>Per chiamare il metodo di LongTask  
  
-   Aggiungere il codice seguente al gestore eventi `Button1_Click` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Prima di `LongTask` metodo viene chiamato, l'etichetta che visualizza la percentuale di completamento deve essere inizializzato e il livello di classe `Boolean` flag dell'annullamento del metodo deve essere impostata su `False`.  
  
 `LongTask` viene chiamato con una durata di attività di 12,2 secondi. Il `PercentDone` l'evento viene generato una volta ogni un terzo di secondo. Ogni volta che viene generato l'evento, il `mWidget_PercentDone` evento procedure viene eseguita.  
  
 Quando `LongTask` viene eseguita `mblnCancel` viene testato per verificare se `LongTask` è stato completato correttamente, o se è stato arrestato perché `mblnCancel` è stato impostato su `True`. La percentuale di completamento viene aggiornata solo nel caso precedente.  
  
#### <a name="to-run-the-program"></a>Per eseguire il programma  
  
1.  Premere F5 per attivare il progetto in modalità di esecuzione.  
  
2.  Scegliere il **Avvia attività** pulsante. Ogni volta che il `PercentDone` viene generato l'evento, l'etichetta viene aggiornato con la percentuale di completamento dell'attività.  
  
3.  Scegliere il **annullare** pulsante per arrestare l'attività. Si noti che l'aspetto del **annullare** pulsante non influisce immediatamente quando si fa clic. Il `Click` evento non può essere eseguita finché il `My.Application.DoEvents` istruzione consente l'elaborazione di eventi.  
  
    > [!NOTE]
    >  Il `My.Application.DoEvents` metodo non elabora gli eventi in esattamente allo stesso modo del form. Ad esempio, in questa procedura dettagliata, è necessario fare clic il **annullare** due volte sul pulsante. Per consentire al modulo gestire gli eventi direttamente, è possibile utilizzare il multithreading. Per altre informazioni, vedere [Managed Threading](../../../../standard/threading/index.md).
  
 Può risultare interessante eseguire il programma con F11 e scorrere il codice una riga alla volta. Si può vedere chiaramente come l'esecuzione entra `LongTask`e quindi reimmesso `Form1` ogni volta che il `PercentDone` viene generato l'evento.  
  
 Che cosa accadrebbe se, durante l'esecuzione torna nel codice del `Form1`, il `LongTask` metodo venisse chiamata nuovamente? Nel peggiore dei casi, potrebbe verificarsi un overflow dello stack se `LongTask` chiamate ogni volta che è stato generato l'evento.  
  
 È possibile che la variabile `mWidget` per gestire gli eventi per un altro `Widget` tramite l'assegnazione di un riferimento al nuovo oggetto `Widget` a `mWidget`. In effetti, è possibile rendere il codice in `Button1_Click` eseguire questa operazione ogni volta che si fa clic sul pulsante.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Per gestire gli eventi per un widget diversi  
  
-   Aggiungere la seguente riga di codice per il `Button1_Click` routine, precede la riga che legge `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 Il codice precedente crea un nuovo `Widget` ogni volta che viene scelto il pulsante. Non appena il `LongTask` metodo viene completato, il riferimento al `Widget` viene rilasciato e il `Widget` viene eliminato definitivamente.  
  
 Oggetto `WithEvents` variabile può contenere un solo riferimento oggetto alla volta, pertanto se si assegna un diverso `Widget` oggetto `mWidget`, precedente `Widget` non verranno gestiti non è più eventi dell'oggetto. Se `mWidget` è l'unica variabile di oggetto che contiene un riferimento ai precedenti `Widget`, l'oggetto viene eliminato. Se si desidera gestire gli eventi da diversi `Widget` oggetti, usare il `AddHandler` istruzione per elaborare eventi da ogni oggetto separatamente.  
  
> [!NOTE]
>  È possibile dichiarare tante `WithEvents` di variabili necessarie, ma le matrici di `WithEvents` variabili non sono supportate.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
