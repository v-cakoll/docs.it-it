---
title: Grafica e disegno in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: e110203605c31f90f71c949f81c18ebf464d52eb
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505550"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Grafica e disegno in Windows Form
Common language runtime usa un'implementazione di Windows interfaccia GDI (Graphics Device) denominata GDI+ avanzata. Con GDI+ è possibile creare grafici, disegnare il testo e modificare immagini grafiche come oggetti. GDI+ è progettato per offrire prestazioni e semplicità d'uso. È possibile utilizzare GDI+ per eseguire il rendering di immagini grafiche in Windows Form e controlli. Sebbene sia possibile usare GDI+ direttamente nei Web Form, è possibile visualizzare immagini grafiche tramite il controllo Server Web Image.  
  
 In questa sezione sono disponibili argomenti che illustrano i concetti fondamentali della programmazione in GDI+. Anche se non è da considerarsi come un riferimento esaustivo, la sezione contiene informazioni sugli oggetti <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> e <xref:System.Drawing.Color> e riporta informazioni su come creare forme, testo o visualizzare immagini. Per altre informazioni, vedere [riferimento per GDI+](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference).  
  
 Se si preferisce iniziare subito, vedere [Guida introduttiva alla programmazione grafica](getting-started-with-graphics-programming.md), che include argomenti su come usare il codice per disegnare linee, forme, testo e altro in Windows Form.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Cenni preliminari sulla grafica](graphics-overview-windows-forms.md)  
 Fornisce un'introduzione alle classi gestite relative agli elementi grafici.  
  
 [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)  
 Vengono fornite informazioni sulle classi gestite GDI+.  
  
 [Uso di classi grafiche gestite](using-managed-graphics-classes.md)  
 Viene illustrato come a completata una serie di attività usando il GDI+ classi gestite.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing>  
 Fornisce accesso alle funzionalità grafiche di base GDI+.  
  
 <xref:System.Drawing.Drawing2D>  
 Fornisce funzionalità grafica vettoriale e bidimensionale avanzata.  
  
 <xref:System.Drawing.Imaging>  
 Fornisce funzionalità di imaging GDI+ avanzate.  
  
 <xref:System.Drawing.Text>  
 Fornisce funzionalità tipografiche GDI+ avanzate. Le classi presenti in questo spazio dei nomi consentono la creazione e l'uso di raccolte di tipi di carattere.  
  
 <xref:System.Drawing.Printing>  
 Fornisce funzionalità di stampa.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Disegno e rendering di controlli personalizzati](../controls/custom-control-painting-and-rendering.md)  
 Spiega in dettaglio come fornire codice per i controlli di disegno.
