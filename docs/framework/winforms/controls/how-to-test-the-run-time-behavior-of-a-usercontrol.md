---
title: 'Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 48531ab1ef3b30b6516e3f2e7b5858a8884cbfe8
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211698"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedura: Testare il comportamento in fase di esecuzione di UserControl

Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testarne il comportamento in fase di esecuzione. È possibile creare un progetto di applicazione basata su Windows separato e posizionare il controllo in un modulo di test, ma questa procedura non è pratica. Un modo più veloce e più semplice consiste nell'usare la **UserControl Test Container** offerte da Visual Studio. Questo contenitore di test viene avviata direttamente dal progetto di libreria di controlli Windows.

> [!IMPORTANT]
> Per il contenitore di test caricare il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.

> [!NOTE]
> Non è possibile testare un controllo di Visual C++ utilizzando la **UserControl Test Container**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Testare il comportamento in fase di esecuzione di UserControl

1. In Visual Studio, creare un progetto di libreria di controlli di Windows denominato **EsempioTestContainer**. Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Label> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.

3. Premere **F5** per compilare il progetto ed eseguire il **UserControl Test Container**. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.

4. Selezionare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà visualizzata nel <xref:System.Windows.Forms.PropertyGrid> a destra del controllo il **anteprima** riquadro. Modificare il relativo valore su `ControlDark`. Osservare che modifica un colore più scuro del controllo. Provare a modificare altri valori di proprietà e osservare gli effetti sul controllo.

5. Fare clic sul **controllo utente Dock Fill** casella di controllo sotto il **anteprima** riquadro. Osservare che il controllo viene ridimensionato per riempire il riquadro. Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.

6. Chiudere il contenitore di test.

7. Aggiungere un altro controllo utente per il **EsempioTestContainer** progetto. Per informazioni dettagliate, vedere [Procedura: Aggiungere elementi esistenti a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100)).

8. Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.

9. Premere F5 per compilare il progetto ed eseguire il contenitore di test.

10. Scegliere il **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> passare tra i due controlli utente.

## <a name="test-user-controls-from-another-project"></a>Controlli utente di test da un altro progetto

È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.

1. Creare un progetto di libreria di controlli di Windows denominato **Esempiotestcontainer2**. Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).

2. Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.RadioButton> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.

3. Premere F5 per compilare il progetto ed eseguire il contenitore di test. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.

4. Scegliere il **carico** pulsante.

5. Nel **aperto** finestra di dialogo passare alla **EsempioTestContainer**. dll, che è stata compilata nella procedura precedente. Selezionare **EsempioTestContainer**DLL e fare clic sui **Open** pulsante per caricare i controlli utente

6. Usare la **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal **EsempioTestContainer** progetto.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- [Procedura: Modificare controlli compositi](how-to-author-composite-controls.md)
- [Procedura dettagliata: Modifica di un controllo composito con Visual Basic](walkthrough-authoring-a-composite-control-with-visual-basic.md)
- [Procedura dettagliata: Modifica di un controllo composito con VisualC#](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Progettazione controllo utente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
