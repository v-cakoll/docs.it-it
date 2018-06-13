---
title: Cenni preliminari sul componente ImageList (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ImageList
helpviewer_keywords:
- collection controls [Windows Forms], images
- icon list control
- ImageList component [Windows Forms], about ImageList component
ms.assetid: 7e25d89b-5633-40c1-afc3-82e0e301ffa2
ms.openlocfilehash: bda9bb71dd2e9b6da2de2444013ed724979f61af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535285"
---
# <a name="imagelist-component-overview-windows-forms"></a>Cenni preliminari sul componente ImageList (Windows Form)
Il componente <xref:System.Windows.Forms.ImageList> di Windows Form viene usato per archiviare immagini, che possono quindi essere visualizzate da altri controlli. Un elenco di immagini consente di scrivere codice per un singolo catalogo di immagini coerente. Ad esempio, è possibile ruotare le immagini visualizzate da un controllo <xref:System.Windows.Forms.Button> semplicemente modificando la proprietà <xref:System.Windows.Forms.ButtonBase.ImageIndex%2A> o <xref:System.Windows.Forms.ButtonBase.ImageKey%2A> del pulsante. È anche possibile associare lo stesso elenco di immagini a più controlli. Se ad esempio si usa sia un controllo <xref:System.Windows.Forms.ListView> che un controllo <xref:System.Windows.Forms.TreeView> per visualizzare lo stesso elenco di file e si modifica l'icona di un file nell'elenco di immagini, la nuova icona comparirà in entrambe le visualizzazioni.  
  
## <a name="using-imagelist-with-controls"></a>Uso di ImageList con i controlli  
 È possibile usare un elenco di immagini con qualsiasi controllo che abbia una proprietà `ImageList` oppure, nel caso del controllo <xref:System.Windows.Forms.ListView>, le proprietà <xref:System.Windows.Forms.ListView.SmallImageList%2A> e <xref:System.Windows.Forms.ListView.LargeImageList%2A>. Di seguito sono elencati i controlli che possono essere associati a un elenco di immagini: <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ToolBar>, <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.RadioButton> e <xref:System.Windows.Forms.Label>. Per associare l'elenco di immagini a un controllo, impostare la proprietà `ImageList` del controllo sul nome del componente <xref:System.Windows.Forms.ImageList>.  
  
## <a name="key-properties"></a>Proprietà chiave  
 La proprietà chiave del componente <xref:System.Windows.Forms.ImageList> è <xref:System.Windows.Forms.ImageList.Images%2A>, che contiene le immagini che verranno usate dal controllo associato. A ogni singola immagine è possibile accedere tramite il valore di indice o la chiave corrispondente. La proprietà <xref:System.Windows.Forms.ImageList.ColorDepth%2A> determina il numero di colori usati per il rendering delle immagini. Le immagini verranno tutte visualizzate con le stesse dimensioni, impostate tramite la proprietà <xref:System.Windows.Forms.ImageList.ImageSize%2A>. Le immagini più grandi verranno ridimensionate e adattate.  
  
 Se si usa [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], è possibile accedere a un'ampia libreria di immagini standard da usare nelle proprie applicazioni.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ImageList>  
 [Procedura: Aggiungere o rimuovere immagini con il componente ImageList di Windows Form](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
