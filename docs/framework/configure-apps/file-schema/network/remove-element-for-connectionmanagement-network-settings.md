---
title: '&lt;rimuovere&gt; elemento per connectionManagement (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 92536ad7605211f3a7f606920b054a217427c8f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltremovegt-element-for-connectionmanagement-network-settings"></a>&lt;rimuovere&gt; elemento per connectionManagement (impostazioni di rete)
Rimuove un indirizzo IP o nome DNS dall'elenco di gestione connessione.  
  
 \<configuration>  
\<System.NET >  
\<connectionManagement >  
\<rimuovere >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<remove   
  address="server name or IP address"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`address`|Un indirizzo IP o nome DNS.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a un host di rete.|  
  
## <a name="remarks"></a>Note  
 Il `remove` elemento rimuove la voce di elenco di gestione connessione per il server specificato.  
  
 Il valore di `address` attributo deve essere un nome host o indirizzo IP valido.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente rimuove tutte le voci di elenco di gestione connessione per il server www.adventure-works.com e viene configurata un'applicazione può utilizzare quattro connessioni al server www.contoso.com e due connessioni a tutti gli altri server.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <remove address="http://www.adventure-works.com" />  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Net.ServicePoint>  
 <xref:System.Net.ServicePointManager>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
