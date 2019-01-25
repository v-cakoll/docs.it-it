---
title: '&lt;specifiedPickupDirectory&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#specifiedPickupDirectory
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/specifiedPickupDirectory
helpviewer_keywords:
- specifiedPickupDirectory element
- <specifiedPickupDirectory> element
ms.assetid: 0121f49d-bff2-4bc6-af06-f1628dcd61f1
ms.openlocfilehash: 7735aea55f03b0703ebb7b0e3c5f958b57f1238d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611306"
---
# <a name="ltspecifiedpickupdirectorygt-element-network-settings"></a>&lt;specifiedPickupDirectory&gt; (impostazioni di rete)
Configura la directory locale per un server SMTP Simple Mail Transport Protocol ().  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
\<specifiedPickupDirectory>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<specifiedPickupDirectory  
  pickupDirectoryLocation="directory"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`pickupDirectoryLocation`|La directory in cui le applicazioni salvano i messaggio di posta elettronica per l'elaborazione successiva con il server SMTP.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<SMTP > (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().|  
  
## <a name="remarks"></a>Note  
 Con l'attributo `specifiedPickupDirectory` viene impostata la directory in cui nelle applicazioni vengono salvati i messaggi di posta elettronica da elaborare mediante il server SMTP.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente specifica c:\maildrop come la directory di prelievo della posta.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="SpecifiedPickupDirectory">  
        <specifiedPickupDirectory  
          pickupDirectoryLocation="c:\maildrop"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSpecifiedPickupDirectoryElement?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
