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
ms.openlocfilehash: 12267e0a70419298bc581421c4f3a220088d205f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956307"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Procedura dettagliata: Gestione degli eventi (Visual Basic)
Questo è il secondo di due argomenti in cui viene illustrato come utilizzare gli eventi. Il primo argomento, [procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), Mostra come dichiarare e generare eventi. In questa sezione vengono usati il form e la classe di questa procedura dettagliata per illustrare come gestire gli eventi quando si verificano.  
  
 Nell' `Widget` esempio di classe vengono utilizzate istruzioni tradizionali di gestione degli eventi. Visual Basic fornisce altre tecniche per l'utilizzo degli eventi. Come esercizio, è possibile modificare questo esempio per usare le `AddHandler` istruzioni e. `Handles`  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Per gestire l'evento PercentDone della classe widget  
  
1. Inserire il codice seguente in `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     La `WithEvents` parola chiave specifica che la `mWidget` variabile viene utilizzata per gestire gli eventi di un oggetto. Specificare il tipo di oggetto fornendo il nome della classe da cui verrà creato l'oggetto.  
  
     La variabile `mWidget` è dichiarata `WithEvents` in perché le variabili devono essere a livello di `Form1` classe. Questo vale indipendentemente dal tipo di classe in cui vengono inserite.  
  
     La variabile `mblnCancel` viene usata per annullare il `LongTask` metodo.  
  
## <a name="writing-code-to-handle-an-event"></a>Scrittura di codice per la gestione di un evento  
 Non appena si dichiara una variabile usando `WithEvents`, il nome della variabile viene visualizzato nell'elenco a discesa a sinistra dell'editor di **codice**della classe. Quando si seleziona `mWidget`, gli `Widget` eventi della classe vengono visualizzati nell'elenco a discesa a destra. Se si seleziona un evento, viene visualizzata la routine evento corrispondente `mWidget` con il prefisso e un carattere di sottolineatura. A tutte le routine di evento associate `WithEvents` a una variabile viene assegnato il nome della variabile come prefisso.  
  
#### <a name="to-handle-an-event"></a>Per gestire un evento  
  
1. Selezionare `mWidget` dall'elenco a discesa a sinistra nell'editor di **codice**.  
  
2. Selezionare l' `PercentDone` evento dall'elenco a discesa a destra. Nell' **editor di codice** viene `mWidget_PercentDone` aperta la routine evento.  
  
    > [!NOTE]
    > L' **editor di codice** è utile, ma non obbligatorio, per l'inserimento di nuovi gestori di eventi. In questa procedura dettagliata è più diretto copiare semplicemente i gestori eventi direttamente nel codice.  
  
3. Aggiungere il codice seguente al gestore eventi `mWidget_PercentDone` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     Ogni volta `PercentDone` che viene generato l'evento, nella routine dell'evento viene visualizzata la `Label` percentuale di completamento in un controllo. Il `DoEvents` metodo consente di ridisegnare l'etichetta e offre all'utente anche la possibilità di fare clic sul pulsante **Annulla** .  
  
4. Aggiungere il codice seguente per il `Button2_Click` gestore eventi:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Se l'utente fa clic sul pulsante Annulla `LongTask` mentre è in esecuzione `Button2_Click` , l'evento viene eseguito non appena `DoEvents` l'istruzione consente l'elaborazione di eventi. La variabile `mblnCancel` a livello di classe è impostata `True`su e l' `mWidget_PercentDone` evento lo testa e imposta l' `ByRef Cancel` argomento su `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Connessione di una variabile WithEvents a un oggetto  
 `Form1`è ora configurato per gestire gli eventi `Widget` di un oggetto. Tutto ciò che rimane è trovare un `Widget` punto.  
  
 Quando si dichiara una variabile `WithEvents` in fase di progettazione, non vi è alcun oggetto associato. Una `WithEvents` variabile è analoga a qualsiasi altra variabile oggetto. È necessario creare un oggetto e assegnarvi un riferimento con la `WithEvents` variabile.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Per creare un oggetto e assegnarvi un riferimento  
  
1. Selezionare **(eventi Form1)** nell'elenco a discesa a sinistra nell'editor di **codice**.  
  
2. Selezionare l' `Load` evento dall'elenco a discesa a destra. Nell' **editor di codice** viene `Form1_Load` aperta la routine evento.  
  
