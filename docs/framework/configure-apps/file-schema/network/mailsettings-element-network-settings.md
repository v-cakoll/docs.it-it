---
title: Elemento <mailSettings> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: fb4c8844ed3eb13af483c214d659090c0c563c33
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71698082"
---
# <a name="mailsettings-element-network-settings"></a>Elemento > \<mailSettings (impostazioni di rete)
Configura le opzioni di invio della posta elettronica.  

[ **\<configuration>** ](../configuration-element.md)  
&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)  
&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<mailSettings >**  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
 No.  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|[Elemento > \<smtp (impostazioni di rete)](smtp-element-network-settings.md)|Configura le opzioni del protocollo di trasporto di posta elettronica semplice.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Elemento \<system.Net> (impostazioni di rete)](system-net-element-network-settings.md)|Contiene le impostazioni di rete che specificano la modalità di connessione alla rete di .NET Framework.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.  
  
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
- [Schema delle impostazioni di rete](index.md)
