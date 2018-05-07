---
title: 'Procedura: connettere più eventi a un unico gestore eventi in Windows Form'
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 527a76376a4c1d5ad051f4768ca2bd42c3548b3d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Procedura: connettere più eventi a un unico gestore eventi in Windows Form
Nella progettazione delle applicazioni, potrebbe essere necessario utilizzare un singolo gestore eventi per più eventi o di più eventi di eseguire la stessa procedura. Ad esempio, è spesso un notevole risparmio di tempo per generare l'evento stesso come un pulsante sul form non espongono la stessa funzionalità di un comando di menu. È possibile farlo usando la visualizzazione di eventi della finestra proprietà in c# o il `Handles` (parola chiave) e **nome classe** e **nome del metodo** caselle di riepilogo a discesa nell'Editor di codice Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Per connettere più eventi a un unico gestore eventi in Visual Basic  
  
1.  Il modulo di mouse e scegliere **Visualizza codice**.  
  
2.  Dal **nome classe** casella di riepilogo a discesa, selezionare uno dei controlli che si desidera gestire con il gestore dell'evento.  
  
3.  Dal **nome del metodo** casella a discesa, selezionare uno degli eventi che si desidera gestire il gestore eventi.  
  
4.  L'Editor di codice inserito il gestore eventi appropriato e posiziona il punto di inserimento all'interno del metodo. Nell'esempio seguente, è il <xref:System.Windows.Forms.Control.Click> evento per il <xref:System.Windows.Forms.Button> controllo.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Aggiungere gli altri eventi si desidera gestiti per il `Handles` clausola.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Aggiungere il codice appropriato per il gestore dell'evento.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Per connettere più eventi a un singolo gestore eventi in c#  
  
1.  Selezionare il controllo a cui si desidera connettersi a un gestore eventi.  
  
2.  Nella finestra Proprietà fare clic su di **eventi** pulsante (![pulsante eventi](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3.  Fare clic sul nome dell'evento che si desidera gestire.  
  
4.  Nella sezione valore accanto al nome di evento, fare clic sul pulsante di menu a discesa per visualizzare un elenco di gestori di eventi esistente che corrisponde alla firma del metodo dell'evento che si desidera gestire.  
  
5.  Selezionare il gestore eventi appropriato dall'elenco.  
  
     Verrà aggiunto codice al form per associare l'evento al gestore dell'evento esistente.  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di gestori eventi in Windows Form](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [Informazioni generali sui gestori eventi](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
