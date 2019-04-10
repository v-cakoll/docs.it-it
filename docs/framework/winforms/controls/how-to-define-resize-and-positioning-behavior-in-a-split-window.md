---
title: 'Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328673"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a>Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa
I pannelli del <xref:System.Windows.Forms.SplitContainer> controllo si prestano bene a viene ridimensionata e modificati dagli utenti. Tuttavia, vi saranno si vogliano verrà a livello di programmazione della barra di divisione, in cui è posizionato e in che misura può essere spostato.  
  
 Il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà e le altre proprietà di <xref:System.Windows.Forms.SplitContainer> controllo consentono di controllare con precisione il comportamento dell'interfaccia utente in base alle esigenze. Queste proprietà sono elencate nella tabella seguente.  
  
|Nome|Descrizione|  
|----------|-----------------|  
|<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> proprietà|Determina se la barra di divisione è mobile tramite mouse o tastiera.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> proprietà|Determina la distanza in pixel dal bordo sinistro o superiore per la barra di divisione mobile.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà|Determina la distanza minima, in pixel, che la barra di divisione può essere spostato dall'utente.|  
  
 Nell'esempio seguente viene modificato il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà per creare un effetto "allineamento splitter"; quando l'utente trascina la barra di divisione, viene automaticamente incrementato in unità pari a 10 pixel anziché il valore predefinito 1.  
  
### <a name="to-define-splitcontainer-resize-behavior"></a>Per definire il comportamento di ridimensionamento SplitContainer  
  
1. In una procedura, impostare il <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà sulla dimensione desiderata, in modo da ottenuta il comportamento della barra di divisione 'snap'.  
  
     Nell'esempio di codice seguente, all'interno del form <xref:System.Windows.Forms.Form.Load> evento, la barra di divisione all'interno di <xref:System.Windows.Forms.SplitContainer> NFS è impostata su jump 10 pixel quando trascinata.  
  
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
  
     (Visual C#) Inserire il codice seguente nel costruttore del form per registrare il gestore dell'evento.  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     Spostare leggermente la barra di divisione verso sinistra o destra non avranno alcun effetto visibile. Tuttavia, quando il puntatore del mouse esce 10 pixel in direzione orizzontale, la barra di divisione verrà bloccato per la nuova posizione.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
