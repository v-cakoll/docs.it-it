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
ms.openlocfilehash: 0a3e9ab5a048e085b192ffc0eb796caae1e58efe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a>Procedura: aggiungere controlli senza interfaccia a un Windows Form
Un controllo non visivo (o un componente) fornisce funzionalità per l'applicazione. A differenza di altri controlli, componenti non forniscono un'interfaccia utente per l'utente e pertanto non dovrà essere visualizzato nell'area di progettazione Windows Form. Quando un componente viene aggiunto a un form, Progettazione Windows Form visualizza un contenitore ridimensionabile nella parte inferiore del form vengono visualizzati tutti i componenti. Dopo aver aggiunto un controllo barra dei componenti, è possibile selezionare il componente e impostarne le proprietà come qualsiasi altro controllo nel form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-component-to-a-windows-form"></a>Per aggiungere un componente a un Windows Form  
  
1.  Aprire il form. Per informazioni dettagliate, vedere [procedura: visualizzare Windows Form nella finestra di progettazione](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).  
  
2.  Nel **della casella degli strumenti**, fare clic su un componente e trascinarla nel form.  
  
     Il componente verrà visualizzato nella barra dei componenti.  
  
 Inoltre, i componenti possono essere aggiunti a un form in fase di esecuzione. Si tratta di uno scenario comune, soprattutto perché i componenti non dispone di un'espressione visual, a differenza di controlli che hanno un'interfaccia utente. Nell'esempio seguente, un <xref:System.Windows.Forms.Timer> componente viene aggiunto in fase di esecuzione. (Si noti che Visual Studio contiene un numero di timer diversi; in questo caso, utilizzare un Windows Form <xref:System.Windows.Forms.Timer> componente. Per ulteriori informazioni sui diversi timer in Visual Studio, vedere [Introduzione ai timer basati su Server](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)  
  
> [!CAUTION]
>  Componenti spesso presentano proprietà specifiche del controllo che deve essere impostata per il componente funzionare in modo efficace. In caso del <xref:System.Windows.Forms.Timer> componente, impostare il `Interval` proprietà. Assicurarsi che, quando si aggiunge componenti al progetto, impostare le proprietà necessarie per il componente.  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a>Per aggiungere un componente a un Windows Form a livello di codice  
  
1.  Creare un'istanza di <xref:System.Windows.Forms.Timer> classe nel codice.  
  
2.  Impostare il `Interval` proprietà per determinare il tempo tra i tick del timer.  
  
3.  Configurare le altre proprietà necessarie per il componente.  
  
     Il codice seguente viene illustrata la creazione di un <xref:System.Windows.Forms.Timer> con il relativo `Interval` set di proprietà.  
  
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
    >  Facendo riferimento a un controllo UserControl dannoso può esporre il computer locale a un rischio per la sicurezza attraverso la rete. Questo potrebbe essere solo un problema nel caso di un utente con un controllo personalizzato, seguito da si aggiunga al progetto.  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli Windows Form](../../../../docs/framework/winforms/controls/index.md)  
 [Procedura: Aggiungere controlli a un Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [Procedura: Aggiungere i controlli ActiveX a Windows Form](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [Procedura: Copiare i controlli tra Windows Form](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [Inserimento di controlli in Windows Form](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [Controlli da usare in Windows Form](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Controlli Windows Form per funzione](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
