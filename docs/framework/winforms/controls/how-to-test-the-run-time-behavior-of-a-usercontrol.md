---
title: 'Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
ms.openlocfilehash: 40ec136a86b52dcb007d15d5a2917212745961f2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512209"
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl
Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testarne il comportamento in fase di esecuzione. È possibile creare un progetto di applicazione basata su Windows separato e posizionare il controllo in un modulo di test, ma questa procedura non è pratica. Un modo più veloce e più semplice consiste nell'usare la **UserControl Test Container** offerte da Visual Studio. Questo contenitore di test viene avviata direttamente dal progetto di libreria di controlli Windows.  
  
> [!IMPORTANT]
>  Per il contenitore di test caricare il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
> [!NOTE]
>  Non è possibile testare un controllo di Visual C++ utilizzando la **UserControl Test Container**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Per testare il comportamento in fase di esecuzione di UserControl  
  
1.  Creare un progetto di libreria di controlli di Windows denominato **EsempioTestContainer**. Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Label> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.  
  
3.  Premere F5 per compilare il progetto ed eseguire la **UserControl Test Container**. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.  
  
4.  Selezionare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà visualizzata nel <xref:System.Windows.Forms.PropertyGrid> a destra del controllo il **anteprima** riquadro. Modificare il relativo valore su `ControlDark`. Osservare che modifica un colore più scuro del controllo. Provare a modificare altri valori di proprietà e osservare gli effetti sul controllo.  
  
5.  Fare clic sul **controllo utente Dock Fill** casella di controllo sotto il **anteprima** riquadro. Osservare che il controllo viene ridimensionato per riempire il riquadro. Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.  
  
6.  Chiudere il contenitore di test.  
  
7.  Aggiungere un altro controllo utente per il **EsempioTestContainer** progetto. Per informazioni dettagliate, vedere [NIB: procedura: aggiungere elementi esistenti a un progetto](https://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.  
  
9. Premere F5 per compilare il progetto ed eseguire il contenitore di test.  
  
10. Scegliere il **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> passare tra i due controlli utente.  
  
## <a name="testing-user-controls-from-another-project"></a>Controlli utente da un altro progetto di test  
 È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Per testare i controlli utente da un altro progetto  
  
1.  Creare un progetto di libreria di controlli di Windows denominato **Esempiotestcontainer2**. Per informazioni dettagliate, vedere [modello di libreria di controllo di Windows](https://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Nel **finestra di progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.RadioButton> controllare dal **casella degli strumenti** nell'area di progettazione del controllo.  
  
3.  Premere F5 per compilare il progetto ed eseguire il contenitore di test. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nella **anteprima** riquadro.  
  
4.  Scegliere il **carico** pulsante.  
  
5.  Nel **aperto** finestra di dialogo passare alla **EsempioTestContainer**. dll, che è stata compilata nella procedura precedente. Selezionare **EsempioTestContainer**DLL e fare clic sui **Open** pulsante per caricare i controlli utente  
  
6.  Usare la **selezionare controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal **EsempioTestContainer** progetto.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.UserControl>  
 [Procedura: Modificare controlli compositi](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [Procedura dettagliata: modifica di un controllo composito con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Procedura dettagliata: modifica di un controllo composito con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Progettazione controllo utente](https://msdn.microsoft.com/library/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
