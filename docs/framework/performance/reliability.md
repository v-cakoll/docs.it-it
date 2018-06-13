---
title: Affidabilità
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b00ba0fdf732a864fb4fb757c6012a3d36740b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395411"
---
# <a name="reliability"></a>Affidabilità
È importante che il codice in esecuzione in ambienti server, ad esempio SQL Server, fornisca protezione contro le eccezioni asincrone. L'affidabilità, come descritto in questo argomento, non è specifica di SQL Server, ma della scrittura di codice affidabile per qualsiasi host in esecuzione in un ambiente .NET Framework versione 2.0. SQL Server è tuttavia il primo servizio che fa un uso completo delle nuove funzionalità di affidabilità della versione 2.0, quindi viene usato come esempio.  
  
 Il codice in esecuzione in SQL Server deve rispettare linee guida per l'affidabilità più rigorose rispetto ad altri ambienti server. Ciò è dovuto al funzionamento stabile di SQL Server fino al limite estremo di utilizzo delle risorse.  Le eccezioni <xref:System.OutOfMemoryException> e <xref:System.Threading.ThreadAbortException> non sono rare nell'ambiente SQL Server. Queste linee guida in generale sono incentrate meno sull'affidabilità e più su come consentire al codice gestito completamente attendibile di generare un errore non grave in caso di riciclo a livello di <xref:System.AppDomain>, che rappresenta il modo principale in cui il server mantiene la coerenza e la disponibilità.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Programmazione per SQL Server e attributi di protezione host](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 Descrive come viene usato l'attributo <xref:System.Security.Permissions.HostProtectionAttribute> da SQL Server per limitare l'esecuzione del codice gestito.  
  
 [Procedure consigliate per l'ottimizzazione dell'affidabilità](../../../docs/framework/performance/reliability-best-practices.md)  
 Fornisce linee guida per la scrittura di codice che soddisfa i requisiti di affidabilità.  
  
 [Aree a esecuzione vincolata](../../../docs/framework/performance/constrained-execution-regions.md)  
 Descrive la funzione e il comportamento delle aree a esecuzione vincolata.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
