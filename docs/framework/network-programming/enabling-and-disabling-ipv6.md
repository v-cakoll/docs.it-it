---
title: Abilitazione e disabilitazione di IPv6
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 73dee0cb57674c8a2fa4ba2246162870ab1e3a10
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083686"
---
# <a name="enabling-and-disabling-ipv6"></a>Abilitazione e disabilitazione di IPv6
Per usare il protocollo IPv6, assicurarsi di eseguire una versione del sistema operativo che supporti IPv6 e che il sistema operativo e le classi di rete siano configurati correttamente.  
  
## <a name="configuration-steps"></a>Procedura di configurazione  
 La tabella seguente elenca diverse configurazioni  
  
|Sistema operativo abilitato per IPv6|Classi di rete abilitate per IPv6|Description|  
|-------------------------------------|---------------------------------------|-----------------|  
|No|No|È possibile analizzare gli indirizzi IPv6.|  
|No|Sì|È possibile analizzare gli indirizzi IPv6.|  
|Sì|No|È possibile analizzare gli indirizzi IPv6 e risolvere gli indirizzi IPv6 usando metodi di risoluzione dei nomi non contrassegnati come obsoleti.|  
|Sì|Sì|È possibile analizzare e risolvere gli indirizzi IPv6 usando tutti i metodi, inclusi quelli contrassegnati come obsoleti.|  
  
 Tenere presente che, per abilitare il supporto IPv6 per tutte le classi nello spazio dei nomi System.Net, è necessario modificare il file di configurazione del computer o il file di configurazione per l'applicazione. Il file di configurazione per un'applicazione ha la precedenza sul file di configurazione del computer.  
  
 Per un esempio di modifica del file di configurazione del computer, *machine.config*, per abilitare il supporto Ipv6, vedere [Procedura: Modificare il file di configurazione del computer per abilitare il supporto Ipv6](../../../docs/framework/network-programming/how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md). Verificare anche che il supporto IPv6 sia abilitato per il sistema operativo.  
  
 .NET Framework ha un'opzione di configurazione impostata in un file di configurazione nel modo seguente  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 Per .NET Framework versione 1.1 e versioni precedenti, il valore dell'opzione di configurazione **ipv6 enabled** specifica se i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> restituiscono indirizzi IPv6.  
  
 Per .NET Framework versione 2.0 e versioni successive, se Windows supporta IPv6, i membri della classe <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>) restituiscono indirizzi IPv6 con una limitazione. I membri obsoleti del DNS <xref:System.Net.Dns?displayProperty=nameWithType> (ad esempio, il metodo <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>) leggeranno e riconosceranno il valore nel file di configurazione per l'impostazione abilitata per ipv6.  
  
## <a name="see-also"></a>Vedere anche

- [protocollo IPv6](../../../docs/framework/network-programming/internet-protocol-version-6.md)
- [socket](../../../docs/framework/network-programming/sockets.md)
- [Schema delle impostazioni di rete](../../../docs/framework/configure-apps/file-schema/network/index.md)
- [Elemento \<ipv6> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/ipv6-element-network-settings.md)
