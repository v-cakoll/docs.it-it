---
title: 'Procedura: allineare ed estendere un controllo in un controllo TableLayoutPanel'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfc1c64bc0bd9cbebad44193fb5adbe529877487
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>Procedura: allineare ed estendere un controllo in un controllo TableLayoutPanel
È possibile allineare ed estendere i controlli in un <xref:System.Windows.Forms.TableLayoutPanel> con il <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> proprietà.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-align-and-stretch-a-control"></a>Per allineare ed estendere un controllo  
  
1.  Trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo il **della casella degli strumenti** nel form.  
  
2.  Trascinare un <xref:System.Windows.Forms.Button> controllo il **della casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo. Il <xref:System.Windows.Forms.Button> controllo è centrato nella cella.  
  
3.  Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Left,Right`. Il <xref:System.Windows.Forms.Button> controllo occupa in base alla larghezza della cella.  
  
4.  Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Top,Bottom`. Il <xref:System.Windows.Forms.Button> controllo occupa in base all'altezza della cella.  
  
5.  Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>. Il <xref:System.Windows.Forms.Button> controllo si espande per riempire la cella.  
  
6.  Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.None>. Il <xref:System.Windows.Forms.Button> controllo si sposterà all'angolo superiore sinistro della cella e restituisce le dimensioni originali. Il **Progettazione Windows Form** è impostato il <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Top, Left`.  
  
7.  Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà `Bottom,Right`. Il <xref:System.Windows.Forms.Button> controllo si sposta nell'angolo inferiore destro della cella.  
  
8.  Impostare il valore della <xref:System.Windows.Forms.Button> del controllo <xref:System.Windows.Forms.Control.Anchor%2A> proprietà <xref:System.Windows.Forms.AnchorStyles.None>. Il <xref:System.Windows.Forms.Button> controllo viene spostata al centro della cella.  
  
## <a name="see-also"></a>Vedere anche  
 [Controllo TableLayoutPanel](../../../../docs/framework/winforms/controls/tablelayoutpanel-control-windows-forms.md)
