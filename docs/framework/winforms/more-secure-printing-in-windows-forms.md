---
title: "Stampa più protetta in Windows Form"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b89a94fd0223d817b0dee37f7a3ed84dcbacbbec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="more-secure-printing-in-windows-forms"></a>Stampa più protetta in Windows Form
Applicazioni Windows Forms includono spesso funzionalità di stampa. Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] utilizza il <xref:System.Drawing.Printing.PrintingPermission> classe per controllare l'accesso alle funzionalità di stampa e associato <xref:System.Drawing.Printing.PrintingPermissionLevel> il valore di enumerazione per indicare il livello di accesso. Per impostazione predefinita, la stampa è abilitata per impostazione predefinita nelle aree Internet e Intranet locale; Tuttavia, il livello di accesso è limitato in entrambe le aree. Se l'applicazione può essere stampato, è necessario l'intervento dell'utente, o non stampa dipende dal valore di autorizzazione concesso all'applicazione. Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> accesso e l'area Intranet riceve <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> accesso.  
  
 La tabella seguente illustra le funzionalità disponibili per ogni livello di autorizzazione di stampa.  
  
|PrintingPermissionLevel|Descrizione|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Fornisce accesso completo a tutte le stampanti installate.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Consente la stampa a livello di codice per la stampante predefinita e stampa protetta mediante una finestra di dialogo di stampa limitata. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Consente la stampa solo da una finestra di dialogo più limitata. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Impedisce l'accesso alle stampanti. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Vedere anche  
 [Accesso più sicuro a file e dati in Windows Form](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)  
 [Considerazioni aggiuntive sulla sicurezza in Windows Form](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)  
 [Panoramica della sicurezza in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)  
 [Sicurezza di Windows Form](../../../docs/framework/winforms/windows-forms-security.md)
