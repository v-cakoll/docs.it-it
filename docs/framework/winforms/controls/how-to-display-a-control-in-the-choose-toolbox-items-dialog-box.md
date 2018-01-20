---
title: 'Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3964551ba2eec0980541e95a7db20ef057a1dd61
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti
Quando si sviluppano e si distribuiscono i controlli, si consiglia di tali controlli siano visibili nel **Scegli elementi della casella degli strumenti** nella finestra di dialogo viene visualizzata quando si fa clic su di **della casella degli strumenti** e selezionare  **Scegli elementi**. È possibile abilitare il controllo venga visualizzato nella finestra di dialogo mediante la procedura di registrazione AssemblyFoldersEx.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Per visualizzare il controllo nella finestra di dialogo Scegli elementi della casella degli strumenti  
  
-   Installare l'assembly di controllo per global assembly cache. Per ulteriori informazioni, vedere [procedura: installare un Assembly nella Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     oppure  
  
-   Registrare il controllo e i relativi assembly in fase di progettazione associato utilizzando la procedura di registrazione AssemblyFoldersEx. AssemblyFoldersEx è un percorso del Registro di sistema in cui archiviare i percorsi per ogni versione di framework che supportano i fornitori di terze parti. Risoluzione in fase di progettazione è possibile esaminare in questo percorso del Registro di sistema per individuare gli assembly di riferimento. Lo script del Registro di sistema può specificare i controlli che si desidera visualizzare nella casella degli strumenti. Per ulteriori informazioni, vedere [la distribuzione di un controllo personalizzato e gli assembly in fase di progettazione (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb).  
  
## <a name="see-also"></a>Vedere anche  
 [Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](http://msdn.microsoft.com/library/bd07835f-18a8-433e-bccc-7141f65263bb)  
 [Distribuzione di un controllo personalizzato e gli assembly in fase di progettazione (Visual Studio 2013)](http://msdn.microsoft.com/library/96158eb0-b691-4ae1-9e7b-3c65a1b798cb)  
 [Sviluppo di controlli Windows Form in fase di progettazione](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [Procedura: Installare un assembly nella Global Assembly Cache](../../../../docs/framework/app-domains/how-to-install-an-assembly-into-the-gac.md)  
 [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
