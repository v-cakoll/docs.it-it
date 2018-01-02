---
title: '&lt;SMTP&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp
- http://schemas.microsoft.com/.NetConfiguration/v2.0#smtp
helpviewer_keywords:
- <smtp> element
- smtp element
ms.assetid: 220b0329-e384-4e0c-86b4-0945ad17efd9
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 598fe3dc2a49187e923cd689f863d0a3327e735f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ltsmtpgt-element-network-settings"></a>&lt;SMTP&gt; elemento (impostazioni di rete)
Configura il formato di consegna, il metodo di consegna e l'indirizzo del mittente per l'invio dei messaggi di posta elettronica.  
  
 \<configuration>  
\<System.NET >  
\<mailSettings >  
\<SMTP >  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
      <smtp  
        deliveryFormat="format"   
        deliveryMethod="method"   
        from="from address">
          <specifiedPickupDirectory> … </ specifiedPickupDirectory >  
          <network> … </network>  
      </smtp>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`deliveryFormat`|Specifica il formato di consegna dei messaggi di posta elettronica in uscita. I valori accettabili sono SevenBit e International.|  
|`deliveryMethod`|Specifica il metodo di recapito dei messaggi di posta elettronica. Valori accettabili sono rete pickupDirectoryFromIis e specifiedPickupDirectory.|  
|`from`|Specifica l'indirizzo del mittente dei messaggi di posta elettronica in uscita.|  
  
### <a name="child-elements"></a>Elementi figlio  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`specifiedPickupDirectory`|Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().|  
|`network`|Consente di configurare le opzioni di rete per un server SMTP esterno.|  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Elemento \<mailSettings> (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Configura opzioni di invio della posta elettronica.|  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network" deliveryFormat="SevenBit"  from="ben@contoso.com">  
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
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpDeliveryFormat>  
 <xref:System.Net.Mail.SmtpDeliveryMethod>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
