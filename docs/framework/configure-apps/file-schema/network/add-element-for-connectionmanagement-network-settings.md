---
title: Elemento <add> per connectionManagement (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/add
helpviewer_keywords:
- <add> element, connectionManagement
- <connectionManagement>, add element
- add element, connectionManagement
- connectionManagement, add element
ms.assetid: 856bf57d-1c63-46c7-a178-03d97b0a4149
ms.openlocfilehash: 093b68d31e03094bedefa96a2f2d53eb3d84edf0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155011"
---
# <a name="add-element-for-connectionmanagement-network-settings"></a>Elemento \<add> per connectionManagement (impostazioni di rete)
Aggiunge un indirizzo IP o nome DNS all'elenco di gestione delle connessioni.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<connectionManagement>**](connectionmanagement-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<add
  address="address expression"
  maxconnection="integer"
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`address`|Stringa che descrive un indirizzo IP o un nome DNS.|  
|`maxconnection`|Numero massimo di connessioni consentite verso un server. Se non impostato, il valore predefinito è 2.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a un host di rete.|  
  
## <a name="remarks"></a>Commenti  
 Il valore dell'attributo `address` deve essere un'espressione regolare valida o un asterisco per indicare tutte le connessioni oppure una stringa nel formato `<schema>://<idn_hostname>[:<port>]`.  
  
 Se l'URI passato a qualsiasi API HTTP contiene Unicode, il nome verrà convertito internamente usando <xref:System.Uri.DnsSafeHost%2A>, il che potrebbe restituire una stringa Unicode (il comportamento dipende dalla configurazione IDN corrente).  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene configurata un'applicazione per l'utilizzo di quattro connessioni al server `www.contoso.com` e due connessioni a tutti gli altri server.  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address="http://www.contoso.com" maxconnection="4" />  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Schema delle impostazioni di rete](index.md)
