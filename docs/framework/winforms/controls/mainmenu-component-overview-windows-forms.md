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
ms.openlocfilehash: da1b76a7019f364e7463a8345aa80d9a9bd6089e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168480"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente MainMenu (Windows Form)
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere la funzionalità per il <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.  
  
 I moduli di Windows <xref:System.Windows.Forms.MainMenu> componente consente di visualizzare un menu di scelta in fase di esecuzione. Tutti i sottomenu del menu principale e singoli elementi sono <xref:System.Windows.Forms.MenuItem> oggetti.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Una voce di menu può essere designata come elemento predefinito impostando la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> proprietà `true`. L'elemento predefinito viene visualizzato in grassetto quando si fa clic sul menu. La voce di menu <xref:System.Windows.Forms.MenuItem.Checked%2A> la proprietà `true` o `false`e indica se la voce di menu è selezionata. La voce di menu <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> proprietà consente di personalizzare l'aspetto dell'elemento selezionato: se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostata su `true`, un pulsante di opzione viene visualizzata accanto all'elemento; se <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> è impostato su `false`, viene visualizzato un segno di spunta accanto all'elemento.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Panoramica del controllo MenuStrip](menustrip-control-overview-windows-forms.md)
