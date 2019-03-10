---
title: Disegno e rendering di controlli personalizzati
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: ec9002ffa4a7e2c82f59d52344764a01afe4c568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722139"
---
# <a name="custom-control-painting-and-rendering"></a>Disegno e rendering di controlli personalizzati
Disegno personalizzato di controlli è una delle numerose attività complesse più semplici da .NET Framework. Durante la creazione di un controllo personalizzato, sono disponibili molte opzioni riguardanti l'aspetto del controllo con interfaccia grafica. Se si crea un controllo da cui eredita il `Control`, è necessario fornire codice che consente il controllo eseguire il rendering della propria rappresentazione grafica. Se si sta creando un controllo utente nulla mediante eredità dal `UserControl`, o sta ereditando da uno dei controlli Windows Form, è possibile eseguire l'override la rappresentazione grafica standard e fornire il proprio codice di grafica. Se si desidera fornire per il rendering personalizzate per i controlli costitutivi di un `UserControl` si sta creando, le opzioni disponibili sono più limitate, ma comunque consentano un'ampia gamma di possibilità con interfaccia grafica per le applicazioni e dei controlli.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Rendering di un controllo di Windows Form](rendering-a-windows-forms-control.md)  
 Viene illustrato come programmare la logica che viene visualizzato un controllo.  
  
 [Controlli creati dall'utente](user-drawn-controls.md)  
 Fornisce una panoramica dei passaggi necessari per la scrittura e si esegue l'override del codice di rendering per il controllo.  
  
 [Controlli costitutivi](constituent-controls.md)  
 Viene descritto come implementare il codice per il rendering personalizzate per i controlli che costituiscono i moduli e controlli utente.  
  
 [Procedura: Rendere invisibile il controllo in fase di esecuzione](how-to-make-your-control-invisible-at-run-time.md)  
 Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.Visible%2A> proprietà per nascondere e mostrare un controllo.  
  
 [Procedura: Assegnare al controllo uno sfondo trasparente](how-to-give-your-control-a-transparent-background.md)  
 Viene illustrato come utilizzare il <xref:System.Windows.Forms.Control.SetStyle%2A> metodo per creare un colore di sfondo è parzialmente trasparente, opaco o trasparente.  
  
 [Rendering dei controlli con stili visivi](rendering-controls-with-visual-styles.md)  
 Viene illustrato come eseguire il rendering di controlli con stili di visualizzazione nei sistemi operativi che li supportano.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Windows.Forms.Control>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.UserControl>  
 Descrive la classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Illustra tale metodo.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Procedura: Creare oggetti Graphics per disegnare](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 Introduce [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funzionalità grafica da una prospettiva e fornisce i collegamenti di Visual Studio per altre informazioni.  
  
 [Tipi di controlli personalizzati](varieties-of-custom-controls.md)  
 Descrive i tipi di controlli personalizzati che è possibile creare.
