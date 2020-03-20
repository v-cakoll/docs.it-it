---
title: Elemento <network> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: f7cfcc3b9d5a717c23175cd15aa48ae97c828e57
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154816"
---
# <a name="network-element-network-settings"></a>\<network> Element (Impostazioni di rete)
Configura le opzioni di rete per un server SMTP (Simple Mail Transport Protocol) esterno.  

[**\<>di configurazione**](../configuration-element.md)\
&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<>mailSettings**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>smtp**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di rete**

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
  
### <a name="attributes"></a>Attributes  
  
|Attributo|Descrizione|  
|---------------|-----------------|  
|`clientDomain`|Specifica il nome di dominio client da utilizzare nella richiesta iniziale del protocollo SMTP per la connessione al server di posta SMTP. Il valore predefinito è il nome localhost del computer locale che invia la richiesta.|  
|`defaultCredentials`|Specifica se le credenziali utente predefinite devono essere utilizzate per accedere al server di posta SMTP per le transazioni SMTP. Il valore predefinito è `false`.|  
|`enableSsl`|Specifica se viene utilizzato SSL per accedere a un server di posta SMTP. Il valore predefinito è `false`.|  
|`host`|Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP. Questo attributo non ha un valore predefinito.|  
|`password`|Specifica la password da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non ha un valore predefinito.|  
|`port`|Specifica il numero di porta da utilizzare per connettersi al server di posta SMTP. Il valore predefinito è 25.|  
|`targetName`|Specifica il nome del provider di servizi (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP. Questo attributo non ha un valore predefinito.|  
|`userName`|Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non ha un valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 No.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|Descrizione|  
|-------------|-----------------|  
|[\<Elemento> smtp (impostazioni di rete)](smtp-element-network-settings.md)|Configura le opzioni di invio della posta SMTP (Simple Mail Transport Protocol).|  
  
## <a name="remarks"></a>Osservazioni  
 Alcuni server SMTP richiedono l'autenticazione al server prima dell'utilizzo. Se si desidera autenticarsi utilizzando le credenziali di rete `defaultCredentials` predefinite `true`nell'host, impostare l'attributo su . La <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `defaultCredentials` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.  
  
 È inoltre possibile utilizzare l'autenticazione di base (un nome utente e una password) per autenticarsi al server SMTP. Per utilizzare questa opzione, è necessario specificare un nome utente e una password validi per il server SMTP specificato.  
  
> [!NOTE]
> L'autenticazione `userName` `password` di base invia i valori e al server non crittografati. Chiunque monitori il traffico di rete può visualizzare le tue credenziali e usarle per connettersi al server. È consigliabile utilizzare un meccanismo di autenticazione più sicuro, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` `true`è , verrà utilizzato Kerberos o NTLM se il server supporta questi protocolli.  
  
 Le opzioni di autenticazione di base e credenziali di rete predefinite si escludono a vicenda; se si `defaultCredentials` `true` imposta su e si specifica un nome utente e una password, vengono utilizzate le credenziali di rete predefinite e i dati di autenticazione di base vengono ignorati.  
  
 Per l'autenticazione `userName`di base se `password` si specifica un , è inoltre necessario specificare un per l'autenticazione al server di posta.  
  
 La <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `userName` ottenere il valore corrente dell'attributo dai file di configurazione applicabili. La <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `password` ottenere il valore corrente dell'attributo dai file di configurazione applicabili. Un `password` attributo normalmente non verrebbe immesso nei file di configurazione per motivi di sicurezza.  
  
 L'attributo `clientDomain` modifica il nome di dominio client utilizzato nella richiesta iniziale del protocollo SMTP in un server SMTP. L'attributo `clientDomain` può essere impostato sul nome di dominio completo del computer locale, anziché sul nome localhost utilizzato per impostazione predefinita. Ciò garantisce una maggiore conformità agli standard del protocollo SMTP. Il valore predefinito è il nome localhost del computer locale che invia la richiesta. La <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `clientDomain` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.  
  
 L'attributo `targetName` viene utilizzato per l'autenticazione quando si utilizza la protezione estesa. Il valore predefinito è nel formato\<"SMTPSVC/ host>" dove \<host> è il nome host del server di posta SMTP. La <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `targetName` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.  
  
 L'attributo `enableSsl` specifica se SSL viene utilizzato per accedere a un server di posta SMTP. La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per Secure SMTP over Transport Layer Security, come definito in RFC 3207. In questa modalità, la sessione SMTP inizia su un canale non crittografato, quindi un comando STARTTLS viene emesso dal client al server per passare a proteggere la comunicazione tramite SSL. Vedere RFC 3207 pubblicato dalla Internet Engineering Task Force (IETF) per ulteriori informazioni.  
  
 Un metodo di connessione alternativo è il punto in cui viene stabilita in anticipo una sessione SSL prima dell'invio di qualsiasi comando di protocollo. Questo metodo di connessione viene talvolta chiamato SMTPS e per impostazione predefinita utilizza la porta 465. Questo metodo di connessione alternativo tramite SSL non è attualmente supportato.  
  
 La <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `enableSsl` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.  
  
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
- [Schema delle impostazioni di rete](index.md)
