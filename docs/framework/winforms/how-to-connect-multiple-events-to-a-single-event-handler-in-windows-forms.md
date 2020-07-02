---
title: 'Procedura: connettere più eventi a un singolo gestore eventi'
description: Informazioni su come connettere più eventi a un singolo gestore eventi in Windows Forms usando la visualizzazione eventi della Finestra Proprietà in C#.
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
ms.openlocfilehash: cca85c223b46d9a82dbc3e34e3377fb83c075959
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621886"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Procedura: Connettere più eventi a un unico gestore eventi in Windows Forms
Nella progettazione dell'applicazione, potrebbe essere necessario usare un singolo gestore eventi per più eventi o fare in modo che più eventi eseguano la stessa procedura. Ad esempio, si tratta spesso di un potente risparmio di tempo per fare in modo che un comando di menu generi lo stesso evento di un pulsante nel form, se espone la stessa funzionalità. A tale scopo, è possibile usare la visualizzazione eventi del Finestra Proprietà in C# o la `Handles` parola chiave e le caselle a discesa **nome classe** e nome **Metodo** nell'editor del codice Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Per connettere più eventi a un singolo gestore eventi in Visual Basic  
  
1. Fare clic con il pulsante destro del mouse sul form e scegliere **Visualizza codice**.  
  
2. Nella casella di riepilogo a discesa **nome classe** selezionare uno dei controlli per i quali si desidera disporre dell'handle del gestore eventi.  
  
3. Nella casella di riepilogo a discesa **nome metodo** selezionare uno degli eventi che si desidera vengano gestiti dal gestore eventi.  
  
4. L'editor di codice inserisce il gestore eventi appropriato e posiziona il punto di inserimento all'interno del metodo. Nell'esempio seguente è l' <xref:System.Windows.Forms.Control.Click> evento per il <xref:System.Windows.Forms.Button> controllo.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. Aggiungere gli altri eventi che si desidera gestire alla `Handles` clausola.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. Aggiungere il codice appropriato al gestore dell'evento.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Per connettere più eventi a un singolo gestore eventi in C\#
  
1. Selezionare il controllo a cui si desidera connettere un gestore eventi.  
  
2. Nella Finestra Proprietà fare clic sul pulsante **eventi** (![pulsante eventi](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3. Fare clic sul nome dell'evento che si desidera gestire.  
  
4. Nella sezione valore accanto al nome dell'evento, fare clic sul pulsante a discesa per visualizzare un elenco di gestori eventi esistenti che corrispondono alla firma del metodo dell'evento che si desidera gestire.  
  
5. Selezionare il gestore eventi appropriato nell'elenco.  
  
     Il codice verrà aggiunto al form per associare l'evento al gestore eventi esistente.  
  
## <a name="see-also"></a>Vedere anche

- [Creazione di gestori eventi in Windows Form](creating-event-handlers-in-windows-forms.md)
- [Panoramica sui gestori eventi](event-handlers-overview-windows-forms.md)
