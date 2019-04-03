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
ms.openlocfilehash: 0f48c90232c00f53007e7d2f8f08e2107406ecad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841004"
---
# <a name="walkthrough-declaring-and-raising-events-visual-basic"></a>Procedura dettagliata: Dichiarazione e generazione di eventi (Visual Basic)
Questa procedura dettagliata illustra come dichiarare e generare eventi per una classe denominata `Widget`. Dopo aver completato i passaggi, è possibile leggere l'argomento complementare [procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md), che mostra come usare gli eventi da `Widget` oggetti da fornire informazioni sullo stato in un'applicazione.  
  
## <a name="the-widget-class"></a>La classe di Widget  
 Si supponga che per il momento in cui è necessario un `Widget` classe. Il `Widget` classe dispone di un metodo che può richiedere molto tempo per l'esecuzione e si vuole che l'applicazione sia in grado di venga visualizzato un indicatore di completamento.  
  
 Naturalmente, è possibile apportare le `Widget` oggetto Mostra una finestra di dialogo percentuale di completamento, ma è quindi potrebbe bloccarsi con tale finestra di dialogo in tutti i progetti in cui è stato usato il `Widget` classe. Una buona regola della progettazione di oggetti consiste nel consentire all'applicazione che usa un handle di oggetto dell'interfaccia utente, a meno che l'obiettivo finale dell'oggetto sia per la gestione di un form o finestra di dialogo.  
  
 Lo scopo della `Widget` consiste nell'eseguire altre attività, è preferibile aggiungere un' `PercentDone` evento e lasciare che le procedure che chiama `Widget`di metodi gestiscono che gli aggiornamenti di stato di evento e la visualizzazione. Il `PercentDone` evento può fornire anche un meccanismo per l'annullamento dell'attività.  
  
#### <a name="to-build-the-code-example-for-this-topic"></a>Per compilare l'esempio di codice in questo argomento  
  
1.  Aprire un nuovo progetto applicazione Windows di Visual Basic e creare un form denominato `Form1`.  
  
2.  Aggiungere due pulsanti e un'etichetta a `Form1`.  
  
3.  Assegnare i nomi agli oggetti come illustrato nella tabella seguente.  
  
    |Oggetto|Proprietà|Impostazione|  
    |------------|--------------|-------------|  
    |`Button1`|`Text`|Attività di avvio|  
    |`Button2`|`Text`|Annulla|  
    |`Label`|`(Name)`, `Text`|lblPercentDone, 0|  
  
4.  Nel **Project** menu, scegliere **Aggiungi classe** per aggiungere una classe denominata `Widget.vb` al progetto.  
  
#### <a name="to-declare-an-event-for-the-widget-class"></a>Per dichiarare un evento per la classe di Widget  
  
-   Usare la `Event` parola chiave per dichiarare un evento nel `Widget` classe. Si noti che un evento può avere `ByVal` e `ByRef` gli argomenti, come `Widget`del `PercentDone` dimostrato dall'evento:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#1)]  
  
 Quando l'oggetto chiamante riceve un' `PercentDone` evento, il `Percent` argomento contiene la percentuale di completamento dell'attività. Il `Cancel` argomento può essere impostato su `True` per annullare il metodo che ha generato l'evento.  
  
> [!NOTE]
>  È possibile dichiarare argomenti dell'evento, come avviene gli argomenti di routine, con le eccezioni seguenti: Gli eventi non possono avere `Optional` o `ParamArray` argomenti e gli eventi non hanno valori restituiti.  
  
 Il `PercentDone` evento viene generato dal `LongTask` metodo il `Widget` classe. `LongTask` accetta due argomenti: il periodo di tempo il metodo finge di eseguire le operazioni e l'intervallo di tempo minimo prima che `LongTask` mette in pausa per generare il `PercentDone` evento.  
  
#### <a name="to-raise-the-percentdone-event"></a>Per generare l'evento PercentDone  
  
1.  Per semplificare l'accesso per il `Timer` proprietà utilizzata da questa classe, aggiungere un' `Imports` istruzione all'inizio della sezione delle dichiarazioni di modulo di classe, sopra il `Class Widget` istruzione.  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#2)]  
  
2.  Aggiungere il codice seguente alla classe `Widget`:  
  
     [!code-vb[VbVbcnWalkthroughDeclaringAndRaisingEvents#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnWalkthroughDeclaringAndRaisingEvents/VB/Widget.vb#3)]  
  
 Quando l'applicazione chiama il `LongTask` metodo, il `Widget` classe genera le `PercentDone` eventi ogni `MinimumInterval` secondi. Quando termina, l'evento `LongTask` verifica se il `Cancel` argomento è stato impostato su `True`.  
  
 In questo caso, sono necessarie alcune dichiarazioni di non responsabilità. Per semplicità, il `LongTask` procedura presuppone che si conosce in anticipo quanto tempo l'attività. Ciò avviene quasi mai. Suddivisione in blocchi di dimensioni pari delle attività può essere difficile e spesso ciò che più interessa gli utenti è semplicemente la quantità di tempo trascorso prima che diventino un valore che indica che qualcosa è in corso.  
  
 In questo esempio si potrebbe individua un difetto di un altro. Il `Timer` proprietà restituisce il numero di secondi trascorsi dalla mezzanotte; pertanto, l'applicazione si blocca se è stato avviato prima di mezzanotte. Un approccio più attenzione alla misurazione del tempo potrebbe tenere in considerazione o evitarli del tutto, utilizzando le proprietà, ad esempio `Now`.  
  
 Ora che il `Widget` classe può generare eventi, è possibile spostare la successiva procedura dettagliata. [Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md) illustra come usare `WithEvents` per associare un gestore eventi con il `PercentDone` evento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:Microsoft.VisualBasic.DateAndTime.Timer%2A>
- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>
- [Procedura dettagliata: Gestione degli eventi](../../../../visual-basic/programming-guide/language-features/events/walkthrough-handling-events.md)
- [Eventi](../../../../visual-basic/programming-guide/language-features/events/index.md)
