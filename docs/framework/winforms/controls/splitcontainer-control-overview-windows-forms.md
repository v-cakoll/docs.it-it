---
title: Cenni preliminari sul controllo SplitContainer
ms.date: 03/30/2017
f1_keywords:
- SplitContainer
helpviewer_keywords:
- SplitContainer control [Windows Forms], about SplitContainer control
ms.assetid: 6de5a5f7-97a5-402d-be6d-7e2785483db5
ms.openlocfilehash: 5cb5240ed4ebe3e27c20844681068711c222e9a9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742918"
---
# <a name="splitcontainer-control-overview-windows-forms"></a>Panoramica del controllo SplitContainer (Windows Form)
Il controllo <xref:System.Windows.Forms.SplitContainer> Windows Form può essere considerato un oggetto composto, poiché è costituito da due pannelli separati da una barra mobile. Quando il puntatore del mouse viene posizionato sopra la barra, assume una forma diversa per indicare che la barra è mobile.  
  
> [!IMPORTANT]
> Nella **casella degli strumenti**<xref:System.Windows.Forms.SplitContainer> controllo sostituisce il controllo <xref:System.Windows.Forms.Splitter> che era presente nella versione precedente di Visual Studio. È consigliabile usare il controllo <xref:System.Windows.Forms.SplitContainer> anziché il controllo <xref:System.Windows.Forms.Splitter>. La classe <xref:System.Windows.Forms.Splitter> è ancora inclusa in .NET Framework per assicurare la compatibilità con le applicazioni esistenti, ma per i nuovi progetti si consiglia di usare il controllo <xref:System.Windows.Forms.SplitContainer>.  
  
 Con il controllo <xref:System.Windows.Forms.SplitContainer> è possibile creare interfacce utente complesse. spesso, una selezione in un pannello determina quali oggetti vengono visualizzati nel pannello altro. Questa disposizione è particolarmente efficace per la visualizzazione e la ricerca di informazioni. La presenza di due pannelli che consentono di aggregare le informazioni in aree, la barra o il "Splitter" consente agli utenti di ridimensionare facilmente i pannelli.  
  
 È anche possibile annidare più di un controllo <xref:System.Windows.Forms.SplitContainer>, con il secondo controllo <xref:System.Windows.Forms.SplitContainer> orientato orizzontalmente, per creare i pannelli superiore e inferiore.  
  
 Tenere presente che il controllo <xref:System.Windows.Forms.SplitContainer> è accessibile da tastiera per impostazione predefinita; Gli utenti possono premere i tasti di direzione per spostare la barra di divisione se la proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> è impostata su `false`.  
  
 La proprietà <xref:System.Windows.Forms.SplitContainer.Orientation%2A> del controllo <xref:System.Windows.Forms.SplitContainer> determina la direzione della barra di divisione, non del controllo stesso. Di conseguenza, quando questa proprietà è impostata su <xref:System.Windows.Forms.Orientation.Vertical>, il separatore viene eseguito dall'alto verso il basso, creando i pannelli sinistro e destro.  
  
 Tenere inoltre presente che il valore della proprietà <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> varia a seconda del valore della proprietà <xref:System.Windows.Forms.SplitContainer.Orientation%2A>. Per ulteriori informazioni, vedere <xref:System.Windows.Forms.SplitContainer.SplitterRectangle%2A> proprietà.  
  
 È anche possibile limitare le dimensioni e lo spostamento del controllo <xref:System.Windows.Forms.SplitContainer>. La proprietà <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A> determina quale pannello rimarrà invariato dopo il ridimensionamento del controllo <xref:System.Windows.Forms.SplitContainer> e la proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> determina se la barra di divisione è mobile mediante la tastiera o il mouse.  
  
> [!NOTE]
> Anche se la proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> è impostata su `true`, la barra di divisione può comunque essere spostata a livello di codice. ad esempio, usando la proprietà <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>.  
  
 Infine, ogni pannello del controllo <xref:System.Windows.Forms.SplitContainer> dispone di proprietà per determinarne le singole dimensioni.  
  
## <a name="commonly-used-properties-methods-and-events"></a>Proprietà, metodi ed eventi usati comunemente  
  
|Name|Descrizione|  
|----------|-----------------|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.FixedPanel%2A>|Determina quale pannello rimarrà invariato dopo il ridimensionamento del controllo <xref:System.Windows.Forms.SplitContainer>.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A>|Determina se la barra di divisione può essere spostata con la tastiera o il mouse.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.Orientation%2A>|Determina se la barra di divisione è disposta verticalmente o orizzontalmente.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A>|Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>|Determina la distanza minima, in pixel, che la barra di divisione può spostare dall'utente.|  
|Proprietà <xref:System.Windows.Forms.SplitContainer.SplitterWidth%2A>|Determina lo spessore, in pixel, della barra di divisione.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoving>|Si verifica quando la barra di divisione viene spostato.|  
|Evento<xref:System.Windows.Forms.SplitContainer.SplitterMoved>|Si verifica quando la barra di divisione viene spostata.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.SplitContainer>
- [Controllo SplitContainer](splitcontainer-control-windows-forms.md)
- [Esempio di controllo SplitContainer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/0ffz7d1b(v=vs.90))
