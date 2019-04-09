---
title: 'Procedura: Aggiungere i controlli ActiveX a Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: 780411949c543a2178de5e7c531bd2202703f27a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166050"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Procedura: Aggiungere i controlli ActiveX a Windows Forms
Mentre è con ottimizzazione per la finestra di progettazione Windows Form per ospitare i controlli Windows Form, è anche possibile inserire controlli ActiveX in Windows Form.  
  
> [!CAUTION]
>  Esistono limitazioni delle prestazioni per Windows Form quando i controlli ActiveX a essi aggiunti.  
  
 Prima di aggiungere i controlli ActiveX al form, è necessario aggiungerli nella casella degli strumenti. Per altre informazioni, vedere [componenti COM, finestra di dialogo Personalizza casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-an-activex-control-to-your-windows-form"></a>Per aggiungere un controllo ActiveX a Windows Form  
  
-   Fare doppio clic sul controllo della casella degli strumenti.  
  
     Visual Studio aggiunge tutti i riferimenti al controllo del progetto. Per altre informazioni sugli aspetti da tenere presenti quando si usano controlli ActiveX in Windows Form, vedere [considerazioni sull'inserimento di controlli ActiveX in un Form Windows](considerations-when-hosting-an-activex-control-on-a-windows-form.md).  
  
    > [!NOTE]
    >  Il Windows Form Control Importer di ActiveX (AxImp.exe) crea argomenti dell'evento di tipo diverso da quanto previsto durante l'importazione di librerie a collegamento dinamico ActiveX. Gli argomenti creati da AxImp.exe sono simili al seguente: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)`, quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` è previsto. Tenere presente che questo irregolarità impedisce al codice funziona correttamente. Per informazioni dettagliate, vedere [Windows Forms Control Importer di ActiveX (Aximp.exe)](../../tools/aximp-exe-windows-forms-activex-control-importer.md).  
  
## <a name="see-also"></a>Vedere anche

- [Controlli per Windows Form](index.md)
- [Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Procedura: Aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md)
- [Disposizione di controlli in Windows Form](arranging-controls-on-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
