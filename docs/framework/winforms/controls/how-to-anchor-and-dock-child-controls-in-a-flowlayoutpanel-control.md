---
title: 'Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms], child controls
- FlowLayoutPanel control [Windows Forms], child controls
- controls [Windows Forms], child
- child controls [Windows Forms], anchoring and docking
ms.assetid: a2bcdfca-9b63-45e6-9c0e-3411015cba98
ms.openlocfilehash: 9a00fcd53211dd126c0e9203d6d577959b971e70
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922913"
---
# <a name="how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Procedura: Ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel
Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> supporta le proprietà <xref:System.Windows.Forms.Control.Anchor%2A> e <xref:System.Windows.Forms.Control.Dock%2A> nei controlli figlio.  
  
### <a name="to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control"></a>Per ancorare e agganciare controlli figlio in un controllo FlowLayoutPanel  
  
1. Creare un controllo <xref:System.Windows.Forms.FlowLayoutPanel> nel form.  
  
2. Impostare la <xref:System.Windows.Forms.Control.Width%2A> <xref:System.Windows.Forms.FlowLayoutPanel> proprietà del controllo su **300**e impostare la relativa <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> proprietà <xref:System.Windows.Forms.FlowDirection.TopDown>su.  
  
3. Creare due controlli <xref:System.Windows.Forms.Button> e inserirli nel controllo <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
4. Impostare la <xref:System.Windows.Forms.Control.Width%2A> del primo pulsante su **200**.  
  
5. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> del secondo pulsante su <xref:System.Windows.Forms.DockStyle.Fill>.  
  
    > [!NOTE]
    > Il secondo pulsante assume la stessa larghezza del primo. Non si adatta alla larghezza del controllo <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
6. Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> del secondo pulsante su `None`. Verrà ripristinata la larghezza originale del pulsante.  
  
7. Impostare la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> del secondo pulsante su `Left, Right`.  
  
    > [!IMPORTANT]
    >  Il secondo pulsante assume la stessa larghezza del primo. Non si adatta alla larghezza del controllo <xref:System.Windows.Forms.FlowLayoutPanel>. Di seguito è riportata la regola generale per l'ancoraggio e l'aggancio nel controllo <xref:System.Windows.Forms.FlowLayoutPanel>: per le direzioni del flusso verticale il controllo <xref:System.Windows.Forms.FlowLayoutPanel> calcola la larghezza di una colonna implicita dal controllo figlio più largo presente nella colonna. Tutti gli altri controlli in questa colonna con la proprietà <xref:System.Windows.Forms.Control.Anchor%2A> o <xref:System.Windows.Forms.Control.Dock%2A> vengono allineati o estesi in base alla colonna implicita. Le direzioni del flusso orizzontale si comportano in modo simile. Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> calcola l'altezza di una riga implicita dal controllo figlio più alto presente nella riga e tutti i controlli figlio agganciati o ancorati in questa riga vengono allineati o ridimensionati di conseguenza.  
  
## <a name="example"></a>Esempio  
 La figura seguente illustra quattro pulsanti ancorati e agganciati rispetto al pulsante blu in un controllo <xref:System.Windows.Forms.FlowLayoutPanel>. L'elemento <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> è <xref:System.Windows.Forms.FlowDirection.LeftToRight>.  
  
 ![Ancoraggio FlowLayoutPanel](./media/net-flpanchorexp.gif "NET_FLPanchorExp")  
  
 La figura seguente illustra quattro pulsanti ancorati e agganciati rispetto al pulsante blu in un controllo <xref:System.Windows.Forms.FlowLayoutPanel>. L'elemento <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A> è <xref:System.Windows.Forms.FlowDirection.TopDown>.  
  
 ![Ancoraggio FlowLayoutPanel](./media/vs-flpanchor2.gif "VS_FLPanchor2")  
  
 L'esempio di codice seguente illustra diversi valori della proprietà <xref:System.Windows.Forms.Control.Anchor%2A> per un controllo <xref:System.Windows.Forms.Button> in un controllo <xref:System.Windows.Forms.FlowLayoutPanel>.  
  
 [!code-csharp[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/CS/FlpAnchorExampleForm.cs#1)]
 [!code-vb[System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlowLayoutPanel.AnchorExampleForm/VB/FlpAnchorExampleForm.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Panoramica del controllo FlowLayoutPanel](flowlayoutpanel-control-overview.md)
