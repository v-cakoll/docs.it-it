---
title: 'Procedura: creare un''interfaccia di tipo Esplora risorse in un Windows Form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Explorer [Windows Forms], creating with Windows Forms
- SplitContainer control [Windows Forms], Explorer-style interface
- forms [Windows Forms], Windows Explorer type
ms.assetid: 9a3d5f4f-5dda-4350-9ad5-57ce5976dc47
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c30dd18e7303cf9fe913760da3f9dad7bca3c95
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-explorerstyle-interface-on-a-windows-form"></a>Procedura: creare un'interfaccia di tipo Esplora risorse in un Windows Form
In Esplora risorse è una scelta dell'interfaccia utente comune per le applicazioni a causa la conoscenza pronta.  
  
 In Esplora risorse, in pratica, è un <xref:System.Windows.Forms.TreeView> controllo e un <xref:System.Windows.Forms.ListView> controllo in due pannelli separati. Il ridimensionabili da una barra di divisione. Questa disposizione dei controlli è particolarmente efficace per la visualizzazione e la ricerca di informazioni.  
  
 La procedura seguente viene illustrato come disporre i controlli in un formato simile a Esplora risorse di Windows. Essi non viene illustrato come aggiungere le funzionalità di esplorazione file dell'applicazione in Esplora risorse.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-a-windows-explorer-style-windows-form"></a>Per creare un modulo di Windows di tipo Esplora risorse di Windows  
  
1.  Creare un nuovo progetto applicazione Windows. Per informazioni dettagliate, vedere [Procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
2.  Dal **della casella degli strumenti**:  
  
    1.  Trascinare un <xref:System.Windows.Forms.SplitContainer> controllo nel form.  
  
    2.  Trascinare un <xref:System.Windows.Forms.TreeView> controllare in **SplitterPanel1** (il pannello del <xref:System.Windows.Forms.SplitContainer> controllo contrassegnato **Panel1**).  
  
    3.  Trascinare un <xref:System.Windows.Forms.ListView> controllare in **pannello SplitterPanel2** (il pannello del <xref:System.Windows.Forms.SplitContainer> controllo contrassegnato **Panel2**).  
  
3.  Selezionare tutti i tre controlli premendo il tasto CTRL e facendo clic su essi a sua volta. Quando si seleziona il <xref:System.Windows.Forms.SplitContainer> controllo, fare clic sulla barra di divisione, anziché i pannelli.  
  
    > [!NOTE]
    >  Non utilizzare il **Seleziona tutto** comando il **modifica** menu. Se in tal caso, la proprietà necessaria per il passaggio successivo non compariranno nella **proprietà** finestra.  
  
4.  Nel **proprietà** finestra, impostare il <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.  
  
5.  Premere F5 per eseguire l'applicazione.  
  
     Il modulo Visualizza un'interfaccia utente di due parti, simile a quella di Esplora risorse di Windows.  
  
    > [!NOTE]
    >  Quando si trascina la barra di divisione, i pannelli vengono ridimensionati.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SplitContainer>  
 [Procedura: Creare un'interfaccia utente a più riquadri con Windows Form](../../../../docs/framework/winforms/controls/how-to-create-a-multipane-user-interface-with-windows-forms.md)  
 [Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa](../../../../docs/framework/winforms/controls/how-to-define-resize-and-positioning-behavior-in-a-split-window.md)  
 [Procedura: Suddividere una finestra orizzontalmente](../../../../docs/framework/winforms/controls/how-to-split-a-window-horizontally.md)  
 [Controllo SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)
