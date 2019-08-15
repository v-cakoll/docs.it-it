---
title: "Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms usando la finestra di progettazione"
ms.date: 03/30/2017
helpviewer_keywords:
- user interface [Windows Forms], multipane
- SplitContainer control [Windows Forms], using the designer
- multipane user interface
ms.assetid: c3f9294d-a26c-4198-9242-f237f55f7573
ms.openlocfilehash: f96124f7d97e733b1f0e2559320ce2e09ba5ff21
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039952"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms-using-the-designer"></a>Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms usando la finestra di progettazione
Nella procedura seguente verrà creata un'interfaccia utente a più riquadri simile a quella usata in Microsoft Outlook, con un elenco di **cartelle** , un riquadro **messaggi** e un riquadro di **Anteprima** . Questa disposizione viene eseguita principalmente tramite l'ancoraggio dei controlli con il modulo.

 Quando si ancora un controllo, si determina il bordo del contenitore padre a cui un controllo viene collegato. Se quindi si imposta la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà su <xref:System.Windows.Forms.DockStyle.Right>, il bordo destro del controllo verrà ancorato al bordo destro del controllo padre. Inoltre, il bordo ancorato del controllo viene ridimensionato in modo che corrisponda a quello del relativo controllo contenitore. Per ulteriori informazioni sul funzionamento della <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà, vedere [procedura: Ancorare i controlli](how-to-dock-controls-on-windows-forms.md)in Windows Forms.

 Questa procedura è incentrata sulla disposizione <xref:System.Windows.Forms.SplitContainer> di e degli altri controlli nel form, non sull'aggiunta di funzionalità per fare in modo che l'applicazione riproduca Microsoft Outlook.

 Per creare questa interfaccia utente, posizionare tutti i controlli all'interno di <xref:System.Windows.Forms.SplitContainer> un controllo, che contiene <xref:System.Windows.Forms.TreeView> un controllo nel pannello a sinistra. Il pannello destro <xref:System.Windows.Forms.SplitContainer> del controllo contiene un secondo <xref:System.Windows.Forms.SplitContainer> controllo con un <xref:System.Windows.Forms.ListView> controllo sopra un <xref:System.Windows.Forms.RichTextBox> controllo. Questi <xref:System.Windows.Forms.SplitContainer> controlli consentono il ridimensionamento indipendente degli altri controlli nel form. È possibile adattare le tecniche di questa procedura per creare interfacce utente personalizzate.

## <a name="to-create-an-outlook-style-user-interface-at-design-time"></a>Per creare un'interfaccia utente di tipo Outlook in fase di progettazione

1. Creare un nuovo progetto di applicazione Windows (**file** > **nuovo** > **progetto** >  **C# Visual** o **Visual Basic** > **desktop classico**  >  **Applicazione Windows Forms**).

2. Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo dalla **casella degli strumenti** nel form. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.

3. Trascinare un <xref:System.Windows.Forms.TreeView> controllo dalla **casella degli strumenti** al pannello a sinistra del <xref:System.Windows.Forms.SplitContainer> controllo. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà su <xref:System.Windows.Forms.DockStyle.Left> facendo clic sul pannello a sinistra nell'editor dei valori visualizzato quando si fa clic sulla freccia in giù.

4. Trascinare un <xref:System.Windows.Forms.SplitContainer> altro controllo dalla **casella degli strumenti**e posizionarlo nel pannello destro del <xref:System.Windows.Forms.SplitContainer> controllo aggiunto al form. Nella finestra **Proprietà** impostare la <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà su <xref:System.Windows.Forms.DockStyle.Fill> e la <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà su <xref:System.Windows.Forms.Orientation.Horizontal>.

5. Trascinare un <xref:System.Windows.Forms.ListView> controllo dalla **casella degli strumenti** al pannello superiore del secondo <xref:System.Windows.Forms.SplitContainer> controllo aggiunto al form. Impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> del controllo <xref:System.Windows.Forms.ListView> su <xref:System.Windows.Forms.DockStyle.Fill>.

6. Trascinare un <xref:System.Windows.Forms.RichTextBox> controllo dalla **casella degli strumenti** al pannello inferiore del secondo <xref:System.Windows.Forms.SplitContainer> controllo. Impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> del controllo <xref:System.Windows.Forms.RichTextBox> su <xref:System.Windows.Forms.DockStyle.Fill>.

     A questo punto, se si preme F5 per eseguire l'applicazione, nel modulo verrà visualizzata un'interfaccia utente in tre parti, simile a quella di Microsoft Outlook.

    > [!NOTE]
    >  Quando si posiziona il puntatore del mouse su uno dei separatori all'interno <xref:System.Windows.Forms.SplitContainer> dei controlli, è possibile ridimensionare le dimensioni interne.

A questo punto, nello sviluppo di applicazioni, è stata creata un'interfaccia utente sofisticata. Il passaggio successivo consiste nel procedere con la programmazione dell'applicazione stessa, forse connettendo il controllo <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ListView> i controlli a un tipo di origine dati. Per ulteriori informazioni sulla connessione di controlli ai dati, vedere [Data Binding e Windows Forms](../data-binding-and-windows-forms.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
