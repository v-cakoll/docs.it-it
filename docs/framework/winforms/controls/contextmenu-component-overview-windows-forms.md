---
title: Panoramica del componente ContextMenu
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746191"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente ContextMenu (Windows Form)
> [!IMPORTANT]
> Anche se <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituiscono e aggiungono funzionalità ai controlli <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono conservati sia per la compatibilità con le versioni precedenti che per un uso futuro, se lo si desidera.  
  
 Con il componente Windows Forms <xref:System.Windows.Forms.ContextMenu>, è possibile fornire agli utenti un menu di scelta rapida facilmente accessibile dei comandi utilizzati di frequente associati all'oggetto selezionato. Gli elementi in un menu di scelta rapida sono spesso un subset degli elementi dei menu principali che vengono visualizzati altrove nell'applicazione. Un utente può in genere accedere a un menu di scelta rapida facendo clic con il pulsante destro del mouse. In Windows Forms i menu di scelta rapida sono associati ai controlli.  
  
## <a name="key-properties"></a>Proprietà chiave  
 È possibile associare un menu di scelta rapida a un controllo impostando la proprietà <xref:System.Windows.Forms.Control.ContextMenu%2A> del controllo sul componente <xref:System.Windows.Forms.ContextMenu>. Un unico menu di scelta rapida può essere associato a più controlli, ma ogni controllo può avere un solo menu di scelta rapida.  
  
 La proprietà chiave del componente <xref:System.Windows.Forms.ContextMenu> è la proprietà <xref:System.Windows.Forms.Menu.MenuItems%2A>. È possibile aggiungere voci di menu a livello di codice creando <xref:System.Windows.Forms.MenuItem> oggetti e aggiungendoli al <xref:System.Windows.Forms.Menu.MenuItemCollection> del menu di scelta rapida. Poiché gli elementi in un menu di scelta rapida vengono in genere creati da altri menu, si aggiungono spesso elementi a un menu di scelta rapida copiando tali elementi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
