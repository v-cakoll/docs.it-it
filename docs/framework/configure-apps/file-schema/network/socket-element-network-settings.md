---
title: Elemento <socket> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089085"
---
# <a name="socket-element-network-settings"></a>Elemento \<socket> (impostazioni di rete)
Specifica se le operazioni socket utilizzano le porte di completamento.  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

## <a name="syntax"></a>Sintassi  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|**Attributo**|**Descrizione**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Indica se il socket deve utilizzare sempre le porte di completamento per le chiamate al metodo Accept. Il valore predefinito è `false`.|  
|`alwaysUseCompletionPortsForConnect`|Indica se il socket deve utilizzare sempre le porte di completamento per le chiamate al metodo Connect. Il valore predefinito è `false`.|  
|`ipProtectionLevel`|Specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket. Il valore predefinito dipende dalla versione di Windows.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Commenti  
 Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>. Le porte di completamento sono consigliate per le applicazioni server a prestazioni elevate.  
  
 Il valore predefinito per gli `alwaysUseCompletionPortsForAccept` `alwaysUseCompletionPortsForConnect` attributi e è **false**.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>È possibile utilizzare l'oggetto per ottenere il valore corrente dell' `alwaysUseCompletionPortsForAccept` attributo dai file di configurazione applicabili. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>È possibile utilizzare l'oggetto per ottenere il valore corrente dell' `alwaysUseCompletionPortsForConnect` attributo dai file di configurazione applicabili.  
  
 L' `ipProtectionLevel` attributo specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket. La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà consente la configurazione di una restrizione per un socket IPv6 in un ambito specificato, ad esempio indirizzi con lo stesso prefisso locale del collegamento o del sito. Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6. Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni. Questa opzione consente di ampliare o limitare l'ambito di un socket in ascolto, abilitando l'accesso illimitato da parte di utenti pubblici e privati, quando appropriato, o limitando l'accesso solo allo stesso sito, in base alle esigenze.  
  
 Questa `ipProtectionLevel` impostazione di attributo influisca solo sul traffico in ingresso iniziale:  
  
- Un server TCP in ascolto delle connessioni in ingresso su un socket.  
  
- Un'applicazione UDP che riceve un pacchetto in un socket.  
  
 Questa impostazione di configurazione non influisce sulle connessioni TCP già stabilite (il traffico non è limitato in entrambe le direzioni) e non influisce su un'applicazione che invia pacchetti UDP.  
  
 I valori possibili per l' `ipProtectionLevel` impostazione dell'attributo corrispondono ai livelli di protezione definiti specificati nell' <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumerazione, come indicato di seguito:  
  
|**Valore dell'attributo**|**Descrizione**|  
|-|-|  
|EdgeRestricted|Il livello di protezione IP è limitato dal perimetro. Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet. Questa impostazione non consente l'attraversamento NAT (Network Address Translation) tramite l'implementazione di Windows Teredo. Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi provenienti da Internet diretti alla porta aperta. In Windows Server 2003 e in Windows XP, il valore predefinito per il livello di protezione IP in un socket è limitato dal perimetro.|  
|Con restrizioni|Il livello di protezione IP è limitato. Questo valore verrebbe utilizzato da applicazioni Intranet che non implementano scenari Internet. Queste applicazioni non sono in genere testate o protette da attacchi analoghi a quelli provenienti da Internet. Questa impostazione limiterà il traffico ricevuto solo a quello locale rispetto al collegamento.|  
|Senza restrizioni|Il livello di protezione IP è illimitato. Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet, incluse la applicazioni che usufruiscono delle funzionalità di attraversamento NAT IPv6 compilate in Windows (ad esempio, Teredo). Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi provenienti da Internet diretti alla porta aperta. In Windows Server 2008 R2 e in Windows Vista, il valore predefinito per il livello di protezione IP in un socket è illimitato.|  
|Non specificata|Il livello di protezione IP non è specificato. In Windows 7 e in Windows Server 2008 R2, il valore predefinito per il livello di protezione IP in un socket non è specificato.|  
  
 Il valore predefinito per l' `ipProtectionLevel` attributo non è **specificato**.  
  
 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `ipProtectionLevel` attributo dai file di configurazione applicabili.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che devono essere utilizzate le porte di completamento e che l'impostazione predefinita <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> deve essere senza restrizioni.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
