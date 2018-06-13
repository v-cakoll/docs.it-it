---
title: Disegno e rendering di controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: 18a05a739f42d41a650e66723f44aae69c1707c7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526051"
---
# <a name="custom-control-painting-and-rendering"></a>Disegno e rendering di controlli personalizzati
Disegno personalizzato di controlli è una delle molte attività complesse semplificata da .NET Framework. Durante la creazione di un controllo personalizzato, sono disponibili molte opzioni riguardanti l'aspetto grafico. Se si sta creando un controllo da cui eredita il `Control`, è necessario fornire codice che consente la rappresentazione grafica di eseguire il rendering del controllo. Se si sta creando un controllo utente ereditando dalla classe di `UserControl`, o da uno dei controlli Windows Form, è possibile eseguire l'override della rappresentazione grafica standard e fornire il proprio codice di grafica. Se si desidera fornire per il rendering personalizzate per i controlli costitutivi di un `UserControl` si esegue la creazione, le opzioni sono più limitate, ma consentono ancora un'ampia gamma di possibilità grafiche per i controlli e le applicazioni.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Rendering di un controllo di Windows Form](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 Viene illustrato come programmare la logica che viene visualizzato un controllo.  
  
 [Controlli creati dall'utente](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 Fornisce una panoramica dei passaggi necessari per la scrittura e si esegue l'override per il controllo del codice di rendering.  
  
 [Controlli costitutivi](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 Viene descritto come implementare il codice per il rendering personalizzate per i controlli che costituiscono il form e controlli utente.  
  
 [Procedura: Rendere invisibile il controllo in fase di esecuzione](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.Visible%2A> proprietà per nascondere e mostrare un controllo.  
  
 [Procedura: Assegnare uno sfondo trasparente al controllo](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per creare un colore di sfondo opaco, trasparente o semitrasparente.  
  
 [Rendering dei controlli con stili visivi](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 Viene illustrato come eseguire il rendering di controlli con stili visivi nei sistemi operativi che li supportano.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.Control>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.UserControl>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Viene descritto il metodo.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Creare oggetti Graphics per disegnare](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Introduce [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funzionalità grafica da una prospettiva e fornisce i collegamenti di Visual Studio per ulteriori informazioni.  
  
 [Tipi di controlli personalizzati](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 Descrive i tipi di controlli personalizzati, che è possibile creare.
