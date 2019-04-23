---
title: 'Procedura: Ereditare dalla classe Control'
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- Control class [Windows Forms], inheriting from
- custom controls [Windows Forms], inheritance
- OnPaint method [Windows Forms]
- custom controls [Windows Forms], creating
ms.assetid: 46ba0df3-5cf7-443c-a3b4-a72660172476
ms.openlocfilehash: 14f225f5587379b3efa7b6dc2475f1b697ebb281
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314217"
---
# <a name="how-to-inherit-from-the-control-class"></a>Procedura: Ereditare dalla classe Control
Se si desidera creare un controllo completamente personalizzato da usare in un Form di Windows, è necessario ereditare dal <xref:System.Windows.Forms.Control> classe. Durante l'eredità dal <xref:System.Windows.Forms.Control> classe richiede che si esegue la pianificazione e implementazione più, nonché è la più vasta gamma di opzioni. Quando si eredita da <xref:System.Windows.Forms.Control>, si ereditano le funzionalità di base che consentono di attivare i controlli. La funzionalità riguardante il <xref:System.Windows.Forms.Control> classe gestisce l'input dell'utente tramite tastiera e mouse, definisce i limiti e le dimensioni del controllo, fornisce un handle di windows e fornisce la gestione dei messaggi e sicurezza. Non incorpora nessun disegno, che in questo caso è il rendering reale dell'interfaccia grafica del controllo, e non consente di incorporare alcuna funzionalità di interazione utente specifica. È necessario fornire tutti questi aspetti tramite codice personalizzato.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-create-a-custom-control"></a>Per creare un controllo personalizzato  
  
1. Creare una nuova **Applicazione Windows** o un progetto **Libreria di controllo Windows**.  
  
2. Scegliere **Aggiungi classe** dal menu **Progetto**.  
  
3. Nella finestra di dialogo **Aggiungi nuovo elemento**, fare clic su **Controllo personalizzato**.  
  
     Un nuovo controllo personalizzato viene aggiunto al progetto.  
  
4. Premere F7 per aprire l'**Editor di codice** per il controllo personalizzato.  
  
5. Individuare il <xref:System.Windows.Forms.Control.OnPaint%2A> metodo, che sarà vuoto, ad eccezione di una chiamata al <xref:System.Windows.Forms.Control.OnPaint%2A> metodo della classe di base.  
  
6. Modificare il codice per incorporare il disegno personalizzato desiderato per il controllo.  
  
     Per informazioni sul codice di scrittura per eseguire il rendering della grafica dei controlli, vedere [Disegno e rendering di controlli personalizzati](custom-control-painting-and-rendering.md).  
  
7. Implementare eventuali metodi, proprietà o eventi personalizzati da incorporare nel controllo.  
  
8. Salvare ed eseguire il test del controllo.  
  
## <a name="see-also"></a>Vedere anche

- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
- [Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)
- [Procedura: Ereditare da esistenti di Windows Form](how-to-inherit-from-existing-windows-forms-controls.md)
- [Procedura: Creare controlli per Windows Form](how-to-author-controls-for-windows-forms.md)
- [Risoluzione dei problemi relativi ai gestori eventi ereditati in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
