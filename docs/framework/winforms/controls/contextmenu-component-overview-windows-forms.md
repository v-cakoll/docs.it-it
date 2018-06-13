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
ms.openlocfilehash: 5d548815533e8f9bb37ad00129a5ae526612ea08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526123"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente ContextMenu (Windows Form)
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e un utilizzo futuro, se si sceglie.  
  
 Windows Form <xref:System.Windows.Forms.ContextMenu> componente, è possibile fornire agli utenti con un menu di scelta rapida facilmente accessibile di comandi utilizzati frequentemente vengono associati all'oggetto selezionato. Gli elementi in un menu di scelta rapida sono spesso un sottoinsieme degli elementi dei menu principali vengono visualizzati in un' posizione nell'applicazione. Un utente di accedere in genere un menu di scelta rapida facendo clic con il mouse. In Windows Form, vengono associati ai controlli menu di scelta rapida.  
  
## <a name="key-properties"></a>Proprietà chiave  
 È possibile associare un menu di scelta rapida con un controllo mediante l'impostazione del controllo <xref:System.Windows.Forms.Control.ContextMenu%2A> proprietà per il <xref:System.Windows.Forms.ContextMenu> componente. Menu di scelta rapida singolo può essere associato a più controlli, ma ciascuno può essere solo un menu di scelta rapida.  
  
 La proprietà chiave di <xref:System.Windows.Forms.ContextMenu> componente è il <xref:System.Windows.Forms.Menu.MenuItems%2A> proprietà. È possibile aggiungere voci di menu a livello di programmazione creando <xref:System.Windows.Forms.MenuItem> oggetti e aggiungendoli al <xref:System.Windows.Forms.Menu.MenuItemCollection> del menu di scelta rapida. Poiché gli elementi in un menu di scelta rapida sono in genere creati da altri menu, è più di frequente verranno aggiungere elementi a un menu di scelta rapida copiandoli.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
