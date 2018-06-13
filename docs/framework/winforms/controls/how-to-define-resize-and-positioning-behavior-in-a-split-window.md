---
title: 'Procedura: definire il ridimensionamento e il posizionamento in una finestra divisa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 015e93fb551b8d48b8a57662b8def61c3cb46c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531635"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Procedura: definire il ridimensionamento e il posizionamento in una finestra divisa
I pannelli del <xref:System.Windows.Forms.SplitContainer> controllo si prestano bene a essere ridimensionati e modificati dagli utenti. Tuttavia, verranno indicate le ore verrà quando si desidera controllare a livello di codice della barra di divisione, in cui è posizionato e in quale misura può essere spostato.  
  
 Il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà e le altre proprietà di <xref:System.Windows.Forms.SplitContainer> controllo offrono un controllo preciso il comportamento dell'interfaccia utente in base alle esigenze. Queste proprietà sono elencate nella tabella seguente.  
  
|nome|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina se la barra di divisione può essere spostata tramite mouse o tastiera.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distanza minima, in pixel, che la barra di divisione può essere spostato dall'utente.|  
  
 Nell'esempio seguente viene modificato il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà per creare un effetto "aggancio divisione"; quando l'utente trascina la barra di divisione, viene incrementata in unità di 10 pixel anziché il valore predefinito 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Per definire il comportamento di ridimensionamento SplitContainer  
  
1.  In una routine, impostare il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà sulla dimensione desiderata, in modo da ottenuta il comportamento della barra di divisione 'snap'.  
  
     Nell'esempio di codice seguente all'interno del form <xref:System.Windows.Forms.Form.Load> evento, la barra di divisione all'interno di <xref:System.Windows.Forms.SplitContainer> NFS è impostata su 10 pixel quando trascinato di spostamento.  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     (Visual c#) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Spostare leggermente la barra di divisione verso sinistra o destra non avrà alcun effetto visibile. Tuttavia, quando il puntatore del mouse esce 10 pixel in direzione orizzontale, la barra di divisione verrà bloccata la nuova posizione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SplitContainer>  
 <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
