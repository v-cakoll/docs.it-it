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
ms.openlocfilehash: a7ea9fcf25942f21d2d549ea998161398fbc608f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534212"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente MainMenu (Windows Form)
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere funzionalità a di <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e un utilizzo futuro, se si sceglie.  
  
 Windows Form <xref:System.Windows.Forms.MainMenu> componente consente di visualizzare un menu in fase di esecuzione. Tutti i sottomenu del menu principale e singoli elementi <xref:System.Windows.Forms.MenuItem> oggetti.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Una voce di menu può essere designata come voce predefinita impostando la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> proprietà `true`. Quando si fa clic sul menu, la voce predefinita viene visualizzata in grassetto. La voce di menu <xref:System.Windows.Forms.MenuItem.Checked%2A> la proprietà `true` o `false`e indica se è selezionata la voce di menu. La voce di menu <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> proprietà consente di personalizzare l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `true`, viene visualizzato un pulsante di opzione accanto all'elemento; se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false`, viene visualizzato un segno di spunta accanto all'elemento.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [Panoramica sul controllo MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
