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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 110036e5031a2956375b1edf0689237661522d39
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2019
ms.locfileid: "72180201"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedura: Testare il comportamento in fase di esecuzione di un UserControl

Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testarne il comportamento in fase di esecuzione. È possibile creare un progetto di applicazione basato su Windows separato e inserire il controllo in un form di test, ma questa procedura non è praticabile. Un modo più rapido e semplice consiste nell'usare il **contenitore di test UserControl** fornito da Visual Studio. Questo contenitore di test viene avviato direttamente dal progetto libreria di controlli Windows.

> [!IMPORTANT]
> Affinché il contenitore di test carichi il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.

> [!NOTE]
> Non è C++ possibile testare un controllo visivo utilizzando il **contenitore di test UserControl**.

## <a name="test-the-run-time-behavior-of-a-usercontrol"></a>Testare il comportamento in fase di esecuzione di un UserControl

1. In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **EsempioTestContainer**.

2. Nella **Progettazione Windows Form**trascinare un controllo <xref:System.Windows.Forms.Label> dalla **casella degli strumenti** nell'area di progettazione del controllo.

3. Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il **contenitore di test UserControl**. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel riquadro di **Anteprima** .

4. Selezionare la proprietà <xref:System.Windows.Forms.Control.BackColor%2A> visualizzata nel controllo <xref:System.Windows.Forms.PropertyGrid> a destra del riquadro di **Anteprima** . Modificare il valore in **ControlDark**. Osservare che il controllo viene modificato in un colore più scuro. Provare a modificare altri valori di proprietà e osservare l'effetto sul controllo.

5. Fare clic sulla casella di **controllo Dock Fill User Control** sotto il riquadro di **Anteprima** . Si noti che il controllo viene ridimensionato per riempire il riquadro. Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.

6. Chiudere il contenitore di test.

7. Aggiungere un altro controllo utente al progetto **EsempioTestContainer** .

8. Nella **Progettazione Windows Form**trascinare un controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** nell'area di progettazione del controllo.

9. Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il contenitore di test.

10. Fare clic su **selezionare il controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente.

## <a name="test-user-controls-from-another-project"></a>Testare i controlli utente da un altro progetto

È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.

1. In Visual Studio creare un progetto libreria di controlli Windows e denominarlo **EsempioTestContainer2**.

2. Nella **Progettazione Windows Form**trascinare un controllo <xref:System.Windows.Forms.RadioButton> dalla **casella degli strumenti** nell'area di progettazione del controllo.

3. Premere <kbd>F5</kbd> per compilare il progetto ed eseguire il contenitore di test. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel riquadro di **Anteprima** .

4. Fare clic sul pulsante **carica** .

5. Nella finestra di dialogo **Apri** passare a *EsempioTestContainer. dll*compilato nella procedura precedente. Selezionare *EsempioTestContainer. dll* e fare clic sul pulsante **Apri** per caricare i controlli utente.

6. Usare il **controllo utente Select** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal progetto **EsempioTestContainer** .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.UserControl>
- [Procedura: Crea controlli compositi @ no__t-0
- [Procedura dettagliata: Creazione di un controllo composito @ no__t-0
- [Progettazione controllo utente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/183c3hth(v=vs.100))
