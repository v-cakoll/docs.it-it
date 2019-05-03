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
ms.openlocfilehash: 2acbcc9197a630a993471c22e572a4f3ed682c64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956052"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Cenni preliminari sul componente ContextMenu (Windows Form)
> [!IMPORTANT]
>  Sebbene <xref:System.Windows.Forms.MenuStrip> e <xref:System.Windows.Forms.ContextMenuStrip> sostituire e aggiungere la funzionalità per il <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> controlli delle versioni precedenti, <xref:System.Windows.Forms.MainMenu> e <xref:System.Windows.Forms.ContextMenu> vengono mantenuti per compatibilità con le versioni precedenti e per un uso futuro, se si sceglie.  
  
 Con i moduli di Windows <xref:System.Windows.Forms.ContextMenu> componente, è possibile fornire agli utenti un menu di scelta rapida facilmente accessibile di comandi usati di frequente associate all'oggetto selezionato. Gli elementi in un menu di scelta rapida sono spesso un sottoinsieme degli elementi del menu principali che vengono visualizzati in un' posizione nell'applicazione. In genere accessibili all'utente un menu di scelta rapida facendo clic con il mouse. In Windows Form, i menu di scelta rapida sono associati ai controlli.  
  
## <a name="key-properties"></a>Proprietà chiave  
 È possibile associare un menu di scelta rapida a un controllo mediante l'impostazione del controllo <xref:System.Windows.Forms.Control.ContextMenu%2A> proprietà per il <xref:System.Windows.Forms.ContextMenu> componente. Un menu di scelta rapida singolo può essere associato a più controlli, ma ogni controllo può avere solo un menu di scelta rapida.  
  
 Le proprietà chiave della <xref:System.Windows.Forms.ContextMenu> componente è il <xref:System.Windows.Forms.Menu.MenuItems%2A> proprietà. È possibile aggiungere voci di menu a livello di programmazione creando <xref:System.Windows.Forms.MenuItem> gli oggetti e ad aggiungerle nel <xref:System.Windows.Forms.Menu.MenuItemCollection> del menu di scelta rapida. Poiché gli elementi in un menu di scelta rapida vengono in genere addebitati altri menu di scelta, è più di frequente aggiungerà gli elementi a un menu di scelta rapida copiandoli.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
