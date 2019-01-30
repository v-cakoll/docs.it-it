---
title: Elemento <socket> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 3f599d6ada288db861f69fc64e6b84ee326b5830
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256894"
---
# <a name="socket-element-network-settings"></a>\<socket > (impostazioni di rete)
Specifica se le operazioni socket usano le porte di completamento.  
  
 \<configuration>  
\<system.net>  
\<Impostazioni >  
\<socket>  
  
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
|`alwaysUseCompletionPortsForAccept`|Indica se il socket deve utilizzare sempre le porte di completamento delle chiamate al metodo Accept. Il valore predefinito è `false`.|  
|`alwaysUseCompletionPortsForConnect`|Indica se il socket deve utilizzare sempre le porte di completamento delle chiamate al metodo Connect. Il valore predefinito è `false`.|  
|`ipProtectionLevel`|Specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket. Il valore predefinito dipende dalla versione di Windows.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|**Elemento**|**Descrizione**|  
|-----------------|---------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.|  
  
## <a name="remarks"></a>Note  
 Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>. Le porte di completamento sono consigliate per le applicazioni server ad alte prestazioni.  
  
 Il valore predefinito per il `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` attributi viene **false**.  
  
 Il <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> può essere utilizzato per ottenere il valore corrente del `alwaysUseCompletionPortsForAccept` attributo dal file di configurazione applicabili. Il <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> può essere utilizzato per ottenere il valore corrente del `alwaysUseCompletionPortsForConnect` attributo dal file di configurazione applicabili.  
  
 Il `ipProtectionLevel` attributo specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket. Il <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà consente la configurazione di una restrizione per un socket IPv6 in un ambito specificato, ad esempio indirizzi con lo stesso prefisso locale del sito o al collegano. Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6. Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni. Questa opzione allarga o restringe l'ambito di un socket di ascolto, consentendo l'accesso illimitato di utenti pubblici e privati, laddove appropriato, o limitando l'accesso solo allo stesso sito, come richiesto.  
  
 Ciò `ipProtectionLevel` impostazione dell'attributo interessa solo il traffico in ingresso iniziale:  
  
-   Un server TCP in ascolto delle connessioni in ingresso su un socket.  
  
-   Un'applicazione di UDP ricezione di un pacchetto su un socket.  
  
 Questa impostazione di configurazione non influisce sulle già stabilite le connessioni TCP (il traffico è senza restrizioni in entrambe le direzioni) e non un'applicazione che invia i pacchetti UDP.  
  
 I valori possibili per il `ipProtectionLevel` impostazione dell'attributo corrispondono ai livelli di protezione definiti specificati nella <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumerazione come illustrato di seguito:  
  
|**Valore dell'attributo**|**Descrizione**|  
|-|-|  
|EdgeRestricted|Il livello di protezione IP è limitato dal perimetro. Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet. Questa impostazione non consente l'attraversamento Network Address Translation (NAT) usando l'implementazione di Windows Teredo. Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi Internet indirizzati alla porta aperta. In Windows Server 2003 e Windows XP, il valore predefinito per il livello di protezione IP in un socket è limitato dal perimetro.|  
|con restrizioni|Il livello di protezione IP è limitato. Questo valore verrebbe utilizzato dalle applicazioni intranet che non implementano scenari Internet. Queste applicazioni non sono in genere testate o protette contro gli attacchi di tipo Internet. Questa impostazione limiterà il traffico ricevuto solo link-local.|  
|Senza restrizioni|Il livello di protezione IP è illimitato. Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet, incluse le applicazioni sfruttando i vantaggi delle funzionalità di attraversamento NAT IPv6 compilate in Windows (ad esempio, Teredo). Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi Internet indirizzati alla porta aperta. In Windows Server 2008 R2 e Windows Vista, il valore predefinito per il livello di protezione IP in un socket è illimitato.|  
|Non specificato|Il livello di protezione IP non è specificato. In Windows 7 e Windows Server 2008 R2, il valore predefinito per il livello di protezione IP in un socket non è specificato.|  
  
 Il valore predefinito per il `ipProtectionLevel` attributo è **Unspecified**.  
  
 Il <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà può essere utilizzata per ottenere il valore corrente del `ipProtectionLevel` attributo dal file di configurazione applicabili.  
  
## <a name="configuration-files"></a>File di configurazione  
 Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come specificare che le porte di completamento devono essere utilizzate e che il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> devono essere senza restrizioni.  
  
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
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
