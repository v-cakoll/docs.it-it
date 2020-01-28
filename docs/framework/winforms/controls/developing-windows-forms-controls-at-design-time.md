---
title: Sviluppare controlli in fase di progettazione
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls [Windows Forms]
- Windows Forms controls, creating
- controls [Windows Forms]
- controls [Windows Forms], creating
- user controls [Windows Forms]
- custom controls [Windows Forms]
ms.assetid: e5a8e088-7ec8-4fd9-bcb3-9078fd134829
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dac049ea6a51037daa0e23dc93476e4410b2df06
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745993"
---
# <a name="develop-windows-forms-controls-at-design-time"></a>Sviluppare controlli Windows Forms in fase di progettazione

.NET Framework offre agli autori di controlli numerose tecnologie di creazione dei controlli. Gli autori non devono più limitarsi alla progettazione di controlli compositi che fungono da raccolta dei controlli preesistenti. Grazie all'ereditarietà, è possibile creare i propri controlli da controlli compositi preesistenti o da controlli Windows Form preesistenti. È anche possibile progettare propri controlli che implementano il disegno personalizzato. Queste opzioni offrono una grande flessibilità per la progettazione e la funzionalità dell'interfaccia visiva. Per sfruttare queste funzionalità, è preferibile avere familiarità con i concetti della programmazione basata su oggetti.

> [!NOTE]
> Non è necessario avere una conoscenza approfondita dell'ereditarietà, ma può essere utile fare riferimento a [nozioni fondamentali sull'ereditarietà (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md).

Per creare controlli personalizzati da usare nei Web Form, vedere [Sviluppo di controlli server ASP.NET personalizzati](https://docs.microsoft.com/previous-versions/aspnet/zt27tfhy(v=vs.100)).

## <a name="in-this-section"></a>In questa sezione

[Procedura dettagliata: modifica di un controllo composito](walkthrough-authoring-a-composite-control-with-visual-csharp.md)\
Illustra come creare un controllo composito semplice in C#.

[Procedura dettagliata: eredità da un controllo Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)\
Illustra come creare un controllo Windows Form semplice usando l'ereditarietà in C#.

[Procedura dettagliata: esecuzione di attività comuni usando gli smart tag nei controlli Windows Forms](performing-common-tasks-using-smart-tags-on-wf-controls.md)\
Illustra come usare la funzionalità di smart tag nei controlli Windows Form.

[Procedura dettagliata: serializzazione di raccolte di tipi standard con DesignerSerializationVisibilityAttribute](serializing-collections-designerserializationvisibilityattribute.md)\
Viene illustrato come utilizzare l'attributo <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content?displayProperty=nameWithType> per serializzare una raccolta.

[Procedura dettagliata: Debug di controlli Windows Form personalizzati in fase di progettazione](walkthrough-debugging-custom-windows-forms-controls-at-design-time.md)\
Illustra come eseguire il debug del comportamento in fase di progettazione di un controllo Windows Form.

[Procedura dettagliata: creazione di un controllo Windows Forms che sfrutta le funzionalità della fase di progettazione di Visual Studio](creating-a-wf-control-design-time-features.md)\
Illustra come integrare profondamente un controllo composito nell'ambiente di progettazione.

[Procedura: Creare controlli per Windows Forms](how-to-author-controls-for-windows-forms.md)\
Offre una serie di considerazioni sull'implementazione di un controllo Windows Form.

[Procedura: modificare controlli compositi](how-to-author-composite-controls.md)\
Illustra come creare un controllo ereditando da un controllo composito.

[Procedura: Ereditare dalla classe UserControl](how-to-inherit-from-the-usercontrol-class.md)\
Offre una panoramica della procedura di creazione di un controllo composito.

[Procedura: Ereditare da controlli di Windows Forms esistenti](how-to-inherit-from-existing-windows-forms-controls.md)\
Viene illustrato come creare un controllo esteso ereditando dalla classe del controllo <xref:System.Windows.Forms.Button>.

[Procedura: Ereditare dalla classe Control](how-to-inherit-from-the-control-class.md)\
Offre una panoramica della creazione di un controllo esteso.

[Procedura: allineare un controllo ai bordi dei form in fase di progettazione](how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)\
Viene illustrato come utilizzare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> per allineare il controllo al bordo del form che occupa.

[Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)\
Illustra la procedura di installazione del controllo in modo che venga visualizzato nella finestra di dialogo **Customize Toolbox** (Personalizza casella degli strumenti).

[Procedura: specificare una bitmap della casella degli strumenti per un controllo](how-to-provide-a-toolbox-bitmap-for-a-control.md)\
Viene illustrato come utilizzare il <xref:System.Drawing.ToolboxBitmapAttribute> per visualizzare un'icona accanto al controllo personalizzato nella **casella degli strumenti**.

[Procedura: Eseguire il test del comportamento in fase di esecuzione di UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)\
Illustra come usare **UserControl Test Container** per testare il comportamento di un controllo composito.

[Errori in fase di progettazione in Progettazione Windows Form](design-time-errors-in-the-windows-forms-designer.md)\
Illustra il significato e l'uso dell'elenco errori della fase di progettazione visualizzato in Microsoft Visual Studio quando il caricamento di Progettazione Windows Form non riesce.

[Risoluzione dei problemi relativi alla modifica di controlli e componenti](troubleshooting-control-and-component-authoring.md)\
Illustra come diagnosticare e correggere gli errori comuni che possono verificarsi quando si crea un componente o un controllo personalizzato.

## <a name="reference"></a>Riferimenti

- <xref:System.Windows.Forms.Control?displayProperty=nameWithType>

- <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>

## <a name="related-sections"></a>Sezioni correlate

[Sviluppo di controlli Windows Form personalizzati con .NET Framework](developing-custom-windows-forms-controls.md)\
Illustra come creare i controlli personalizzati con .NET Framework.

[Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md)\
Introduce Common Language Runtime, progettato per semplificare la creazione e l'uso dei componenti. Un aspetto importante di questa semplificazione è la migliore interoperabilità tra componenti scritti usando linguaggi di programmazione diversi. Common Language Specification (CLS) consente di creare strumenti e componenti che usano più linguaggi di programmazione.

[Procedura dettagliata: compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)\
Descrive come abilitare la visualizzazione dei componenti o dei controlli nella finestra di dialogo **Customize Toolbox** (Personalizza casella degli strumenti).
