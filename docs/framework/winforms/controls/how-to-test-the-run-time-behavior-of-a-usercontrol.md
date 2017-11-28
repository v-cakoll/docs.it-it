---
title: 'Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UserControl class [Windows Forms], testing
- user controls [Windows Forms], testing
- composite controls [Windows Forms], testing
- UserControl Test Container
- UserControl class [Windows Forms], run-time behavior
ms.assetid: 4e4d5c49-1346-40ac-9d96-40211b573583
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2ce4f821a7b964b3ed2e03c795346b47bb88d618
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-test-the-run-time-behavior-of-a-usercontrol"></a>Procedura: eseguire il test del comportamento in fase di esecuzione di UserControl
Quando si sviluppa un <xref:System.Windows.Forms.UserControl>, è necessario testare il comportamento in fase di esecuzione. È possibile creare un progetto di applicazione separata basati su Windows e inserire il controllo in un form di test, ma questa procedura non è pratica. Un modo più veloce e più semplice consiste nell'usare il **UserControl Test Container** fornite da Visual Studio. Questo contenitore di test viene avviata direttamente dal progetto libreria di controllo di Windows.  
  
> [!IMPORTANT]
>  Per il contenitore di test caricare il <xref:System.Windows.Forms.UserControl>, il controllo deve avere almeno un costruttore pubblico.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
> [!NOTE]
>  Non è possibile testare un controllo di Visual C++ tramite la **UserControl Test Container**.  
  
### <a name="to-test-the-run-time-behavior-of-a-usercontrol"></a>Per testare il comportamento in fase di esecuzione di UserControl  
  
1.  Creare un progetto libreria di controlli Windows denominato **EsempioTestContainer**. Per informazioni dettagliate, vedere [modello libreria di controlli Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Nel **Progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Label> controllo il **della casella degli strumenti** nell'area di progettazione del controllo.  
  
3.  Premere F5 per compilare il progetto ed eseguire il **UserControl Test Container**. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel **anteprima** riquadro.  
  
4.  Selezionare il <xref:System.Windows.Forms.Control.BackColor%2A> proprietà visualizzata nella <xref:System.Windows.Forms.PropertyGrid> controllo a destra del **anteprima** riquadro. Modificare il valore su `ControlDark`. Osservare che il controllo di modifica di un colore più scuro. Provare a modificare altri valori di proprietà e osservare l'effetto sul controllo.  
  
5.  Fare clic su di **controllo utente Dock Fill** seguente casella di controllo di **anteprima** riquadro. Osservare che il controllo viene ridimensionato per riempire il riquadro. Ridimensionare il contenitore di test e osservare che il controllo viene ridimensionato con il riquadro.  
  
6.  Chiudere il contenitore di test.  
  
7.  Aggiungere un altro controllo utente per il **EsempioTestContainer** progetto. Per informazioni dettagliate, vedere [NIB: procedura: aggiungere elementi esistenti a un progetto](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).  
  
8.  Nel **Progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nell'area di progettazione del controllo.  
  
9. Premere F5 per compilare il progetto ed eseguire il test container.  
  
10. Fare clic su di **Seleziona controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente.  
  
## <a name="testing-user-controls-from-another-project"></a>Controlli utente da un altro progetto di test  
 È possibile testare i controlli utente da altri progetti nel contenitore di test del progetto corrente.  
  
#### <a name="to-test-user-controls-from-another-project"></a>Per testare i controlli utente da un altro progetto  
  
1.  Creare un progetto libreria di controlli Windows denominato **Esempiotestcontainer2**. Per informazioni dettagliate, vedere [modello libreria di controlli Windows](http://msdn.microsoft.com/en-us/722f4e2d-1310-4ed5-8f33-593337ab66b4).  
  
2.  Nel **Progettazione Windows Form**, trascinare un <xref:System.Windows.Forms.RadioButton> controllo il **della casella degli strumenti** nell'area di progettazione del controllo.  
  
3.  Premere F5 per compilare il progetto ed eseguire il test container. Il contenitore di test viene visualizzato con il <xref:System.Windows.Forms.UserControl> nel **anteprima** riquadro.  
  
4.  Fare clic su di **carico** pulsante.  
  
5.  Nel **aprire** finestra di dialogo passare a **EsempioTestContainer**. dll, che è incorporato nella procedura precedente. Selezionare **EsempioTestContainer**DLL e scegliere il **aprire** per caricare i controlli utente  
  
6.  Utilizzare il **Seleziona controllo utente** <xref:System.Windows.Forms.ComboBox> per passare tra i due controlli utente dal **EsempioTestContainer** progetto.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.UserControl>  
 [Procedura: Modificare controlli compositi](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 [Procedura dettagliata: modifica di un controllo composito con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [Procedura dettagliata: modifica di un controllo composito con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 [Finestra di progettazione controlli utente](http://msdn.microsoft.com/en-us/2abb9eec-ba32-45cb-b73d-8b52a8bd6bf1)
