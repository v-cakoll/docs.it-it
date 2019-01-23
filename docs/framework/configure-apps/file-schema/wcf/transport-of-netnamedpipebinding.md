---
title: '&lt;transport&gt; di &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 7177dda08e1ce5b4f8adb072dce6155df714979d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556086"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a>&lt;transport&gt; di &lt;netNamedPipeBinding&gt;
Definisce le impostazioni di sicurezza del trasporto per una named pipe.  
  
 \<system.ServiceModel>  
\<le associazioni >  
\<netNamedPipeBinding>  
\<binding>  
\<security>  
\<transport>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|protectionLevel|Definisce il livello di protezione della named pipe. La firma dei messaggi riduce il rischio di manomissione da parte di terzi durante il trasferimento. La crittografia fornisce riservatezza a livello di dati durante il trasporto. Di seguito vengono elencati i valori validi:<br /><br /> -None: Nessuna protezione.<br />-Accesso: I messaggi vengono firmati.<br />-   EncryptAndSign: I messaggi vengono crittografati e firmati.<br /><br /> Il valore predefinito è EncryptAndSign.|  
  
### <a name="child-elements"></a>Elementi figlio  
 nessuno  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|Definisce le impostazioni di sicurezza per un'associazione.|  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [Protezione di servizi e client](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Associazioni](../../../../../docs/framework/wcf/bindings.md)
- [Configurazione di associazioni fornite dal sistema](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Uso di associazioni per configurare servizi e client](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../../../docs/framework/misc/binding.md)
