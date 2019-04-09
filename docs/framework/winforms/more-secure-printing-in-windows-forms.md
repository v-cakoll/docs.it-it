---
title: Stampa più protetta in Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 5ee170980ed02d90606c774e2a7055f047292e33
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197360"
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

- [File e accesso ai dati più protetti in Windows Form](more-secure-file-and-data-access-in-windows-forms.md)
- [Considerazioni aggiuntive sulla sicurezza in Windows Form](additional-security-considerations-in-windows-forms.md)
- [Cenni preliminari sulla sicurezza in Windows Form](security-in-windows-forms-overview.md)
- [Sicurezza di Windows Form](windows-forms-security.md)
