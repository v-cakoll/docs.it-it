---
title: 'Procedura: aggiungere controlli senza interfaccia a un Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 9458fc7f3344a5692581485a0e5bd462e45551d9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43731988"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Procedura: aggiungere controlli senza interfaccia a un Windows Form
Un controllo non visivo (o componente) offre funzionalità all'applicazione. A differenza di altri controlli, componenti non forniscono un'interfaccia utente per l'utente e pertanto non sono necessario essere visualizzato nell'area di progettazione di Windows Form. Quando un componente viene aggiunto a un form, finestra di progettazione Windows Form consente di visualizzare una barra delle applicazioni ridimensionabile nella parte inferiore del form in cui vengono visualizzati tutti i componenti. Dopo aver aggiunto un controllo alla barra dei componenti, è possibile selezionare il componente e impostarne le proprietà come si farebbe con qualsiasi altro controllo nel form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Per aggiungere un componente a un modulo di Windows  
  
1.  Aprire il form. Per informazioni dettagliate, vedere [procedura: visualizzare Windows Form nella finestra di progettazione](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Nel **casella degli strumenti**, fare clic su un componente e trascinarla al form.  
  
     Il componente viene visualizzato nella barra dei componenti.  
  
 Inoltre, i componenti possono essere aggiunti a un form in fase di esecuzione. Questo è uno scenario comune, soprattutto perché i componenti non è un'espressione visual, a differenza dei controlli che hanno un'interfaccia utente. Nell'esempio seguente, un <xref:System.Windows.Forms.Timer> componente viene aggiunto in fase di esecuzione. (Si noti che Visual Studio contiene un numero di timer diverso; in questo caso, usare un controllo Windows Form <xref:System.Windows.Forms.Timer> componente. Per altre informazioni sui diversi timer in Visual Studio, vedere [Introduzione ai timer basati su Server](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)  
  
> [!CAUTION]
>  I componenti hanno spesso specifico del controllo proprietà che deve essere impostata per il componente garantire il corretto funzionamento. Nel caso del <xref:System.Windows.Forms.Timer> componenti elencati di seguito, si imposta il `Interval` proprietà. Assicurarsi che, quando si aggiungono componenti al progetto, impostare le proprietà necessarie per il componente.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>Per aggiungere un componente a un Windows Form a livello di codice  
  
1.  Creare un'istanza di <xref:System.Windows.Forms.Timer> classe nel codice.  
  
2.  Impostare il `Interval` proprietà per determinare il tempo tra i segni di graduazione del timer.  
  
3.  Configurare le altre proprietà necessarie per il componente.  
  
     Il codice seguente illustra la creazione di un <xref:System.Windows.Forms.Timer> con relativo `Interval` set di proprietà.  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  Facendo riferimento a un controllo utente malintenzionato può esporre il computer locale a un rischio per la sicurezza attraverso la rete. Questa è solo un problema nel caso di un utente con un controllo personalizzato, seguito dall'utente erroneamente aggiungendolo al progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Procedura: Aggiungere i controlli ActiveX a Windows Form](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Procedura: Copiare i controlli tra Windows Form](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [Inserimento di controlli in Windows Form](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
