---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926608"
---
# <a name="allowaccounts"></a>\<allowAccounts>
Contiene una raccolta di elementi di configurazione che specificano gli account utente per i processi che ospitano i servizi Windows Communication Foundation (WCF) e a cui viene concesso l'accesso alla connessione al servizio di condivisione.  
  
 \<system.serviceModel.activation>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Attributo|DESCRIZIONE|  
|---------------|-----------------|  
|[\<add>](add-of-allowaccounts.md)|Aggiunge un account utente per i processi che ospitano servizi WCF e a cui viene concesso l'accesso alla connessione al servizio di condivisione|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|NET. pipe > o [ \<](net-pipe.md) [ \<NET. TCP >](net-tcp.md)|Specifica impostazioni di configurazione per i servizi di condivisione Net Pipe o TCP.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
