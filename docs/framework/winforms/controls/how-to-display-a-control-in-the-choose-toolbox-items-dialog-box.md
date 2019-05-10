---
title: 'Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 4ed3f6ffdf8a86d050b81311c9211767d8b179b8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64623605"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti
Quando si sviluppa e Distribuisci i controlli, è possibile i controlli dalla finestra di **Scegli elementi della casella degli strumenti** nella finestra di dialogo viene visualizzata facendo clic sul **della casella degli strumenti** e selezionare  **Scegli elementi**. È possibile abilitare il controllo venga visualizzato nella finestra di dialogo mediante la procedura di registrazione AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Per visualizzare il controllo nella finestra di dialogo Scegli elementi della casella degli strumenti  
  
- Installare l'assembly di controllo per global assembly cache. Per altre informazioni, vedere [Procedura: Installare un assembly nella Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     -oppure-  
  
- Registrare il controllo e gli assembly in fase di progettazione associati usando la procedura di registrazione AssemblyFoldersEx. AssemblyFoldersEx rappresenta il percorso del Registro di sistema in cui i fornitori di terze parti archiviano i percorsi per ogni versione di framework che supportano. Risoluzione in fase di progettazione può esaminare questo percorso del Registro di sistema per trovare gli assembly di riferimento. Lo script del Registro di sistema può specificare i controlli da visualizzare nella casella degli strumenti. Per altre informazioni, vedere [distribuzione di un controllo personalizzato e gli assembly in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).  
  
## <a name="see-also"></a>Vedere anche

- [Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Distribuzione di un controllo personalizzato e gli assembly in fase di progettazione](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))
- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Procedura: Installare un assembly nella Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
