---
title: Cenni preliminari sul componente ContextMenu (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962178"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente ContextMenu (Windows Form)
> [!IMPORTANT]
> Anche <xref:System.Windows.Forms.MenuStrip> se <xref:System.Windows.Forms.ContextMenuStrip> e sostituiscono e aggiungono <xref:System.Windows.Forms.MainMenu> funzionalità <xref:System.Windows.Forms.ContextMenu> ai controlli e delle versioni precedenti <xref:System.Windows.Forms.ContextMenu> e vengono conservati per compatibilità con le versioni precedenti e per un uso futuro, <xref:System.Windows.Forms.MainMenu> se si sceglie.  
  
 Con il componente <xref:System.Windows.Forms.ContextMenu> Windows Forms, è possibile fornire agli utenti un menu di scelta rapida facilmente accessibile dei comandi utilizzati di frequente associati all'oggetto selezionato. Gli elementi in un menu di scelta rapida sono spesso un subset degli elementi dei menu principali che vengono visualizzati altrove nell'applicazione. Un utente può in genere accedere a un menu di scelta rapida facendo clic con il pulsante destro del mouse. In Windows Forms i menu di scelta rapida sono associati ai controlli.  
  
## <a name="key-properties"></a>Proprietà chiave  
 È possibile associare un menu di scelta rapida a un controllo impostando la <xref:System.Windows.Forms.Control.ContextMenu%2A> proprietà <xref:System.Windows.Forms.ContextMenu> del controllo sul componente. Un unico menu di scelta rapida può essere associato a più controlli, ma ogni controllo può avere un solo menu di scelta rapida.  
  
 La proprietà chiave del <xref:System.Windows.Forms.ContextMenu> componente è la <xref:System.Windows.Forms.Menu.MenuItems%2A> proprietà. È possibile aggiungere voci di menu a livello di <xref:System.Windows.Forms.MenuItem> codice creando oggetti e aggiungendoli <xref:System.Windows.Forms.Menu.MenuItemCollection> a del menu di scelta rapida. Poiché gli elementi in un menu di scelta rapida vengono in genere creati da altri menu, si aggiungono spesso elementi a un menu di scelta rapida copiando tali elementi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
