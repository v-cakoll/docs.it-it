---
title: '&lt;rete&gt; (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 7270cee07bea50aa50dc191ac957132e2794c0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599263"
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;rete&gt; (impostazioni di rete)
Consente di configurare le opzioni di rete per un server SMTP Simple Mail Transport Protocol () esterno.  
  
 \<configuration>  
\<system.net>  
\<mailSettings>  
\<smtp>  
\<network>  
  
## <a name="syntax"></a>Sintassi  
  
```xml  
<network  
  clientDomain="string"   
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"   
  password="string"  
  port="integer"   
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Attributi ed elementi  
 Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.  
  
### <a name="attributes"></a>Attributi  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`clientDomain`|Specifica il nome di dominio client da usare nella richiesta iniziale di protocollo SMTP per connettersi al server di posta SMTP. Il valore predefinito è il nome host locale del computer locale l'invio della richiesta.|  
|`defaultCredentials`|Specifica se le credenziali dell'utente predefinito devono essere utilizzate per accedere al server di posta elettronica SMTP per le transazioni SMTP. Il valore predefinito è `false`.|  
|`enableSsl`|Specifica se SSL viene utilizzato per accedere a un server di posta SMTP. Il valore predefinito è `false`.|  
|`host`|Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP. Questo attributo non ha alcun valore predefinito.|  
|`password`|Specifica la password da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non ha alcun valore predefinito.|  
|`port`|Specifica il numero di porta da usare per connettersi al server di posta SMTP. Il valore predefinito è 25.|  
|`targetName`|Specifica il nome di Provider di servizio (SPN) da usare per l'autenticazione quando si usa la protezione estesa per le transazioni SMTP. Questo attributo non ha alcun valore predefinito.|  
|`userName`|Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non ha alcun valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<SMTP > (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().|  
  
## <a name="remarks"></a>Note  
 Alcuni server SMTP richiedono autenticarsi al server prima dell'uso. Se si desidera eseguire l'autenticazione manualmente usando le credenziali di rete predefinite nell'host, impostare il `defaultCredentials` dell'attributo `true`. Il <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `defaultCredentials` attributo dal file di configurazione applicabili.  
  
 È anche possibile usare l'autenticazione di base (nome utente e password) per autenticarsi presso il server SMTP. Per usare questa opzione, è necessario specificare un nome utente valido e una password per il server SMTP specificato.  
  
> [!NOTE]
>  L'autenticazione di base invia le `userName` e `password` valori per il server non crittografati. Chiunque monitoraggio del traffico di rete può visualizzare le credenziali e usarli per connettersi al server. È consigliabile usare un meccanismo di autenticazione più sicuro, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è `true`, Kerberos o NTLM da utilizzare se il server supporta questi protocolli.  
  
 La base predefinita rete credenziali opzioni di autenticazione e si escludono a vicenda; Se si imposta `defaultCredentials` a `true` e specificare un nome utente e password, viene utilizzata la credenziale di rete predefinito e i dati di autenticazione di base viene ignorati.  
  
 Per l'autenticazione di base se si specifica un `userName`, è necessario specificare anche un `password` all'autenticazione di se stessi al server di posta.  
  
 Il <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `userName` attributo dal file di configurazione applicabili. Il <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `password` attributo dal file di configurazione applicabili. Oggetto `password` attributo non sarebbe in genere essere immesso nel file di configurazione per motivi di sicurezza.  
  
 Il `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta iniziale di protocollo SMTP a un server SMTP. Il `clientDomain` attributo può essere impostato per il nome di dominio completo del computer locale, anziché il nome di localhost viene usato per impostazione predefinita. Questo fornisce maggiore conformità agli standard del protocollo SMTP. Il valore predefinito è il nome host locale del computer locale l'invio della richiesta. Il <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `clientDomain` attributo dal file di configurazione applicabili.  
  
 Il `targetName` viene usato per l'autenticazione quando si usa la protezione estesa. Il valore predefinito è nel formato "SMTPSVC /\<host >" dove \<host > è il nome host del server di posta SMTP. Il <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `targetName` attributo dal file di configurazione applicabili.  
  
 Il `enableSsl` attributo specifica se SSL viene utilizzato per accedere a un server di posta SMTP. Il <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per il protocollo SMTP protetto tramite Transport Layer Security come definito in RFC 3207. In questa modalità, la sessione SMTP inizia in un canale non crittografato, quindi viene eseguito un comando STARTTLS dal client al server per passare alla comunicazione sicura tramite SSL. 3207 RFC pubblicate dalla Internet Engineering Task Force (IETF) per altre informazioni, vedere.  
  
 Un metodo alternativo di connessione è in una sessione SSL viene stabilita fin dall'inizio prima di qualsiasi protocollo i comandi vengono inviati. Questo metodo di connessione, talvolta chiamato SMTPS, per impostazione predefinita Usa la porta 465. Questo metodo alternativo di connessione mediante SSL non è attualmente supportato.  
  
 Il <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `enableSsl` attributo dal file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
