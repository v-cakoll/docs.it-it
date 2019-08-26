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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 9a6938b4fe651e13f3ec96642db6027143f1f028
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015888"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti

Quando si sviluppano e si distribuiscono i controlli, è possibile che tali controlli siano visualizzati nella finestra di dialogo **Scegli elementi della casella degli strumenti** di Visual Studio, che viene visualizzato quando si fa clic con il pulsante destro del mouse sulla **casella degli strumenti** e si seleziona **Scegli elementi**. È possibile abilitare il controllo per la visualizzazione in questa finestra di dialogo tramite la procedura di registrazione AssemblyFoldersEx.

Per visualizzare il controllo nella finestra di dialogo Scegli elementi della casella degli strumenti:

- Installare l'assembly di controllo nel Global Assembly Cache. Per altre informazioni, vedere [Procedura: Installare un assembly nella Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)

  -oppure-

- Registrare il controllo e gli assembly in fase di progettazione associati tramite la procedura di registrazione AssemblyFoldersEx. AssemblyFoldersEx è un percorso del registro di sistema in cui i fornitori di terze parti archiviano percorsi per ogni versione del Framework supportata. La risoluzione in fase di progettazione può essere esaminata nel percorso del registro di sistema per trovare gli assembly di riferimento. Lo script del registro di sistema può specificare i controlli che si desidera visualizzare nella casella degli strumenti.

## <a name="see-also"></a>Vedere anche

- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Procedura: Installare un assembly nella Global Assembly Cache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Procedura dettagliata: Popolamento automatico della casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
