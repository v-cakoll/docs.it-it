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
ms.openlocfilehash: aa455945b839ada4100138d5bdf9fc239376e5cb
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663978"
---
# <a name="socket-element-network-settings"></a>\<Elemento socket > (impostazioni di rete)
Specifica se le operazioni socket utilizzano le porte di completamento.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<> socket  
  
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
|`ipProtectionLevel`|Specifica il valore <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> predefinito da utilizzare per un socket. Il valore predefinito dipende dalla versione di Windows.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[Impostazioni](settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>. Le porte di completamento sono consigliate per le applicazioni server a prestazioni elevate.  
  
 Il valore predefinito per gli `alwaysUseCompletionPortsForAccept` attributi `alwaysUseCompletionPortsForConnect` e è **false**.  
  
 È <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> possibile utilizzare l'oggetto per ottenere il valore corrente `alwaysUseCompletionPortsForAccept` dell'attributo dai file di configurazione applicabili. È <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> possibile utilizzare l'oggetto per ottenere il valore corrente `alwaysUseCompletionPortsForConnect` dell'attributo dai file di configurazione applicabili.  
  
 L' `ipProtectionLevel` attributo specifica il valore <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> predefinito da utilizzare per un socket. La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà consente la configurazione di una restrizione per un socket IPv6 in un ambito specificato, ad esempio indirizzi con lo stesso prefisso locale del collegamento o del sito. Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6. Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni. Questa opzione consente di ampliare o limitare l'ambito di un socket in ascolto, abilitando l'accesso illimitato da parte di utenti pubblici e privati, quando appropriato, o limitando l'accesso solo allo stesso sito, in base alle esigenze.  
  
 Questa `ipProtectionLevel` impostazione di attributo influisca solo sul traffico in ingresso iniziale:  
  
- Un server TCP in ascolto delle connessioni in ingresso su un socket.  
  
- Un'applicazione UDP che riceve un pacchetto in un socket.  
  
 Questa impostazione di configurazione non influisce sulle connessioni TCP già stabilite (il traffico non è limitato in entrambe le direzioni) e non influisce su un'applicazione che invia pacchetti UDP.  
  
 I valori possibili per l' `ipProtectionLevel` impostazione dell'attributo corrispondono ai livelli di protezione definiti specificati <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> nell'enumerazione, come indicato di seguito:  
  
|**Valore dell'attributo**|**Descrizione**|  
|-|-|  
|EdgeRestricted|Il livello di protezione IP è limitato da Edge. Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet. Questa impostazione non consente l'attraversamento NAT (Network Address Translation) tramite l'implementazione di Windows Teredo. Queste applicazioni possono ignorare i firewall IPv4, quindi le applicazioni devono essere protette da attacchi Internet diretti alla porta aperta. In Windows Server 2003 e Windows XP, il valore predefinito per il livello di protezione IP in un socket è limitato da Edge.|  
|Limitato|Il livello di protezione IP è limitato. Questo valore verrebbe utilizzato dalle applicazioni Intranet che non implementano scenari Internet. Queste applicazioni in genere non sono testate o finalizzate agli attacchi di tipo Internet. Questa impostazione consente di limitare il traffico ricevuto solo al collegamento locale.|  
|Senza restrizioni|Il livello di protezione IP è senza restrizioni. Questo valore verrebbe utilizzato dalle applicazioni progettate per operare su Internet, incluse le applicazioni che sfruttano le funzionalità di attraversamento NAT IPv6 incorporate in Windows (ad esempio, Teredo). Queste applicazioni possono ignorare i firewall IPv4, quindi le applicazioni devono essere protette da attacchi Internet diretti alla porta aperta. In Windows Server 2008 R2 e Windows Vista, il valore predefinito per il livello di protezione IP in un socket è senza restrizioni.|  
|Non specificata|Il livello di protezione IP non è specificato. In Windows 7 e Windows Server 2008 R2, il valore predefinito per il livello di protezione IP in un socket non è specificato.|  
  
 Il valore predefinito per l' `ipProtectionLevel` attributo non è **specificato**.  
  
 È <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> possibile utilizzare la proprietà per ottenere il valore corrente `ipProtectionLevel` dell'attributo dai file di configurazione applicabili.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che devono essere utilizzate le porte di completamento e che <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> l'impostazione predefinita deve essere senza restrizioni.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](index.md)
