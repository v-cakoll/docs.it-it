---
title: Grafica e disegno in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 3dbb5d36ce2e550c0420a23b40247771e10d60ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Grafica e disegno in Windows Form
Common Language Runtime usa un'implementazione avanzata dell'interfaccia Graphics Device Interface ([!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]) di Windows, denominata [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] consente di creare grafici, testo e di manipolare le immagini come oggetti. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è stato progettato in modo da garantire prestazioni elevate ed è caratterizzato da un'estrema facilità d'uso. È possibile usare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per eseguire il rendering di immagini grafiche in Windows Form e nei relativi controlli. Anche se non è possibile usare [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] direttamente in Web Form, è comunque possibile visualizzare immagini grafiche tramite il controllo server Web Image.  
  
 Questa sezione comprende argomenti in cui vengono presentati i principi fondamentali della programmazione [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Anche se non è da considerarsi come un riferimento esaustivo, la sezione contiene informazioni sugli oggetti <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> e <xref:System.Drawing.Color> e riporta informazioni su come creare forme, testo o visualizzare immagini. Per ulteriori informazioni, vedere [riferimento per GDI+](https://msdn.microsoft.com/library/vs/alm/ms533799.aspx).  
  
 Se si preferisce iniziare subito, vedere [Guida introduttiva alla programmazione grafica](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md), che include argomenti su come usare il codice per disegnare linee, forme, testo e altro in Windows Form.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Cenni preliminari sulla grafica](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 Fornisce un'introduzione alle classi gestite relative agli elementi grafici.  
  
 [Informazioni sul codice gestito GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 Fornisce informazioni sulle classi [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] gestite.  
  
 [Uso di classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)  
 Illustra come completare una serie di attività usando le classi gestite [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing>  
 Fornisce accesso alle funzionalità grafiche di base di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].  
  
 <xref:System.Drawing.Drawing2D>  
 Fornisce funzionalità grafica vettoriale e bidimensionale avanzata.  
  
 <xref:System.Drawing.Imaging>  
 Fornisce funzionalità avanzate [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per le immagini.  
  
 <xref:System.Drawing.Text>  
 Fornisce funzionalità avanzate [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] per la tipografia. Le classi presenti in questo spazio dei nomi consentono la creazione e l'uso di raccolte di tipi di carattere.  
  
 <xref:System.Drawing.Printing>  
 Fornisce funzionalità di stampa.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Disegno e rendering di controlli personalizzati](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)  
 Spiega in dettaglio come fornire codice per i controlli di disegno.
