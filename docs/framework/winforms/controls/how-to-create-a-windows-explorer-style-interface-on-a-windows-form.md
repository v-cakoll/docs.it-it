---
title: "Procedura: Creare un'interfaccia di tipo Esplora risorse in un Windows Form"
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: 34a5cd735c350688d9e83003806668e213932c85
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960619"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Procedura: Creare un'interfaccia di tipo Esplora risorse in un Windows Form
Esplora risorse è una scelta di interfaccia utente comune per le applicazioni grazie alla sua dimestichezza.

 Esplora risorse è essenzialmente un <xref:System.Windows.Forms.TreeView> controllo e un <xref:System.Windows.Forms.ListView> controllo su pannelli distinti. I pannelli vengono resi ridimensionabili da una barra di divisione. Questa disposizione dei controlli è molto efficace per la visualizzazione e l'esplorazione delle informazioni.

 Nei passaggi seguenti viene illustrato come disporre i controlli in un form di tipo Esplora risorse. Non illustrano come aggiungere la funzionalità di esplorazione dei file dell'applicazione Esplora risorse.

## <a name="to-create-a-windows-explorer-style-windows-form"></a>Per creare un Windows Form di tipo Esplora risorse

1. Creare un nuovo progetto di applicazione Windows (**file** > **nuovo** > **progetto** >  **C# Visual** o **Visual Basic** > **desktop classico**  >  **Applicazione Windows Forms**).

2. Dalla **casella degli strumenti**:

    1. Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo nel form.

    2. Trascinare un <xref:System.Windows.Forms.TreeView> controllo in **splitterPanel1** ( <xref:System.Windows.Forms.SplitContainer> il pannello del controllo contrassegnato come **Panel1**).

    3. Trascinare un <xref:System.Windows.Forms.ListView> controllo in **splitterPanel2** ( <xref:System.Windows.Forms.SplitContainer> il pannello del controllo contrassegnato come **Panel2**).

3. Selezionare tutti e tre i controlli premendo il tasto CTRL e facendo clic su di essi a sua volta. Quando si seleziona il <xref:System.Windows.Forms.SplitContainer> controllo, fare clic sulla barra di divisione anziché sui pannelli.

    > [!NOTE]
    > Non utilizzare il comando **Seleziona tutto** nel menu **modifica** . In tal caso, la proprietà necessaria nel passaggio successivo non verrà visualizzata nella finestra **Proprietà** .

4. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.

5. Premere F5 per eseguire l'applicazione.

     Il modulo Visualizza un'interfaccia utente in due parti, simile a quella di Esplora risorse.

    > [!NOTE]
    > Quando si trascina la barra di divisione, i pannelli si ridimensionano.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Procedura: Creare un'interfaccia utente a più riquadri con Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [Procedura: Definire il comportamento di ridimensionamento e posizionamento in una finestra divisa](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [Procedura: Suddividere una finestra orizzontalmente](how-to-split-a-window-horizontally.md)
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
