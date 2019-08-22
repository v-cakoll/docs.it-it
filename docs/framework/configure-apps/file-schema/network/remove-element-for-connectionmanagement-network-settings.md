---
title: Elemento <remove> per connectionManagement (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- connectionManagement, remove element
- <remove> element, connectionManagement
- <connectionManagement>, remove element
- remove element, connectionManagement
ms.assetid: 94b81775-5a22-4975-8c47-8620c40c3f35
ms.openlocfilehash: 8ab7a43fbb3e8df5bb0c99b5947f2fafb362399a
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664036"
---
# <a name="remove-element-for-connectionmanagement-network-settings"></a>\<rimuovere > elemento per connectionManagement (impostazioni di rete)
Rimuove un indirizzo IP o un nome DNS dall'elenco di gestione della connessione.  
  
 \<configuration>  
\<system.net>  
\<> connectionManagement  
\<remove>  
  
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
|`address`|Un indirizzo IP o un nome DNS.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[connectionManagement](connectionmanagement-element-network-settings.md)|Specifica il numero massimo di connessioni a un host di rete.|  
  
## <a name="remarks"></a>Note  
 L' `remove` elemento rimuove la voce dell'elenco di gestione connessione per il server specificato.  
  
 Il valore dell' `address` attributo deve essere un indirizzo IP o un nome host valido.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono rimosse tutte le voci dell'elenco di `www.adventure-works.com` gestione connessione per il server e quindi viene configurata un'applicazione `www.contoso.com` per l'utilizzo di quattro connessioni al server e due connessioni a tutti gli altri server.  
  
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

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [Schema delle impostazioni di rete](index.md)
