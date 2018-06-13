---
title: '&lt;rete&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e53d39f15a01f751a93c5531b3079d77bf0040e4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744668"
---
# <a name="ltnetworkgt-element-network-settings"></a>&lt;rete&gt; elemento (impostazioni di rete)
Configura le opzioni di rete per un server SMTP Simple Mail Transport Protocol () esterno.  
  
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
|`clientDomain`|Specifica il nome di dominio client da utilizzare nella richiesta iniziale di protocollo SMTP per la connessione al server di posta SMTP. Il valore predefinito è il nome host locale del computer locale, l'invio della richiesta.|  
|`defaultCredentials`|Specifica se le credenziali utente predefinite devono essere utilizzate per accedere al server di posta elettronica SMTP per le transazioni SMTP. Il valore predefinito è `false`.|  
|`enableSsl`|Specifica se viene utilizzato SSL per accedere a un server di posta elettronica SMTP. Il valore predefinito è `false`.|  
|`host`|Specifica il nome host del server di posta elettronica SMTP da utilizzare per le transazioni SMTP. Questo attributo non è previsto alcun valore predefinito.|  
|`password`|Specifica la password da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non è previsto alcun valore predefinito.|  
|`port`|Specifica il numero di porta da utilizzare per connettersi al server di posta SMTP. Il valore predefinito è 25.|  
|`targetName`|Specifica il nome di Provider di servizio (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP. Questo attributo non è previsto alcun valore predefinito.|  
|`userName`|Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non è previsto alcun valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<SMTP > elemento (impostazioni di rete)](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|Configura posta elettronica SMTP Simple Mail Transport Protocol (), le opzioni di invio.|  
  
## <a name="remarks"></a>Note  
 Alcuni server SMTP richiedono autenticarsi al server prima dell'uso. Se si desidera eseguire l'autenticazione utilizzando le credenziali di rete predefinite sull'host, impostare il `defaultCredentials` attributo `true`. Il <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `defaultCredentials` attributo dal file di configurazione applicabili.  
  
 È inoltre possibile utilizzare l'autenticazione di base (nome utente e password) per autenticarsi presso il server SMTP. Per utilizzare questa opzione, è necessario specificare un nome utente valido e una password per il server SMTP specificato.  
  
> [!NOTE]
>  Autenticazione di base invia le `userName` e `password` i valori per il server non crittografato. Chiunque monitoraggio del traffico di rete può visualizzare le credenziali e utilizzarle per connettersi al server. È consigliabile utilizzare un meccanismo di autenticazione più sicuro, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è `true`, Kerberos o NTLM da utilizzare se il server supporta questi protocolli.  
  
 L'autenticazione e l'impostazione predefinita rete credenziali opzioni di base si escludono a vicenda; Se si imposta `defaultCredentials` a `true` e specificare un nome utente e una password, viene utilizzata la credenziale di rete predefinito e i dati di autenticazione di base viene ignorati.  
  
 L'autenticazione di base se si specifica un `userName`, è necessario specificare anche un `password` all'autenticazione per il server di posta elettronica.  
  
 Il <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `userName` attributo dal file di configurazione applicabili. Il <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `password` attributo dal file di configurazione applicabili. Oggetto `password` attributo non verrebbe normalmente immesso nei file di configurazione per motivi di sicurezza.  
  
 Il `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta iniziale di protocollo SMTP a un server SMTP. Il `clientDomain` attributo può essere impostato per il nome di dominio completo del computer locale, anziché il nome host locale utilizzato per impostazione predefinita. Questo fornisce maggiore conformità agli standard del protocollo SMTP. Il valore predefinito è il nome host locale del computer locale, l'invio della richiesta. Il <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `clientDomain` attributo dal file di configurazione applicabili.  
  
 Il `targetName` attributo viene utilizzato per l'autenticazione quando si utilizza la protezione estesa. Il valore predefinito è nel formato "SMTPSVC /\<host >" dove \<host > è il nome host del server di posta SMTP. Il <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `targetName` attributo dal file di configurazione applicabili.  
  
 Il `enableSsl` attributo specifica se viene utilizzato SSL per accedere a un server di posta elettronica SMTP. La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per il protocollo SMTP protetto su Transport Layer Security come definito in RFC 3207. In questa modalità, la sessione SMTP inizia in un canale non crittografato, quindi viene eseguito un comando STARTTLS dal client al server per passare alla comunicazione protetta con SSL. Vedere RFC 3207 pubblicato da Internet Engineering Task Force (IETF) per ulteriori informazioni.  
  
 Un metodo di connessione alternativo è in una sessione SSL viene stabilita in anticipo prima di qualsiasi protocollo di comandi vengono inviati. Questo metodo di connessione, talvolta chiamato SMTPS, per impostazione predefinita utilizza la porta 465. Questo metodo di connessione alternativo tramite SSL non è attualmente supportato.  
  
 Il <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `enableSsl` attributo dal file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="network">  
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
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [Schema delle impostazioni di rete](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
