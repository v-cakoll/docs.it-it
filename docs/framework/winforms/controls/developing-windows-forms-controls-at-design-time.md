---
title: Sviluppo di controlli Windows Form in fase di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
ms.openlocfilehash: 267a56cbfd9025e2e20f1468535e5544146535a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529863"
---
# <a name="developing-windows-forms-controls-at-design-time"></a>Sviluppo di controlli Windows Form in fase di progettazione
.NET Framework offre agli autori di controlli numerose tecnologie di creazione dei controlli. Gli autori non devono più limitarsi alla progettazione di controlli compositi che fungono da raccolta dei controlli preesistenti. Grazie all'ereditarietà, è possibile creare i propri controlli da controlli compositi preesistenti o da controlli Windows Form preesistenti. È anche possibile progettare propri controlli che implementano il disegno personalizzato. Queste opzioni offrono una grande flessibilità per la progettazione e la funzionalità dell'interfaccia visiva. Per sfruttare queste funzionalità, è preferibile avere familiarità con i concetti della programmazione basata su oggetti.  
  
> [!NOTE]
>  Non è necessario avere una conoscenza approfondita dell'ereditarietà, ma può risultare utile per fare riferimento a [nozioni fondamentali sull'ereditarietà (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).  
  
 Per creare controlli personalizzati da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](http://msdn.microsoft.com/library/fbe26c16-cff4-4089-b3dd-877411f0c0ef).  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura dettagliata: Modifica di un controllo composito con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 Illustra come creare un controllo composito semplice in Visual Basic.  
  
 [Procedura dettagliata: Modifica di un controllo composito con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)  
 Illustra come creare un controllo composito semplice in C#.  
  
 [Procedura dettagliata: Eredità da un controllo Windows Form con Visual Basic](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)  
 Illustra come creare un controllo Windows Form semplice usando l'ereditarietà in Visual Basic.  
  
 [Procedura dettagliata: Eredità da un controllo Windows Form con Visual C#](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)  
 Illustra come creare un controllo Windows Form semplice usando l'ereditarietà in C#.  
  
 [Procedura dettagliata: Esecuzione di attività comuni con gli smart tag nei controlli Windows Form](../../../../docs/framework/winforms/controls/performing-common-tasks-using-smart-tags-on-wf-controls.md)  
 Illustra come usare la funzionalità di smart tag nei controlli Windows Form.  
  
 [Procedura dettagliata: Serializzazione di raccolte di tipi standard tramite DesignerSerializationVisibilityAttribute](../../../../docs/framework/winforms/controls/serializing-collections-designerserializationvisibilityattribute.md)  
 Viene illustrato come utilizzare il <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> attributo per serializzare una raccolta.  
  
 [Procedura dettagliata: Debug di controlli Windows Form personalizzati in fase di progettazione](../../../../docs/framework/winforms/controls/walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)  
 Illustra come eseguire il debug del comportamento in fase di progettazione di un controllo Windows Form.  
  
 [Procedura dettagliata: Creazione di un controllo Windows Form che usufruisca delle funzionalità offerte da Visual Studio in fase di progettazione](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
 Illustra come integrare profondamente un controllo composito nell'ambiente di progettazione.  
  
 [Procedura: Creare controlli per Windows Form](../../../../docs/framework/winforms/controls/how-to-author-controls-for-windows-forms.md)  
 Offre una serie di considerazioni sull'implementazione di un controllo Windows Form.  
  
 [Procedura: Modificare controlli compositi](../../../../docs/framework/winforms/controls/how-to-author-composite-controls.md)  
 Illustra come creare un controllo ereditando da un controllo composito.  
  
 [Procedura: Ereditare dalla classe UserControl](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)  
 Offre una panoramica della procedura di creazione di un controllo composito.  
  
 [Procedura: Ereditare da controlli Windows Form esistenti](../../../../docs/framework/winforms/controls/how-to-inherit-from-existing-windows-forms-controls.md)  
 Viene illustrato come creare un controllo esteso ereditando dalla classe di <xref:System.Windows.Forms.Button> classe del controllo.  
  
 [Procedura: Ereditare dalla classe Control](../../../../docs/framework/winforms/controls/how-to-inherit-from-the-control-class.md)  
 Offre una panoramica della creazione di un controllo esteso.  
  
 [Procedura: Allineare un controllo ai bordi dei form in fase di progettazione](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.Dock%2A> proprietà per allineare il controllo al bordo del form in cui è contenuto.  
  
 [Procedura: Visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 Illustra la procedura di installazione del controllo in modo che venga visualizzato nella finestra di dialogo **Customize Toolbox** (Personalizza casella degli strumenti).  
  
 [Procedura: Specificare una bitmap nella casella degli strumenti per un controllo](../../../../docs/framework/winforms/controls/how-to-provide-a-toolbox-bitmap-for-a-control.md)  
 Viene illustrato come utilizzare il <xref:System.Drawing.ToolboxBitmapAttribute> per visualizzare un'icona accanto a controllo personalizzato nel **della casella degli strumenti**.  
  
 [Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md)  
 Illustra come usare **UserControl Test Container** per testare il comportamento di un controllo composito.  
  
 [Errori in fase di progettazione in Progettazione Windows Form](../../../../docs/framework/winforms/controls/design-time-errors-in-the-windows-forms-designer.md)  
 Illustra il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Microsoft Visual Studio quando il caricamento di Progettazione Windows Form non riesce.  
  
 [Risoluzione dei problemi relativi alla modifica di controlli e componenti](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)  
 Illustra come diagnosticare e correggere gli errori comuni che possono verificarsi quando si crea un componente o un controllo personalizzato.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Sviluppo di controlli Windows Form personalizzati con .NET Framework](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 Illustra come creare i controlli personalizzati con .NET Framework.  
  
 [Indipendenza del linguaggio e componenti indipendenti dal linguaggio](../../../../docs/standard/language-independence-and-language-independent-components.md)  
 Introduce Common Language Runtime, progettato per semplificare la creazione e l'uso dei componenti. Un aspetto importante di questa semplificazione è la migliore interoperabilità tra componenti scritti usando linguaggi di programmazione diversi. Common Language Specification (CLS) consente di creare strumenti e componenti che usano più linguaggi di programmazione.  
  
 [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 Descrive come abilitare la visualizzazione dei componenti o dei controlli nella finestra di dialogo **Customize Toolbox** (Personalizza casella degli strumenti).
