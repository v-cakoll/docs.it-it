---
title: 'Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "65210357"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel

È possibile allineare ed estendere i controlli in una <xref:System.Windows.Forms.TableLayoutPanel> con il <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> proprietà.

## <a name="align-and-stretch-a-control"></a>Allineare ed estendere un controllo

1. In Visual Studio, trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllare dal **casella degli strumenti** nel form.

2. Trascinare un <xref:System.Windows.Forms.Button> controllare dal **casella degli strumenti** alla cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo. Il <xref:System.Windows.Forms.Button> controllo viene centrato nella cella.

3. Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Left,Right`. Il <xref:System.Windows.Forms.Button> controllo occupa tutto corrisponda alla larghezza della cella.

4. Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Top,Bottom`. Il <xref:System.Windows.Forms.Button> controllo occupa completamente in base all'altezza della cella.

5. Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>. Il <xref:System.Windows.Forms.Button> controllo si espande per riempire la cella.

6. Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.None>. Il <xref:System.Windows.Forms.Button> controllo restituisce le dimensioni originali e si sposta nell'angolo superiore sinistro della cella. Il **finestra di progettazione Windows Form** è impostata la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Top, Left`.

7. Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Bottom,Right`. Il <xref:System.Windows.Forms.Button> controllo si sposta nell'angolo inferiore destro della cella.

8. Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà <xref:System.Windows.Forms.AnchorStyles.None>. Il <xref:System.Windows.Forms.Button> controllo si sposta al centro della cella.

## <a name="see-also"></a>Vedere anche

- [Controllo TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
