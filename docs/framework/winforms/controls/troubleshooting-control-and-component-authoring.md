---
title: Risoluzione dei problemi relativi alla modifica di controlli e componenti
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- troubleshooting components
- troubleshooting controls [Windows Forms]
- controls [Windows Forms], troubleshooting
- components [Windows Forms], troubleshooting
- Windows Forms controls, debugging
ms.assetid: e9c8c099-2271-4737-882f-50f336c7a55e
ms.openlocfilehash: 3ae8a889bf69913d234e31804335ddb08560c30c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343415"
---
# <a name="troubleshooting-control-and-component-authoring"></a>Risoluzione dei problemi relativi alla modifica di controlli e componenti
In questo argomento vengono descritti alcuni problemi comuni che si verificano durante lo sviluppo di componenti e controlli. Per altre informazioni, vedere l'argomento relativo alla [programmazione con i componenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).  
  
-   Impossibile aggiungere un controllo alla casella degli strumenti  
  
-   Impossibile eseguire il debug del componente o controllo utente di Windows Forms  
  
-   L'evento viene generato due volte nel componente o controllo ereditato  
  
-   Errore in fase di progettazione: "Impossibile creare il componente '*nome del componente*'"  
  
-   STAThreadAttribute  
  
-   L'icona del componente non appare nella casella degli strumenti  
  
## <a name="cannot-add-control-to-toolbox"></a>Impossibile aggiungere un controllo alla casella degli strumenti  
 Se si vuole aggiungere un controllo personalizzato creato in un altro progetto o un controllo di terze parti alla **casella degli strumenti**, è necessario farlo manualmente. Se il progetto corrente include il controllo o il componente, deve automaticamente apparire nella **casella degli strumenti**. Per altre informazioni, vedere [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).  
  
#### <a name="to-add-a-control-to-the-toolbox"></a>Per aggiungere un controllo alla casella degli strumenti  
  
1. Fare clic con il pulsante destro del mouse nella **casella degli strumenti** e selezionare **Scegli elementi** dal menu di scelta rapida.  
  
2. Nella finestra di dialogo **Scegli elementi della Casella degli strumenti** aggiungere il componente:  
  
    -   per aggiungere un componente o un controllo di .NET Framework, fare clic sulla scheda **Componenti di .NET Framework**  
  
         - oppure -  
  
    -   per aggiungere un componente COM o un controllo ActiveX, fare clic sulla scheda **Componenti COM**.  
  
3. Se il controllo è indicato nella finestra di dialogo, verificare se è selezionato e quindi fare clic su **OK**.  
  
     Il controllo viene aggiunto alla **della casella degli strumenti**.  
  
4. Se il controllo non è indicato nella finestra di dialogo, eseguire queste operazioni:  
  
    1.  Fare clic sul pulsante **Sfoglia**.  
  
    2.  Passare alla cartella che contiene il file DLL in cui si trova il controllo.  
  
    3.  Selezionare il file DLL e fare clic su **Apri**.  
  
         Il controllo viene visualizzato nella finestra di dialogo.  
  
    4.  Verificare se il controllo è selezionato e quindi fare clic su **OK**.  
  
         Il controllo viene aggiunto alla **casella degli strumenti**.  
  
## <a name="cannot-debug-the-windows-forms-user-control-or-component"></a>Impossibile eseguire il debug del componente o controllo utente di Windows Form  
 Se il controllo deriva dal <xref:System.Windows.Forms.UserControl> (classe), è possibile eseguire il debug, il comportamento in fase di esecuzione con il contenitore di test. Per altre informazioni, vedere [Procedura: Testare il comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).  
  
 Altri componenti e controlli personalizzati non sono progetti autonomi. Devono essere ospitati da un'applicazione, ad esempio un progetto Windows Form. Per eseguire il debug di un controllo o un componente, è necessario aggiungerlo a un progetto Windows Form.  
  
#### <a name="to-debug-a-control-or-component"></a>Per eseguire il debug di un controllo o componente  
  
1. Scegliere **Compila soluzione** dal menu **Compila** per creare il progetto.  
  
2. Scegliere **Aggiungi** dal menu **File**, quindi selezionare **Nuovo progetto** per aggiungere un progetto di test all'applicazione.  
  
3. Nella finestra di dialogo **Aggiungi nuovo progetto** scegliere **Applicazione Windows** come tipo di progetto.  
  
4. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul nodo **Riferimenti** per il nuovo progetto. Nel menu di scelta rapida fare clic su **Aggiungi riferimento** per aggiungere un riferimento al progetto contenente il controllo o il componente.  
  
5. Creare un'istanza del controllo o componente nel progetto di test. Se il componente si trova nella **casella degli strumenti**, è possibile trascinarlo nell'area di progettazione oppure creare l'istanza a livello di codice, come illustrato nell'esempio di codice seguente.  
  
    ```vb  
    Dim Component1 As New MyNeatComponent()  
    ```  
  
    ```csharp  
    MyNeatComponent Component1 = new MyNeatComponent();  
    ```  
  
     È ora possibile eseguire il debug del controllo o del componente come di consueto.  
  
 Per altre informazioni sul debug, vedere [Debugging in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio) e [procedura dettagliata: Controlli di debug personalizzato Windows Form in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md).  
  
## <a name="event-is-raised-twice-in-inherited-control-or-component"></a>L'evento viene generato due volte nel componente o controllo ereditato  
 Ciò è probabilmente dovuto a una clausola `Handles` duplicata. Per altre informazioni, vedere [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).  
  
## <a name="design-time-error-failed-to-create-component-component-name"></a>Errore in fase di progettazione: "Impossibile creare il 'componente nome'"  
 Il componente o controllo deve specificare un costruttore predefinito senza parametri. Quando l'ambiente di progettazione crea un'istanza del componente o controllo, non tenta di definire parametri per gli overload del costruttore che accettano tali parametri.  
  
## <a name="stathreadattribute"></a>STAThreadAttribute  
 Il <xref:System.STAThreadAttribute> indica a common language runtime (CLR) che Windows Form usa il modello di apartment a thread singolo. È possibile riscontrare un comportamento imprevisto se non si applica questo attributo al metodo `Main` dell'applicazione Windows Form. Ad esempio, le immagini di sfondo potrebbero non essere visualizzato, ad esempio controlli <xref:System.Windows.Forms.ListView>. Alcuni controlli possono inoltre richiedere questo attributo per il funzionamento corretto del completamento automatico e del trascinamento della selezione.  
  
## <a name="component-icon-does-not-appear-in-toolbox"></a>L'icona del componente non appare nella casella degli strumenti  
 Quando si usa <xref:System.Drawing.ToolboxBitmapAttribute> per associare un'icona con il componente personalizzato, la bitmap non viene visualizzata nella casella degli strumenti per i componenti generati automaticamente. Per visualizzare la bitmap, ricaricare il controllo usando la finestra di dialogo **Scegli elementi della casella degli strumenti**. Per altre informazioni, vedere [Procedura: Specificare una Bitmap nella casella degli strumenti per un controllo](how-to-provide-a-toolbox-bitmap-for-a-control.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)
- [Procedura dettagliata: Debug di controlli di Windows Form personalizzati in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)
- [Modifica di componenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/5dya64wy(v=vs.120))
- [Risoluzione dei problemi relativi allo sviluppo in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171843(v=vs.120))
