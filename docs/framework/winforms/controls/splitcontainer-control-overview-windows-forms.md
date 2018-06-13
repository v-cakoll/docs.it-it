---
title: Cenni preliminari sul controllo SplitContainer (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 9eea7d397824e443c46acff73fe6db0e43bcfe42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33539478"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Cenni preliminari sul controllo SplitContainer (Windows Form)
Il controllo <xref:System.Windows.Forms.SplitContainer> Windows Form può essere considerato un oggetto composto, poiché è costituito da due pannelli separati da una barra mobile. Quando il puntatore del mouse viene posizionato sopra la barra, assume una forma diversa per indicare che la barra è mobile.  
  
> [!IMPORTANT]
>  Nel **casella degli strumenti**, <xref:System.Windows.Forms.SplitContainer> controllo sostituisce il <xref:System.Windows.Forms.Splitter> controllo che era presente nella versione precedente di Visual Studio. È consigliabile usare il controllo <xref:System.Windows.Forms.SplitContainer> anziché il controllo <xref:System.Windows.Forms.Splitter>. Il <xref:System.Windows.Forms.Splitter> classe è ancora inclusa nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per la compatibilità con le applicazioni esistenti, ma si consiglia di utilizzare il <xref:System.Windows.Forms.SplitContainer> controllo per i nuovi progetti.  
  
 Con il <xref:System.Windows.Forms.SplitContainer> (controllo), è possibile creare complesse interfacce utente, in cui una selezione in un pannello determina quali oggetti vengono visualizzati in un pannello di. Questa disposizione è particolarmente efficace per la visualizzazione e la ricerca di informazioni. Con due pannelli consente aggregare informazioni nelle aree e la barra di "barra di divisione," semplifica agli utenti di ridimensionare i pannelli.  
  
 Più <xref:System.Windows.Forms.SplitContainer> controllo può anche essere annidato, con il secondo <xref:System.Windows.Forms.SplitContainer> controllo orientato in orizzontale, per creare i pannelli superiore e inferiore.  
  
 Tenere presente che il <xref:System.Windows.Forms.SplitContainer> controllo è accessibile da tastiera per impostazione predefinita, gli utenti è possono premere i tasti di direzione per spostare la barra di divisione, se il <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> è impostata su `false`.  
  
 Il <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà del <xref:System.Windows.Forms.SplitContainer> controllo determina la direzione della barra di divisione, non del controllo stesso. Di conseguenza, quando questa proprietà è impostata su <xref:System.Windows.Forms.Orientation.Vertical>, la barra di divisione viene eseguita dall'alto verso il basso, creando un pannello sinistro e destro.  
  
 Inoltre, tenere presente che il valore della <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> proprietà varia a seconda del valore del <xref:System.Windows.Forms.SplitContainer.Orientation%2A> proprietà. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> proprietà.  
  
 È inoltre possibile limitare le dimensioni e lo spostamento del <xref:System.Windows.Forms.SplitContainer> controllo. Il <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> proprietà determina il pannello rimarrà invariata dopo la <xref:System.Windows.Forms.SplitContainer> controllo viene ridimensionato e <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> proprietà determina se la barra di divisione può essere spostata tramite mouse o tastiera.  
  
> [!NOTE]
>  Anche se il <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> è impostata su `true`, la barra di divisione può essere comunque spostata a livello di codice, ad esempio, tramite il <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> proprietà.  
  
 Infine, ogni pannello del <xref:System.Windows.Forms.SplitContainer> controllo dispone di proprietà per determinare le dimensioni.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati comunemente  
  
|nome|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina quale pannello rimarranno invariati dimensioni dopo il <xref:System.Windows.Forms.SplitContainer> controllo viene ridimensionato.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina se la barra di divisione può essere spostata tramite mouse o tastiera.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina se la barra di divisione è disposte orizzontalmente o verticalmente.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distanza minima, in pixel, che la barra di divisione può essere spostato dall'utente.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina lo spessore, in pixel, della barra di divisione.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoving> Evento|Si verifica quando la barra di divisione viene spostato.|  
|<xref:System.Windows.Forms.SplitContainer.SplitterMoved> Evento|Si verifica quando la barra di divisione è stato spostato.|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.SplitContainer>  
 [Controllo SplitContainer](../../../../docs/framework/winforms/controls/splitcontainer-control-windows-forms.md)  
 [Esempio SplitContainer (controllo)](http://msdn.microsoft.com/library/9015fad0-7108-4d85-a83a-a72d038c4f65)
