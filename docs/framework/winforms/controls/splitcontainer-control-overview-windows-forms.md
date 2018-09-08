---
title: Cenni preliminari sul controllo SplitContainer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 81898e09ff513043b205cde13378ae24ee755226
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44193799"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Cenni preliminari sul controllo SplitContainer (Windows Form)
Il controllo <xref:System.Windows.Forms.SplitContainer> Windows Form può essere considerato un oggetto composto, poiché è costituito da due pannelli separati da una barra mobile. Quando il puntatore del mouse viene posizionato sopra la barra, assume una forma diversa per indicare che la barra è mobile.  
  
> [!IMPORTANT]
>  Nel **casella degli strumenti**, <xref:System.Windows.Forms.SplitContainer> controllo sostituisce il <xref:System.Windows.Forms.Splitter> controllo che era presente nella versione precedente di Visual Studio. È consigliabile usare il controllo <xref:System.Windows.Forms.SplitContainer> anziché il controllo <xref:System.Windows.Forms.Splitter>. Il <xref:System.Windows.Forms.Splitter> classe è ancora incluso nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per la compatibilità con le applicazioni esistenti, ma si consiglia di utilizzare il <xref:System.Windows.Forms.SplitContainer> controllo per i nuovi progetti.  
  
 Con la <xref:System.Windows.Forms.SplitContainer> (controllo), è possibile creare complesse interfacce utente, spesso, una selezione in un pannello determina quali oggetti vengono visualizzati in altro pannello. Questa disposizione è particolarmente efficace per la visualizzazione e la ricerca di informazioni. Con due pannelli consente aggregare informazioni nelle aree e la barra di "separatore", rende più semplice per gli utenti di ridimensionare i pannelli.  
  
 Più di un <xref:System.Windows.Forms.SplitContainer> controllo può anche essere annidato, con il secondo <xref:System.Windows.Forms.SplitContainer> controllo orientato orizzontalmente, creare pannelli superiore e inferiore.  
  
 Tenere presente che il <xref:System.Windows.Forms.SplitContainer> controllo è accessibile dalla tastiera per impostazione predefinita, gli utenti possono premere i tasti di direzione per spostare la barra di divisione, se il <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> è impostata su `false`.  
  
 Il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo determina la direzione della barra di divisione, non del controllo stesso. Di conseguenza, quando questa proprietà è impostata su <xref:System.Windows.Forms.Orientation.Vertical>, la barra di divisione viene eseguito dall'alto verso il basso, creando un pannello a sinistra e destra.  
  
 Inoltre, tenere presente che il valore della <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> proprietà varia a seconda del valore del <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà. Per altre informazioni, vedere <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> proprietà.  
  
 È inoltre possibile limitare le dimensioni e lo spostamento del <xref:System.Windows.Forms.SplitContainer> controllo. Il <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> proprietà determina il pannello rimarranno le stesse dimensioni dopo il <xref:System.Windows.Forms.SplitContainer> controllo viene ridimensionato e il <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> proprietà determina se la barra di divisione è mobile tramite mouse o tastiera.  
  
> [!NOTE]
>  Anche se il <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> è impostata su `true`, la barra di divisione può comunque essere spostato a livello di programmazione, ad esempio, usando il <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> proprietà.  
  
 Infine, ogni pannello del <xref:System.Windows.Forms.SplitContainer> controllo dispone di proprietà per determinarne le dimensioni.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati comunemente  
  
|nome|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina quale pannello rimarranno invariati dimensione dopo il <xref:System.Windows.Forms.SplitContainer> controllo viene ridimensionato.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina se la barra di divisione può essere spostato con la tastiera o il mouse.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina se la barra di divisione viene disposto orizzontalmente o verticalmente.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distanza in pixel dal bordo sinistro o superiore per la barra di divisione mobile.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distanza minima, in pixel, che la barra di divisione può essere spostato dall'utente.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina lo spessore, in pixel, della barra di divisione.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoving> |Si verifica quando la barra di divisione viene spostato.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoved> |Si verifica quando la barra di divisione viene spostato.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SplitContainer>  
 [Controllo SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [Esempio di controllo SplitContainer](https://msdn.microsoft.com/library/9015fad0-7108-4d85-a83a-a72d038c4f65)
