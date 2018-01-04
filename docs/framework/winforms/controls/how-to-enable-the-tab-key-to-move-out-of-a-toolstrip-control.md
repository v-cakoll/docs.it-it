---
title: 'Procedura: abilitare il tasto TAB per l''uscita da un controllo ToolStrip'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], moving between
- TAB key [Windows Forms], enabling
- ToolStrip control [Windows Forms], moving from
ms.assetid: 40f9e88b-09a3-428e-8da8-c00bb65079c6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 38a2e331d9530c42be6b9047b11ea235ae81d58d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enable-the-tab-key-to-move-out-of-a-toolstrip-control"></a>Procedura: abilitare il tasto TAB per l'uscita da un controllo ToolStrip
Utilizzare la procedura seguente per consentire all'utente di premere il tasto TAB per uscire da un <xref:System.Windows.Forms.ToolStrip> al controllo successivo nell'ordine di tabulazione.  
  
 Il <xref:System.Windows.Forms.ToolStrip> accetta la prima pressione del tasto TAB e i tasti freccia, selezionare elementi all'interno di <xref:System.Windows.Forms.ToolStrip>. Quando l'utente preme il tasto TAB una seconda volta, accetta l'utente al controllo successivo nell'ordine di tabulazione.  
  
### <a name="to-enable-the-user-to-press-the-tab-key-to-move-out-of-a-toolstrip-to-the-next-control"></a>Per consentire all'utente di premere il tasto TAB per passare da un controllo ToolStrip al controllo successivo  
  
-   Impostare il <xref:System.Windows.Forms.ToolStrip.TabStop%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> a `true`.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStrip.TabStop%2A>  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
