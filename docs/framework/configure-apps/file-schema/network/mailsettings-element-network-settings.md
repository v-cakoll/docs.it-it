---
title: '&lt;mailSettings&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: 5c7b4d8fae2774fe8e52718fbce91e4bc193c124
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198432"
---
# <a name="ltmailsettingsgt-element-network-settings"></a>&lt;mailSettings&gt; (impostazioni di rete)
Consente di configurare le opzioni di invio della posta elettronica.  

\<configuration>  
\<system.net>  
\<mailSettings>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<mailSettings>
  <smtp> … </smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 Nessuno.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|[\<SMTP > (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura le opzioni Simple Mail Transport Protocol.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Elemento \<system.Net> (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
- <xref:System.Net.Mail.SmtpClient>  
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
