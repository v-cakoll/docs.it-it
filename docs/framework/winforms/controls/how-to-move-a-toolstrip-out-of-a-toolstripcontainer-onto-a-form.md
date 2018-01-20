---
title: 'Procedura: spostare ToolStrip da ToolStripContainer a un form'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStrip control [Windows Forms], parenting to forms
- Windows Forms, parenting ToolStrip controls
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97d65abf38ee434218fa9bec0d8a9cade31fb687
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Procedura: spostare ToolStrip da ToolStripContainer a un form
Utilizzare la procedura seguente per spostare un <xref:System.Windows.Forms.ToolStrip> da un <xref:System.Windows.Forms.ToolStripContainer> in un form.  
  
> [!NOTE]
>  Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma. Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** . Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-move-a-toolstrip-out-of-a-toolstripcontainer-onto-a-form"></a>Per spostare ToolStrip da ToolStripContainer a un form  
  
1.  Selezionare <xref:System.Windows.Forms.ToolStrip>.  
  
2.  Taglia il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + X o destro di <xref:System.Windows.Forms.ToolStrip> e scegliere **Taglia** dal menu di scelta rapida.  
  
3.  Selezionare il form.  
  
4.  Incolla il <xref:System.Windows.Forms.ToolStrip> premendo CTRL + V oppure scegliere **Incolla** dal **modifica** menu.  
  
5.  Impostare il <xref:System.Windows.Forms.ToolStrip.Dock%2A> proprietà del <xref:System.Windows.Forms.ToolStrip> a **Top**.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 [Panoramica sul controllo ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
