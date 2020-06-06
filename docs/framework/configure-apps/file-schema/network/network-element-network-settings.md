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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154816"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="f8145-102">Elemento \<network> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f8145-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="f8145-103">Configura le opzioni di rete per un server SMTP (Simple Mail Transport Protocol) esterno.</span><span class="sxs-lookup"><span data-stu-id="f8145-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="f8145-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8145-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f8145-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="f8145-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f8145-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="f8145-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f8145-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="f8145-107">Attributes</span></span>  
  
|<span data-ttu-id="f8145-108">Attributo</span><span class="sxs-lookup"><span data-stu-id="f8145-108">Attribute</span></span>|<span data-ttu-id="f8145-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8145-109">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="f8145-110">Specifica il nome di dominio client da utilizzare nella richiesta di protocollo SMTP iniziale per la connessione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-110">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="f8145-111">Il valore predefinito è il nome localhost del computer locale che invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="f8145-111">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="f8145-112">Specifica se utilizzare le credenziali utente predefinite per accedere al server di posta SMTP per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-112">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="f8145-113">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f8145-113">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="f8145-114">Specifica se viene utilizzato SSL per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-114">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="f8145-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f8145-115">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="f8145-116">Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-116">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="f8145-117">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f8145-117">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="f8145-118">Specifica la password da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-118">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="f8145-119">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f8145-119">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="f8145-120">Specifica il numero di porta da utilizzare per la connessione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-120">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="f8145-121">Il valore predefinito è 25.</span><span class="sxs-lookup"><span data-stu-id="f8145-121">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="f8145-122">Specifica il nome del provider di servizi (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-122">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="f8145-123">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f8145-123">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="f8145-124">Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-124">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="f8145-125">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="f8145-125">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f8145-126">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="f8145-126">Child Elements</span></span>  
 <span data-ttu-id="f8145-127">No.</span><span class="sxs-lookup"><span data-stu-id="f8145-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f8145-128">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="f8145-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f8145-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="f8145-129">Element</span></span>|<span data-ttu-id="f8145-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8145-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f8145-131">\<smtp>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="f8145-131">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="f8145-132">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="f8145-132">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8145-133">Commenti</span><span class="sxs-lookup"><span data-stu-id="f8145-133">Remarks</span></span>  
 <span data-ttu-id="f8145-134">Per alcuni server SMTP è necessario eseguire l'autenticazione al server prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f8145-134">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="f8145-135">Se si desidera eseguire l'autenticazione utilizzando le credenziali di rete predefinite nell'host, impostare l' `defaultCredentials` attributo su `true` .</span><span class="sxs-lookup"><span data-stu-id="f8145-135">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="f8145-136"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `defaultCredentials` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f8145-136">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="f8145-137">È inoltre possibile utilizzare l'autenticazione di base (nome utente e password) per eseguire l'autenticazione al server SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-137">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="f8145-138">Per utilizzare questa opzione, è necessario specificare un nome utente e una password validi per il server SMTP specificato.</span><span class="sxs-lookup"><span data-stu-id="f8145-138">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8145-139">L'autenticazione di base invia i `userName` `password` valori e al server non crittografato.</span><span class="sxs-lookup"><span data-stu-id="f8145-139">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="f8145-140">Chiunque monitora il traffico di rete può visualizzare le credenziali e usarle per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="f8145-140">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="f8145-141">È consigliabile utilizzare un meccanismo di autenticazione più protetto, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è `true` , verrà utilizzato Kerberos o NTLM se il server supporta questi protocolli.</span><span class="sxs-lookup"><span data-stu-id="f8145-141">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="f8145-142">Le opzioni di autenticazione di base e credenziali di rete predefinite si escludono a vicenda. Se si imposta `defaultCredentials` su `true` e si specifica un nome utente e una password, vengono utilizzate le credenziali di rete predefinite e i dati di autenticazione di base vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="f8145-142">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="f8145-143">Per l'autenticazione di base se si specifica un `userName` , è necessario specificare anche per l' `password` autenticazione al server di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f8145-143">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="f8145-144"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `userName` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f8145-144">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="f8145-145"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `password` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f8145-145">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="f8145-146">Un `password` attributo normalmente non viene immesso nei file di configurazione per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f8145-146">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="f8145-147">L' `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta di protocollo SMTP iniziale a un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-147">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="f8145-148">L' `clientDomain` attributo può essere impostato sul nome di dominio completo del computer locale, anziché sul nome localhost usato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f8145-148">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="f8145-149">Questo garantisce una maggiore conformità con gli standard del protocollo SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-149">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="f8145-150">Il valore predefinito è il nome localhost del computer locale che invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="f8145-150">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="f8145-151"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `clientDomain` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f8145-151">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="f8145-152">L' `targetName` attributo viene utilizzato per l'autenticazione quando si utilizza la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="f8145-152">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="f8145-153">Il formato del valore predefinito è "SMTPSVC/ \<host> ", dove \<host> è il nome host del server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-153">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="f8145-154"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `targetName` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f8145-154">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="f8145-155">L' `enableSsl` attributo specifica se viene utilizzato SSL per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="f8145-155">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="f8145-156">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per Secure SMTP su Transport Layer Security come definito nella specifica RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="f8145-156">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="f8145-157">In questa modalità, la sessione SMTP inizia su un canale non crittografato, quindi un comando STARTTLS viene emesso dal client al server per passare alla comunicazione protetta tramite SSL.</span><span class="sxs-lookup"><span data-stu-id="f8145-157">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="f8145-158">Per ulteriori informazioni, vedere la RFC 3207 pubblicata da Internet Engineering Task Force (IETF).</span><span class="sxs-lookup"><span data-stu-id="f8145-158">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="f8145-159">Un metodo di connessione alternativo è il punto in cui viene stabilita una sessione SSL prima dell'invio di tutti i comandi del protocollo.</span><span class="sxs-lookup"><span data-stu-id="f8145-159">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="f8145-160">Questo metodo di connessione viene talvolta denominato SMTPs e per impostazione predefinita Usa la porta 465.</span><span class="sxs-lookup"><span data-stu-id="f8145-160">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="f8145-161">Questo metodo di connessione alternativo che usa SSL attualmente non è supportato.</span><span class="sxs-lookup"><span data-stu-id="f8145-161">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="f8145-162"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `enableSsl` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="f8145-162">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8145-163">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8145-163">Example</span></span>  
 <span data-ttu-id="f8145-164">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="f8145-164">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f8145-165">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f8145-165">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="f8145-166">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="f8145-166">Network Settings Schema</span></span>](index.md)
