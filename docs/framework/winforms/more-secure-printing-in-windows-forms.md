---
title: Stampa più sicura
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, printing
- PrintingPermission class [Windows Forms], Windows Forms security
- printing [Windows Forms], security
- security [Windows Forms], printing
ms.assetid: 48fd36ac-872f-4de0-902a-e52969cd4367
ms.openlocfilehash: 6285b76d01660bfa761ea606421f264bdc0c0af5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734886"
---
# <a name="more-secure-printing-in-windows-forms"></a>Stampa più protetta in Windows Form
Le applicazioni Windows Forms includono spesso le funzionalità di stampa. Il .NET Framework utilizza la classe <xref:System.Drawing.Printing.PrintingPermission> per controllare l'accesso alle funzionalità di stampa e il valore di enumerazione <xref:System.Drawing.Printing.PrintingPermissionLevel> associato per indicare il livello di accesso. Per impostazione predefinita, la stampa è abilitata per impostazione predefinita nelle aree Internet e Intranet locale; Tuttavia, il livello di accesso è limitato in entrambe le zone. Se l'applicazione è in grado di stampare, richiede l'intervento dell'utente o non è possibile stampare dipende dal valore di autorizzazione concesso all'applicazione. Per impostazione predefinita, l'area Intranet locale riceve l'accesso <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> e l'area Intranet riceve <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> accesso.  
  
 Nella tabella seguente sono illustrate le funzionalità disponibili a ogni livello di autorizzazione di stampa.  
  
|PrintingPermissionLevel|Descrizione|  
|-----------------------------|-----------------|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>|Consente l'accesso completo a tutte le stampanti installate.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>|Consente la stampa a livello di codice sulla stampante predefinita e la stampa più sicura tramite una finestra di dialogo di stampa restrittiva. <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.AllPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>|Fornisce la stampa solo da una finestra di dialogo con restrizioni. <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.DefaultPrinting>.|  
|<xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting>|Impedisce l'accesso alle stampanti. <xref:System.Drawing.Printing.PrintingPermissionLevel.NoPrinting> è un subset di <xref:System.Drawing.Printing.PrintingPermissionLevel.SafePrinting>.|  
  
## <a name="see-also"></a>Vedere anche

- [Accesso più sicuro a file e dati in Windows Form](more-secure-file-and-data-access-in-windows-forms.md)
- [Considerazioni aggiuntive sulla sicurezza in Windows Form](additional-security-considerations-in-windows-forms.md)
- [Panoramica della sicurezza in Windows Forms](security-in-windows-forms-overview.md)
- [Sicurezza di Windows Form](windows-forms-security.md)
