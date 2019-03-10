---
title: Cenni preliminari sul controllo Splitter (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 2e3e46c9d4cf118bb846e5d9efefeb0d57fea567
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703193"
---
# <a name="splitter-control-overview-windows-forms"></a>Cenni preliminari sul controllo Splitter (Windows Form)
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.SplitContainer> sostituisce e aggiunge funzionalità per il <xref:System.Windows.Forms.Splitter> controllo delle versioni precedenti, <xref:System.Windows.Forms.Splitter> è stato mantenuto per compatibilità con le versioni precedenti e per un uso futuro, se necessario.  
  
 Windows Form <xref:System.Windows.Forms.Splitter> controlli vengono usati per ridimensionare i controlli ancorati in fase di esecuzione. Il <xref:System.Windows.Forms.Splitter> controllo viene spesso usato nei form con controlli che dispongono di diverse lunghezze dei dati per la presentazione, ad esempio Windows Explorer, la cui riquadri dati contengono informazioni diverse di larghezze in momenti diversi.  
  
## <a name="working-with-the-splitter-control"></a>Utilizzo del controllo barra di divisione  
 Quando l'utente fa riferimento il puntatore del mouse sul bordo di un controllo che può essere ridimensionato da un controllo barra di divisione non ancorato, il puntatore del mouse cambia il suo aspetto per indicare che è possibile ridimensionare il controllo. Con il controllo barra di divisione, l'utente può ridimensionare il controllo ancorato immediatamente precedente. Pertanto, per consentire all'utente di ridimensionare un controllo ancorato in fase di esecuzione, ancorare il controllo deve essere ridimensionato a un bordo di un contenitore e quindi ancorare un controllo splitter al lato del contenitore stesso.  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.SplitContainer>
- [Procedura: Ancorare i controlli in Windows Form](how-to-dock-controls-on-windows-forms.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
