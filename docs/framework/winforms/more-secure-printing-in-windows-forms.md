---
title: Stampa più protetta in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 2bf05461014c3511725cb28caf2de0eb4c2e1d5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621799"
---
# <a name="more-secure-printing-in-windows-forms"></a>Stampa più protetta in Windows Form
Le applicazioni Windows Forms spesso includono funzionalità di stampa. Il [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] utilizza le <xref:System.Drawing.Printing.PrintingPermission> classe per controllare l'accesso alle funzionalità di stampa e associato <xref:System.Drawing.Printing.PrintingPermissionLevel> valore di enumerazione per indicare il livello di accesso. Per impostazione predefinita, la stampa è abilitata per impostazione predefinita nelle aree Internet e Intranet locale; Tuttavia, il livello di accesso è limitato in entrambe le aree. Se l'applicazione può essere stampato, richiede l'intervento dell'utente, o non è possibile stampare dipende il valore dell'autorizzazione concesso all'applicazione. Per impostazione predefinita, l'area Intranet locale riceve <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> riceve l'accesso e l'area Intranet <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> accesso.  
  
 La tabella seguente illustra le funzionalità disponibili in ogni livello di autorizzazione Stampa.  
  
|PrintingPermissionLevel|Descrizione|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Fornisce accesso completo a tutte le stampanti installate.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Abilita la stampa a livello di codice sulla stampante predefinita e stampa più sicura tramite una finestra di dialogo Stampa restrittivi. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Consente la stampa solo da una finestra di dialogo più limitata. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Impedisce l'accesso alle stampanti. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Vedere anche
- [Accesso più sicuro a file e dati in Windows Form](../../../docs/framework/winforms/more-secure-file-and-data-access-in-windows-forms.md)
- [Considerazioni aggiuntive sulla sicurezza in Windows Form](../../../docs/framework/winforms/additional-security-considerations-in-windows-forms.md)
- [Panoramica della sicurezza in Windows Forms](../../../docs/framework/winforms/security-in-windows-forms-overview.md)
- [Sicurezza di Windows Form](../../../docs/framework/winforms/windows-forms-security.md)