3. Aggiungere il codice seguente per la `Form1_Load` routine evento per `Widget`creare:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 Quando questo codice viene eseguito, Visual Basic crea un `Widget` oggetto e connette i relativi eventi alle routine di evento associate `mWidget`a. Da quel momento in poi, ogni `Widget` volta che `PercentDone` il genera l' `mWidget_PercentDone` evento, viene eseguita la routine dell'evento.  
  
#### <a name="to-call-the-longtask-method"></a>Per chiamare il metodo LongTask  
  
- Aggiungere il codice seguente al gestore eventi `Button1_Click` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Prima che `LongTask` venga chiamato il metodo, l'etichetta che visualizza la percentuale di completamento deve essere inizializzata e il flag `Boolean` a livello di classe per l'annullamento del metodo deve `False`essere impostato su.  
  
 `LongTask`viene chiamato con una durata dell'attività di 12,2 secondi. L' `PercentDone` evento viene generato una volta ogni un terzo di un secondo. Ogni volta che viene generato l'evento, `mWidget_PercentDone` viene eseguita la routine dell'evento.  
  
 `mblnCancel` `LongTask` `mblnCancel` Al termine, viene testato per verificare se è terminato normalmente o se è stato interrotto perché è stato impostato `True`su. `LongTask` La percentuale di completamento viene aggiornata solo nel caso precedente.  
  
#### <a name="to-run-the-program"></a>Per eseguire il programma  
  
1. Premere F5 per inserire il progetto in modalità di esecuzione.  
  
2. Fare clic sul pulsante **Avvia attività** . Ogni volta che `PercentDone` viene generato l'evento, l'etichetta viene aggiornata con la percentuale dell'attività completata.  
  
3. Fare clic sul pulsante **Annulla** per arrestare l'attività. Si noti che l'aspetto del pulsante **Annulla** non viene modificato immediatamente quando si fa clic su di esso. L' `Click` evento non può verificarsi fino `My.Application.DoEvents` a quando l'istruzione non consente l'elaborazione di eventi.  
  
    > [!NOTE]
    > Il `My.Application.DoEvents` metodo non elabora gli eventi esattamente allo stesso modo del modulo. In questa procedura dettagliata, ad esempio, è necessario fare clic due volte sul pulsante **Annulla** . Per consentire al modulo di gestire direttamente gli eventi, è possibile utilizzare il multithreading. Per altre informazioni, vedere [Threading gestito](../../../../standard/threading/index.md).
  
 Potrebbe risultare istruttivo eseguire il programma con F11 e scorrere il codice una riga alla volta. È possibile vedere chiaramente il modo in `LongTask`cui l'esecuzione entra, quindi immettere `Form1` di nuovo brevemente `PercentDone` ogni volta che viene generato l'evento.  
  
 Cosa accadrebbe se, durante l'esecuzione fosse tornato nel codice di `Form1`, il `LongTask` metodo veniva chiamato di nuovo? Al peggiore, potrebbe verificarsi un overflow dello stack `LongTask` se venivano chiamati ogni volta che l'evento è stato generato.  
  
 È possibile fare in modo `mWidget` che la variabile gestisca gli `Widget` eventi per un oggetto diverso assegnando un riferimento `Widget` al `mWidget`nuovo a. In realtà, è possibile fare in `Button1_Click` modo che il codice esegua questa operazione ogni volta che si fa clic sul pulsante.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Per gestire gli eventi per un widget diverso  
  
- Aggiungere la seguente riga di codice alla `Button1_Click` procedura, immediatamente prima della riga che legge: `mWidget.LongTask(12.2, 0.33)`  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Il codice precedente crea un nuovo `Widget` oggetto ogni volta che si fa clic sul pulsante. Non appena il `LongTask` metodo viene completato, il riferimento all'oggetto `Widget` `Widget` viene rilasciato e viene eliminato definitivamente.  
  
 Una `WithEvents` variabile può contenere solo un riferimento a un oggetto alla volta, pertanto se si assegna un `Widget` oggetto diverso `mWidget`a, gli `Widget` eventi dell'oggetto precedente non verranno più gestiti. Se `mWidget` è l'unica variabile oggetto contenente un riferimento al precedente `Widget`, l'oggetto viene eliminato definitivamente. Se si desidera gestire gli eventi di diversi `Widget` oggetti, utilizzare l' `AddHandler` istruzione per elaborare separatamente gli eventi da ogni oggetto.  
  
> [!NOTE]
> È possibile dichiarare il numero `WithEvents` di variabili necessario, ma le matrici di `WithEvents` variabili non sono supportate.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
