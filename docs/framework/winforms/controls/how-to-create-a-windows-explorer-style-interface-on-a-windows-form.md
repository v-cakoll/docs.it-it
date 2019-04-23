---
title: "Procedura: Creare un'interfaccia di tipo Esplora risorse in un Windows Form"
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
ms.openlocfilehash: dd70feaba29e29748ac56729632fa359582a6914
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59327373"
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Procedura: Creare un'interfaccia di tipo Esplora risorse in un Windows Form
Windows Explorer è una soluzione di interfaccia utente comune per le applicazioni a causa di relativa familiarità pronto.  
  
 Windows Explorer è costituita essenzialmente da un <xref:System.Windows.Forms.TreeView> controllo e un <xref:System.Windows.Forms.ListView> controllo in due pannelli separati. I pannelli vengono effettuati ridimensionabili da una barra di divisione. Questa disposizione dei controlli in modo efficace per la visualizzazione e le informazioni cercate.  
  
 I passaggi seguenti mostrano come disporre i controlli in un Windows form simile a Esplora risorse. Non illustrano come aggiungere la funzionalità per l'esplorazione del file dell'applicazione Windows Explorer.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Per creare un modulo di Windows di tipo Esplora risorse di Windows  
  
1. Creare un nuovo progetto applicazione Windows (**File** > **New** > **progetto** > **Visual C#** oppure **Visual Basic** > **Desktop classico** > **Windows Forms Application**).  
  
2. Dal **casella degli strumenti**:  
  
    1.  Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo nel form.  
  
    2.  Trascinare un <xref:System.Windows.Forms.TreeView> controllo in **SplitterPanel1** (il pannello del <xref:System.Windows.Forms.SplitContainer> controllo contrassegnato **Panel1**).  
  
    3.  Trascinare un <xref:System.Windows.Forms.ListView> controllo in **pannello SplitterPanel2** (il pannello del <xref:System.Windows.Forms.SplitContainer> controllo contrassegnato **Panel2**).  
  
3. Selezionare tutti i tre controlli premendo il tasto CTRL e facendo clic su essi, a sua volta. Quando si seleziona il <xref:System.Windows.Forms.SplitContainer> controllo, fare clic sulla barra di divisione, anziché i pannelli.  
  
    > [!NOTE]
    >  Non usare la **Seleziona tutto** comando le **modificare** menu. Se in questo caso, la proprietà necessaria nel passaggio successivo non compariranno nella **proprietà** finestra.  
  
4. Nella finestra **Proprietà** impostare la proprietà <xref:System.Windows.Forms.SplitContainer.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5. Premere F5 per eseguire l'applicazione.  
  
     Viene visualizzata un'interfaccia utente di due parti, simile a quella della finestra di esplorazione di Windows.  
  
    > [!NOTE]
    >  Quando si trascina la barra di divisione, i pannelli vengono ridimensionati.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Procedura: Creare un'interfaccia utente a più riquadri con Windows Form](how-to-create-a-multipane-user-interface-with-windows-forms.md)
- [Procedura: Definire il ridimensionamento e posizionamento in una finestra divisa](how-to-define-resize-and-positioning-behavior-in-a-split-window.md)
- [Procedura: Suddividere una finestra orizzontalmente](how-to-split-a-window-horizontally.md)
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
