---
title: Cenni preliminari sul componente MainMenu (Windows Form)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952139"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente MainMenu (Windows Form)
> [!IMPORTANT]
> Anche <xref:System.Windows.Forms.MenuStrip> se <xref:System.Windows.Forms.ContextMenuStrip> e sostituiscono e aggiungono <xref:System.Windows.Forms.MainMenu> funzionalità <xref:System.Windows.Forms.ContextMenu> ai controlli e delle versioni precedenti <xref:System.Windows.Forms.ContextMenu> e vengono conservati per compatibilità con le versioni precedenti e per un uso futuro, <xref:System.Windows.Forms.MainMenu> se si sceglie.  
  
 Il componente <xref:System.Windows.Forms.MainMenu> Windows Forms Visualizza un menu in fase di esecuzione. Tutti i sottomenu del menu principale e dei singoli elementi sono <xref:System.Windows.Forms.MenuItem> oggetti.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Una voce di menu può essere designata come elemento predefinito impostando <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> la proprietà `true`su. Quando si fa clic sul menu, l'elemento predefinito viene visualizzato in grassetto. La proprietà della voce <xref:System.Windows.Forms.MenuItem.Checked%2A> di menu `true` può essere `false`o e indica se la voce di menu è selezionata. La <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> proprietà della voce di menu Personalizza l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `true`, accanto all'elemento viene visualizzato un pulsante di opzione; se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false`, accanto all'elemento viene visualizzato un segno di spunta.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Panoramica sul controllo MenuStrip](menustrip-control-overview-windows-forms.md)
