---
title: Gestione degli eventi (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- event handling [Visual Basic], walkthroughs
- walkthroughs [Visual Basic], event handling
- variables [Visual Basic], WithEvents
- events [Visual Basic], walkthroughs
- WithEvents keyword [Visual Basic], walkthroughs
- event handlers [Visual Basic], walkthroughs
ms.assetid: f145b3fc-5ae0-4509-a2aa-1ff6934706bd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1743e5f5d9dcdf83ab646407cd1fcdc77ff71cd
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-handling-events-visual-basic"></a>Procedura dettagliata: gestione di eventi (Visual Basic)
Questo è il secondo dei due argomenti che illustrano l'utilizzo degli eventi. Il primo argomento, [procedura dettagliata: dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md), viene illustrato come dichiarare e generare eventi. Questa sezione Usa il modulo e una classe da tale procedura dettagliata per mostrare come gestire gli eventi quando si verificano.  
  
 Il `Widget` esempio di classe vengono utilizzate istruzioni di gestione degli eventi tradizionali. Visual Basic fornisce altre tecniche per l'utilizzo di eventi. Come esercizio, è possibile modificare questo esempio per utilizzare il `AddHandler` e `Handles` istruzioni.  
  
### <a name="to-handle-the-percentdone-event-of-the-widget-class"></a>Per gestire l'evento PercentDone della classe Widget  
  
1.  Inserire il codice seguente in `Form1`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#4](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_1.vb)]  
  
     Il `WithEvents` (parola chiave) specifica che la variabile `mWidget` viene utilizzata per gestire gli eventi di un oggetto. Specificare il tipo di oggetto, indicando il nome della classe da cui verrà creato l'oggetto.  
  
     La variabile `mWidget` è dichiarato in `Form1` perché `WithEvents` le variabili possono essere a livello di classe. Questo vale indipendentemente dal tipo di classe in cui vengono inserite.  
  
     La variabile `mblnCancel` viene utilizzato per annullare il `LongTask` metodo.  
  
## <a name="writing-code-to-handle-an-event"></a>Scrittura di codice per gestire un evento  
 Non appena si dichiara una variabile utilizzando `WithEvents`, il nome della variabile viene visualizzato nell'elenco di riepilogo a discesa a sinistra della classe **Editor di codice**. Quando si seleziona `mWidget`, `Widget` gli eventi della classe vengono visualizzati nell'elenco a discesa a destra. Selezionando un evento consente di visualizzare la routine evento corrispondente, con il prefisso `mWidget` e un carattere di sottolineatura. Tutte le procedure di evento associate a un `WithEvents` variabile viene assegnato il nome della variabile come prefisso.  
  
#### <a name="to-handle-an-event"></a>Per gestire un evento  
  
1.  Selezionare `mWidget` dall'elenco di riepilogo a discesa a sinistra nel **Editor di codice**.  
  
2.  Selezionare il `PercentDone` evento dall'elenco a discesa a destra. Il **Editor di codice** apre il `mWidget_PercentDone` routine evento.  
  
    > [!NOTE]
    >  Il **Editor di codice** è utile, ma non obbligatorio, per l'inserimento di nuovi gestori di eventi. In questa procedura dettagliata, è più semplice copiare i gestori eventi direttamente nel codice.  
  
3.  Aggiungere il codice seguente al gestore eventi `mWidget_PercentDone`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#5](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_2.vb)]  
  
     Ogni volta che il `PercentDone` evento viene generato, la routine evento Visualizza la percentuale di completamento in un `Label` controllo. Il `DoEvents` metodo consente di ridisegnare l'etichetta e offre inoltre all'utente la possibilità di scegliere il **Annulla** pulsante.  
  
4.  Aggiungere il codice seguente per il `Button2_Click` gestore eventi:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#6](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_3.vb)]  
  
 Se l'utente fa clic il **Annulla** pulsante durante `LongTask` è in esecuzione, il `Button2_Click` evento viene eseguito non appena il `DoEvents` istruzione consente l'elaborazione degli eventi. La variabile a livello di classe `mblnCancel` è impostato su `True`e `mWidget_PercentDone` evento, quindi esegue il test e imposta il `ByRef Cancel` argomento `True`.  
  
## <a name="connecting-a-withevents-variable-to-an-object"></a>Una variabile WithEvents la connessione a un oggetto  
 `Form1` è ora configurato per gestire un `Widget` agli eventi dell'oggetto. È comunque per trovare un `Widget` in un punto.  
  
 Quando si dichiara una variabile `WithEvents` in fase di progettazione non è associato alcun oggetto. Oggetto `WithEvents` variabile è come qualsiasi altra variabile di oggetto. È necessario creare un oggetto e assegnare un riferimento a esso con il `WithEvents` variabile.  
  
#### <a name="to-create-an-object-and-assign-a-reference-to-it"></a>Per creare un oggetto e assegnare un riferimento a esso  
  
1.  Selezionare **(eventi Form1)** dall'elenco di riepilogo a discesa a sinistra nel **Editor di codice**.  
  
2.  Selezionare il `Load` evento dall'elenco a discesa a destra. Il **Editor di codice** apre il `Form1_Load` routine evento.  
  
3.  Aggiungere il codice seguente per il `Form1_Load` routine evento per creare il `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#7](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_4.vb)]  
  
 Quando viene eseguito questo codice, Visual Basic crea un `Widget` dell'oggetto e si connette relativi eventi alle routine evento associate `mWidget`. Da quel momento, ogni volta che il `Widget` genera relativo `PercentDone` evento, il `mWidget_PercentDone` evento procedure viene eseguita.  
  
#### <a name="to-call-the-longtask-method"></a>Chiamare il metodo LongTask  
  
-   Aggiungere il codice seguente al gestore eventi `Button1_Click`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#8](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_5.vb)]  
  
 Prima di `LongTask` metodo viene chiamato, l'etichetta che consente di visualizzare la percentuale di completamento deve essere inizializzati e il livello di classe `Boolean` flag di annullamento del metodo deve essere impostato su `False`.  
  
 `LongTask` viene chiamato con una durata dell'attività di 12,2 secondi. Il `PercentDone` evento viene generato una volta ogni un terzo di secondo. Ogni volta che viene generato l'evento, il `mWidget_PercentDone` evento procedure viene eseguita.  
  
 Quando `LongTask` viene eseguita, `mblnCancel` viene testato per verificare se `LongTask` è stato completato correttamente, o se è stato arrestato perché `mblnCancel` è stato impostato su `True`. La percentuale di completamento viene aggiornata solo nel primo caso.  
  
#### <a name="to-run-the-program"></a>Per eseguire il programma  
  
1.  Premere F5 per attivare il progetto in modalità di esecuzione.  
  
2.  Fare clic su di **Avvia attività** pulsante. Ogni volta che il `PercentDone` evento viene generato, l'etichetta viene aggiornata con la percentuale di completamento dell'attività.  
  
3.  Fare clic su di **Annulla** pulsante per arrestare l'attività. Si noti che l'aspetto del **Annulla** pulsante Modifica immediatamente quando viene selezionata. Il `Click` evento non può verificarsi fino a quando il `My.Application.DoEvents` istruzione consente l'elaborazione di eventi.  
  
    > [!NOTE]
    >  Il `My.Application.DoEvents` metodo elabora gli eventi esattamente nello stesso modo del form. Ad esempio, in questa procedura dettagliata, è necessario fare clic il **Annulla** due volte sul pulsante. Per consentire al modulo di gestione degli eventi direttamente, è possibile utilizzare il multithreading. Per ulteriori informazioni, vedere [Threading](http://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c).  
  
 Può risultare utile eseguire il programma con F11 e scorrere il codice una riga alla volta. È possibile visualizzare chiaramente come esecuzione entra `LongTask`e quindi brevemente rientra `Form1` ogni volta che il `PercentDone` viene generato l'evento.  
  
 Che cosa accadrebbe se, durante l'esecuzione nel codice di `Form1`, `LongTask` metodo viene chiamato? Nel peggiore dei casi, un overflow dello stack può verificarsi se `LongTask` chiamati ogni volta che è stato generato l'evento.  
  
 È possibile che la variabile `mWidget` per gestire gli eventi per un altro `Widget` oggetto tramite l'assegnazione di un riferimento al nuovo `Widget` a `mWidget`. In effetti, è possibile rendere il codice in `Button1_Click` eseguire questa operazione ogni volta che si sceglie il pulsante.  
  
#### <a name="to-handle-events-for-a-different-widget"></a>Per gestire gli eventi per un widget diverso  
  
-   Aggiungere la seguente riga di codice per il `Button1_Click` procedura, la riga che precede immediatamente `mWidget.LongTask(12.2, 0.33)`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#9](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-handling-events_6.vb)]  
  
 Il codice precedente crea un nuovo `Widget` ogni volta che si fa clic sul pulsante. Non appena il `LongTask` metodo viene completato, il riferimento al `Widget` viene rilasciato e `Widget` viene eliminato definitivamente.  
  
 A `WithEvents` variabile può contenere un solo riferimento oggetto alla volta, pertanto se si assegna un altro `Widget` oggetto `mWidget`, precedente `Widget` non verranno gestiti non è più eventi dell'oggetto. Se `mWidget` è l'unica variabile oggetto che contiene un riferimento a quella vecchia `Widget`, l'oggetto viene eliminato definitivamente. Se si desidera gestire gli eventi da diversi `Widget` oggetti, utilizzare il `AddHandler` istruzione per elaborare gli eventi da ogni oggetto separatamente.  
  
> [!NOTE]
>  È possibile dichiarare `WithEvents` necessario di variabili, ma le matrici di `WithEvents` variabili non sono supportate.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura dettagliata: Dichiarazione e generazione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-declaring-and-raising-events.md)  
 [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
