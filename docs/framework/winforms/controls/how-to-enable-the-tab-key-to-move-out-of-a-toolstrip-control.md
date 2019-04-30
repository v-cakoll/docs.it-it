---
title: "Procedura: Abilitare il tasto TAB per l'uscita da un controllo ToolStrip"
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
ms.openlocfilehash: d4de7345a4e3ce122c4e1fc0a92f09b447204eb6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941427"
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Procedura: Abilitare il tasto TAB per l'uscita da un controllo ToolStrip
Usare la procedura seguente per abilitare l'utente prema il tasto TAB per passare fuori un <xref:System.Windows.Forms.ToolStrip> al controllo successivo nell'ordine di tabulazione.  
  
 Il <xref:System.Windows.Forms.ToolStrip> accetta la prima pressione del tasto TAB e i tasti di direzione consentono di selezionare elementi all'interno di <xref:System.Windows.Forms.ToolStrip>. Quando l'utente preme il tasto TAB una seconda volta, richiede all'utente il controllo successivo nell'ordine di tabulazione.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Per consentire all'utente di premere il tasto TAB per uscire da un oggetto ToolStrip per il controllo successivo  
  
- Impostare il <xref:System.Windows.Forms.ToolStrip.TabStop%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> a `true`.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.TabStop%2A>
- [Panoramica sul controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
