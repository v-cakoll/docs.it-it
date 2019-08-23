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
ms.openlocfilehash: ee60b990bc749dbb9c5d0e7426c57e9392ddf9d4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920979"
---
# <a name="network-element-network-settings"></a>\<Elemento > di rete (impostazioni di rete)
Configura le opzioni di rete per un server SMTP (Simple Mail Transport Protocol) esterno.  
  
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
|`clientDomain`|Specifica il nome di dominio client da utilizzare nella richiesta di protocollo SMTP iniziale per la connessione al server di posta SMTP. Il valore predefinito è il nome localhost del computer locale che invia la richiesta.|  
|`defaultCredentials`|Specifica se utilizzare le credenziali utente predefinite per accedere al server di posta SMTP per le transazioni SMTP. Il valore predefinito è `false`.|  
|`enableSsl`|Specifica se viene utilizzato SSL per accedere a un server di posta SMTP. Il valore predefinito è `false`.|  
|`host`|Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP. Questo attributo non ha alcun valore predefinito.|  
|`password`|Specifica la password da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non ha alcun valore predefinito.|  
|`port`|Specifica il numero di porta da utilizzare per la connessione al server di posta SMTP. Il valore predefinito è 25.|  
|`targetName`|Specifica il nome del provider di servizi (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP. Questo attributo non ha alcun valore predefinito.|  
|`userName`|Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP. Questo attributo non ha alcun valore predefinito.|  
  
### <a name="child-elements"></a>Elementi figlio  
 Nessuno.  
  
### <a name="parent-elements"></a>Elementi padre  
  
|Elemento|DESCRIZIONE|  
|-------------|-----------------|  
|[\<Elemento > SMTP (impostazioni di rete)](smtp-element-network-settings.md)|Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).|  
  
## <a name="remarks"></a>Note  
 Per alcuni server SMTP è necessario eseguire l'autenticazione al server prima dell'utilizzo. Se si desidera eseguire l'autenticazione utilizzando le credenziali di rete predefinite nell'host, impostare l' `defaultCredentials` attributo su. `true` È <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente `defaultCredentials` dell'attributo dai file di configurazione applicabili.  
  
 È inoltre possibile utilizzare l'autenticazione di base (nome utente e password) per eseguire l'autenticazione al server SMTP. Per utilizzare questa opzione, è necessario specificare un nome utente e una password validi per il server SMTP specificato.  
  
> [!NOTE]
> L'autenticazione di base `userName` Invia `password` i valori e al server non crittografato. Chiunque monitora il traffico di rete può visualizzare le credenziali e usarle per connettersi al server. È consigliabile utilizzare un meccanismo di autenticazione più protetto, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è`true`, verrà utilizzato Kerberos o NTLM se il server supporta questi protocolli.  
  
 Le opzioni di autenticazione di base e credenziali di rete predefinite si escludono a vicenda. Se si imposta `defaultCredentials` su `true` e si specifica un nome utente e una password, vengono utilizzate le credenziali di rete predefinite e i dati di autenticazione di base vengono ignorati.  
  
 Per l'autenticazione di base se si `userName`specifica un, è necessario `password` specificare anche per l'autenticazione al server di posta elettronica.  
  
 È <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente `userName` dell'attributo dai file di configurazione applicabili. È <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente `password` dell'attributo dai file di configurazione applicabili. Un `password` attributo normalmente non viene immesso nei file di configurazione per motivi di sicurezza.  
  
 L' `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta di protocollo SMTP iniziale a un server SMTP. L' `clientDomain` attributo può essere impostato sul nome di dominio completo del computer locale, anziché sul nome localhost usato per impostazione predefinita. Questo garantisce una maggiore conformità con gli standard del protocollo SMTP. Il valore predefinito è il nome localhost del computer locale che invia la richiesta. È <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente `clientDomain` dell'attributo dai file di configurazione applicabili.  
  
 L' `targetName` attributo viene utilizzato per l'autenticazione quando si utilizza la protezione estesa. Il formato del valore predefinito è "SMTPSVC/\<host >", dove \<host > è il nome host del server di posta SMTP. È <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente `targetName` dell'attributo dai file di configurazione applicabili.  
  
 L' `enableSsl` attributo specifica se viene utilizzato SSL per accedere a un server di posta SMTP. La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per Secure SMTP su Transport Layer Security come definito nella specifica RFC 3207. In questa modalità, la sessione SMTP inizia su un canale non crittografato, quindi un comando STARTTLS viene emesso dal client al server per passare alla comunicazione protetta tramite SSL. Per ulteriori informazioni, vedere la RFC 3207 pubblicata da Internet Engineering Task Force (IETF).  
  
 Un metodo di connessione alternativo è il punto in cui viene stabilita una sessione SSL prima dell'invio di tutti i comandi del protocollo. Questo metodo di connessione viene talvolta denominato SMTPs e per impostazione predefinita Usa la porta 465. Questo metodo di connessione alternativo che usa SSL attualmente non è supportato.  
  
 È <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> possibile utilizzare la proprietà per ottenere il valore corrente `enableSsl` dell'attributo dai file di configurazione applicabili.  
  
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
