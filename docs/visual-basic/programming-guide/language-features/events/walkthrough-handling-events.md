---
title: Gestione degli eventi
ms.date: 07/20/2015
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
ms.openlocfilehash: cb42f2e41e366cf8765cb9395d1a5641434bab40
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345076"
---
# <a name="walkthrough-handling-events-visual-basic"></a>Procedura dettagliata: gestione di eventi (Visual Basic)
Questo è il secondo di due argomenti in cui viene illustrato come utilizzare gli eventi. Il primo argomento, [procedura dettagliata: dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), Mostra come dichiarare e generare eventi. In questa sezione vengono usati il form e la classe di questa procedura dettagliata per illustrare come gestire gli eventi quando si verificano.  
  
 Nell'esempio di classe `Widget` vengono utilizzate le istruzioni tradizionali di gestione degli eventi. Visual Basic fornisce altre tecniche per l'utilizzo degli eventi. Come esercizio, è possibile modificare questo esempio per usare le istruzioni `AddHandler` e `Handles`.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Per gestire l'evento PercentDone della classe widget  
  
1. Inserire il codice seguente in `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#4)]  
  
     La parola chiave `WithEvents` specifica che la variabile `mWidget` viene utilizzata per gestire gli eventi di un oggetto. Specificare il tipo di oggetto fornendo il nome della classe da cui verrà creato l'oggetto.  
  
     La variabile `mWidget` viene dichiarata in `Form1` perché le variabili `WithEvents` devono essere a livello di classe. Questo vale indipendentemente dal tipo di classe in cui vengono inserite.  
  
     La variabile `mblnCancel` viene utilizzata per annullare il `LongTask` metodo.  
  
## <a name="writing-code-to-handle-an-event"></a>Scrittura di codice per la gestione di un evento  
 Non appena si dichiara una variabile con `WithEvents`, il nome della variabile viene visualizzato nell'elenco a discesa a sinistra dell' **editor di codice**della classe. Quando si seleziona `mWidget`, gli eventi della classe `Widget` vengono visualizzati nell'elenco a discesa a destra. Se si seleziona un evento, viene visualizzata la routine evento corrispondente con il prefisso `mWidget` e un carattere di sottolineatura. A tutte le routine di evento associate a una variabile `WithEvents` viene assegnato il nome della variabile come prefisso.  
  
#### <a name="to-handle-an-event"></a>Per gestire un evento  
  
1. Selezionare `mWidget` dall'elenco a discesa a sinistra nell'editor di **codice**.  
  
2. Selezionare l'evento `PercentDone` dall'elenco a discesa a destra. Nell' **editor di codice** viene aperta la procedura `mWidget_PercentDone` evento.  
  
    > [!NOTE]
    > L' **editor di codice** è utile, ma non obbligatorio, per l'inserimento di nuovi gestori di eventi. In questa procedura dettagliata è più diretto copiare semplicemente i gestori eventi direttamente nel codice.  
  
3. Aggiungere il codice seguente al gestore eventi `mWidget_PercentDone` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#5)]  
  
     Ogni volta che viene generato l'evento `PercentDone`, nella routine evento viene visualizzata la percentuale di completamento in un controllo `Label`. Il metodo di `DoEvents` consente di ridisegnare l'etichetta e offre all'utente la possibilità di fare clic sul pulsante **Annulla** .  
  
4. Aggiungere il seguente codice per il gestore dell'evento `Button2_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#6)]  
  
 Se l'utente fa clic sul pulsante **Annulla** mentre `LongTask` è in esecuzione, l'evento `Button2_Click` viene eseguito non appena l'istruzione `DoEvents` consente l'elaborazione degli eventi. La variabile a livello di classe `mblnCancel` è impostata su `True`e l'evento `mWidget_PercentDone` lo testa e imposta l'argomento `ByRef Cancel` su `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Connessione di una variabile WithEvents a un oggetto  
 `Form1` è ora configurato per gestire gli eventi di un oggetto `Widget`. Non resta che trovare un `Widget` in un punto qualsiasi.  
  
 Quando si dichiara una variabile `WithEvents` in fase di progettazione, non vi è alcun oggetto associato. Una variabile `WithEvents` è analoga a qualsiasi altra variabile oggetto. È necessario creare un oggetto e assegnarvi un riferimento con la variabile `WithEvents`.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Per creare un oggetto e assegnarvi un riferimento  
  
1. Selezionare **(eventi Form1)** nell'elenco a discesa a sinistra nell'editor di **codice**.  
  
2. Selezionare l'evento `Load` dall'elenco a discesa a destra. Nell' **editor di codice** viene aperta la procedura `Form1_Load` evento.  
  
3. Aggiungere il codice seguente per la procedura `Form1_Load` evento per creare il `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#7)]  
  
 Quando viene eseguito questo codice, Visual Basic crea un oggetto `Widget` e connette gli eventi alle routine di evento associate a `mWidget`. Da quel momento in poi, ogni volta che il `Widget` genera il relativo evento `PercentDone`, viene eseguita la procedura di `mWidget_PercentDone` evento.  
  
