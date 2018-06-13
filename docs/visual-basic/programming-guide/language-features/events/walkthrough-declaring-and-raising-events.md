---
title: Dichiarazione e generazione di eventi (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], events
- events [Visual Basic], walkthroughs
- declaring events [Visual Basic], walkthroughs
- events [Visual Basic], declaring
- events [Visual Basic], raising
- raising events [Visual Basic], walkthroughs
ms.assetid: 8ffb3be8-097d-4d3c-b71e-04555ebda2a2
ms.openlocfilehash: 67bbf7bc95a0fe1ee8e9c2a6cf07d850d30bb028
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652809"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Procedura dettagliata: dichiarazione e generazione di eventi (Visual Basic)
Questa procedura dettagliata viene illustrato come dichiarare e generare eventi per una classe denominata `Widget`. Dopo aver completato i passaggi, è possibile leggere l'argomento correlato, [procedura dettagliata: gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), cui viene illustrato come utilizzare gli eventi da `Widget` oggetti da fornire informazioni sullo stato in un'applicazione.  
  
## <a name="the-widget-class"></a>La classe Widget  
 Si supponga che è necessario un `Widget` classe. La `Widget` classe dispone di un metodo che può richiedere un tempo di esecuzione e si desidera che l'applicazione in grado di venga visualizzato un indicatore di completamento.  
  
 Naturalmente, è possibile apportare la `Widget` oggetto visualizzare una finestra di dialogo la percentuale di completamento, ma quindi verrebbe con tale finestra di dialogo in ogni progetto in cui viene utilizzata la `Widget` classe. Corso della progettazione di oggetti è consigliabile per consentire l'applicazione che usa un handle di oggetto dell'interfaccia utente, a meno che non lo scopo dell'oggetto non sia per la gestione di un form o finestra di dialogo.  
  
 Lo scopo di `Widget` consiste nell'eseguire altre attività, pertanto è consigliabile aggiungere un `PercentDone` evento e consentono di procedure che chiama `Widget`del metodi gestiscono che gli aggiornamenti di stato di evento e la visualizzazione. Il `PercentDone` evento può inoltre fornire un meccanismo per l'annullamento dell'attività.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Per compilare l'esempio di codice per questo argomento  
  
1.  Aprire un nuovo progetto applicazione Windows Visual Basic e creare un form denominato `Form1`.  
  
2.  Aggiungere due pulsanti e un'etichetta a `Form1`.  
  
3.  Assegnare i nomi agli oggetti come illustrato nella tabella seguente.  
  
    |Oggetto|Proprietà|Impostazione|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Attività di avvio|  
    |`Button2`|`Text`|Annulla|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  Nel **progetto** menu, scegliere **Aggiungi classe** per aggiungere una classe denominata `Widget.vb` al progetto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Per dichiarare un evento per la classe Widget  
  
-   Utilizzare il `Event` (parola chiave) per dichiarare un evento nel `Widget` classe. Si noti che un evento può avere `ByVal` e `ByRef` argomenti, come `Widget`del `PercentDone` dimostrato dall'evento:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_1.vb)]  
  
 Quando l'oggetto chiamante riceve un `PercentDone` evento, il `Percent` argomento indica la percentuale di completamento dell'attività. Il `Cancel` argomento può essere impostato su `True` per annullare il metodo che ha generato l'evento.  
  
> [!NOTE]
>  È possibile dichiarare argomenti dell'evento, come avviene gli argomenti di routine, con le eccezioni seguenti: non possono contenere eventi `Optional` o `ParamArray` argomenti e gli eventi non hanno valori restituiti.  
  
 Il `PercentDone` evento viene generato dal `LongTask` metodo la `Widget` classe. `LongTask` accetta due argomenti: il periodo di tempo il metodo finge di eseguire le operazioni e l'intervallo di tempo minimo prima che `LongTask` pause per generare il `PercentDone` evento.  
  
#### <a name="to-raise-the-percentdone-event"></a>Per generare l'evento PercentDone  
  
1.  Per semplificare l'accesso per il `Timer` proprietà utilizzate da questa classe, aggiungere un `Imports` istruzione all'inizio della sezione delle dichiarazioni di modulo di classe, sopra il `Class Widget` istruzione.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_2.vb)]  
  
2.  Aggiungere il codice seguente alla classe `Widget` :  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](../../../../visual-basic/programming-guide/language-features/events/codesnippet/VisualBasic/walkthrough-declaring-and-raising-events_3.vb)]  
  
 Quando l'applicazione chiama il `LongTask` (metodo), il `Widget` classe genera il `PercentDone` evento ogni `MinimumInterval` secondi. Quando l'evento restituito, `LongTask` controlla se il `Cancel` argomento è stato impostato su `True`.  
  
 In questa sezione sono necessarie alcune osservazioni. Per semplicità, il `LongTask` procedura si presuppone che si conosce in anticipo quanto tempo l'attività. Ciò avviene quasi mai. Suddivisione in blocchi di dimensioni pari delle attività può essere difficile e spesso gli utenti desiderano soprattutto è semplicemente la quantità di tempo trascorso prima di ottenere un'indicazione che si è in corso.  
  
 In questo esempio si potrebbe individua un difetto di un altro. Il `Timer` proprietà restituisce il numero di secondi trascorsi dalla mezzanotte; pertanto, l'applicazione si blocca se è stato avviato prima di mezzanotte. Un approccio più precisa per misurare il tempo necessario tenere in considerazione o evitarli del tutto, utilizzando le proprietà, ad esempio `Now`.  
  
 Ora che la `Widget` classe può generare eventi, è possibile spostare la successiva procedura dettagliata. [Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) illustra come usare `WithEvents` per associare un gestore eventi con il `PercentDone` evento.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>  
 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>  
 [Procedura dettagliata: Gestione di eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)  
 [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
