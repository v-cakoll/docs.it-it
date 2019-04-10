---
title: 'Procedura: Connettere più eventi a un unico gestore eventi in Windows Forms'
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
ms.openlocfilehash: eec6a754b885cd169e5542221caefb3233c4c8af
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300723"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Procedura: Connettere più eventi a un unico gestore eventi in Windows Forms
Nella progettazione delle applicazioni, si potrebbe essere necessario utilizzare un unico gestore eventi per più eventi o avere più eventi di eseguire la stessa procedura. Ad esempio, è spesso un notevole risparmio di tempo per avere un comando di menu generano lo stesso evento come un pulsante sul form se espongono la stessa funzionalità. Questo scopo, è possibile utilizzare la visualizzazione di eventi della finestra proprietà in C# o tramite il `Handles` parola chiave e il **nome della classe** e **nome metodo** caselle di riepilogo a discesa nell'Editor di codice Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Per connettere più eventi a un unico gestore eventi in Visual Basic  
  
1. Fare clic sulla forma e scegliere **Visualizza codice**.  
  
2. Dal **nome della classe** casella di riepilogo a discesa, selezionare uno dei controlli che si desidera gestire con il gestore dell'evento.  
  
3. Dal **nome del metodo** casella a discesa, selezionare uno degli eventi che si desidera che il gestore di evento da gestire.  
  
4. L'Editor di codice inserito il gestore eventi appropriato e posiziona il punto di inserimento all'interno del metodo. Nell'esempio seguente, è il <xref:System.Windows.Forms.Control.Click> evento per il <xref:System.Windows.Forms.Button> controllo.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. Aggiungere gli altri eventi si vuole gestiti per il `Handles` clausola.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. Aggiungere il codice appropriato per il gestore dell'evento.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Per connettere più eventi a un unico gestore eventi in C\#
  
1. Selezionare il controllo a cui si desidera collegare un gestore eventi.  
  
2. Nella finestra Proprietà scegliere il **eventi** pulsante (![pulsante eventi](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3. Fare clic sul nome dell'evento che si desidera gestire.  
  
4. Nella sezione valore accanto al nome dell'evento, fare clic sul pulsante giù per visualizzare un elenco di gestori degli eventi esistenti che corrispondono alla firma del metodo dell'evento che si desidera gestire.  
  
5. Selezionare il gestore eventi appropriato dall'elenco.  
  
     Verrà aggiunto codice al form per associare l'evento al gestore dell'evento esistente.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)
- [Panoramica sui gestori eventi](event-handlers-overview-windows-forms.md)