#### <a name="to-call-the-longtask-method"></a>Per chiamare il metodo LongTask  
  
- Aggiungere il codice seguente al gestore eventi `Button1_Click` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#8)]  
  
 Prima che venga chiamato il metodo `LongTask`, è necessario inizializzare l'etichetta che visualizza la percentuale di completamento e il flag di `Boolean` a livello di classe per annullare il metodo deve essere impostato su `False`.  
  
 `LongTask` viene chiamato con una durata dell'attività di 12,2 secondi. L'evento `PercentDone` viene generato una volta ogni un terzo di un secondo. Ogni volta che viene generato l'evento, viene eseguita la procedura `mWidget_PercentDone` evento.  
  
 Al termine `LongTask`, `mblnCancel` viene testato per verificare se `LongTask` termina normalmente o se è stato interrotto perché `mblnCancel` è stato impostato su `True`. La percentuale di completamento viene aggiornata solo nel caso precedente.  
  
#### <a name="to-run-the-program"></a>Per eseguire il programma  
  
1. Premere F5 per inserire il progetto in modalità di esecuzione.  
  
2. Fare clic sul pulsante **Avvia attività** . Ogni volta che viene generato l'evento `PercentDone`, l'etichetta viene aggiornata con la percentuale dell'attività completata.  
  
3. Fare clic sul pulsante **Annulla** per arrestare l'attività. Si noti che l'aspetto del pulsante **Annulla** non viene modificato immediatamente quando si fa clic su di esso. L'evento `Click` non può verificarsi fino a quando l'istruzione `My.Application.DoEvents` non consente l'elaborazione di eventi.  
  
    > [!NOTE]
    > Il metodo `My.Application.DoEvents` non elabora gli eventi esattamente allo stesso modo del modulo. In questa procedura dettagliata, ad esempio, è necessario fare clic due volte sul pulsante **Annulla** . Per consentire al modulo di gestire direttamente gli eventi, è possibile utilizzare il multithreading. Per altre informazioni, vedere [Threading gestito](../../../../standard/threading/index.md).
  
 Potrebbe risultare istruttivo eseguire il programma con F11 e scorrere il codice una riga alla volta. È possibile vedere chiaramente il modo in cui l'esecuzione entra `LongTask`e quindi immettere brevemente `Form1` ogni volta che viene generato il `PercentDone` evento.  
  
 Cosa accadrebbe se, durante l'esecuzione fosse tornato nel codice di `Form1`, il metodo `LongTask` veniva chiamato di nuovo? Nel peggiore dei casi, è possibile che si verifichi un overflow dello stack se `LongTask` stato chiamato ogni volta che è stato generato l'evento.  
  
 È possibile fare in modo che la variabile `mWidget` gestisca gli eventi per un oggetto `Widget` diverso assegnando un riferimento al nuovo `Widget` a `mWidget`. Infatti, è possibile fare in modo che il codice sia in `Button1_Click` eseguire questa operazione ogni volta che si fa clic sul pulsante.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Per gestire gli eventi per un widget diverso  
  
- Aggiungere la seguente riga di codice alla procedura `Button1_Click`, immediatamente prima della riga che legge `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Form1.vb#9)]  
  
 Il codice precedente crea un nuovo `Widget` ogni volta che si fa clic sul pulsante. Non appena il metodo `LongTask` viene completato, viene rilasciato il riferimento al `Widget` e il `Widget` viene eliminato definitivamente.  
  
 Una variabile di `WithEvents` può contenere un solo riferimento a un oggetto alla volta, pertanto se si assegna un oggetto `Widget` diverso per `mWidget`, gli eventi dell'oggetto `Widget` precedente non verranno più gestiti. Se `mWidget` è l'unica variabile oggetto contenente un riferimento al `Widget`precedente, l'oggetto viene eliminato definitivamente. Se si desidera gestire gli eventi di diversi oggetti `Widget`, utilizzare l'istruzione `AddHandler` per elaborare separatamente gli eventi da ogni oggetto.  
  
> [!NOTE]
> È possibile dichiarare il numero di variabili `WithEvents` necessarie, ma le matrici di variabili `WithEvents` non sono supportate.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
