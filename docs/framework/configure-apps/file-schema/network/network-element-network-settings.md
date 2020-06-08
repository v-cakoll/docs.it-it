---
title: Elemento <network> (impostazioni di rete)
description: L' <network> elemento impostazioni di rete configura le opzioni di rete per le opzioni del server SMTP esterno nel .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 36857e63871b4672df349934594f0887a042609e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504550"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="72a49-103">Elemento \<network> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="72a49-103">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="72a49-104">Configura le opzioni di rete per un server SMTP (Simple Mail Transport Protocol) esterno.</span><span class="sxs-lookup"><span data-stu-id="72a49-104">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="72a49-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="72a49-105">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72a49-106">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="72a49-106">Attributes and Elements</span></span>  
 <span data-ttu-id="72a49-107">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="72a49-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72a49-108">Attributi</span><span class="sxs-lookup"><span data-stu-id="72a49-108">Attributes</span></span>  
  
|<span data-ttu-id="72a49-109">Attributo</span><span class="sxs-lookup"><span data-stu-id="72a49-109">Attribute</span></span>|<span data-ttu-id="72a49-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72a49-110">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="72a49-111">Specifica il nome di dominio client da utilizzare nella richiesta di protocollo SMTP iniziale per la connessione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-111">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="72a49-112">Il valore predefinito è il nome localhost del computer locale che invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="72a49-112">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="72a49-113">Specifica se utilizzare le credenziali utente predefinite per accedere al server di posta SMTP per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-113">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="72a49-114">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="72a49-114">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="72a49-115">Specifica se viene utilizzato SSL per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-115">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="72a49-116">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="72a49-116">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="72a49-117">Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-117">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="72a49-118">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="72a49-118">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="72a49-119">Specifica la password da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-119">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="72a49-120">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="72a49-120">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="72a49-121">Specifica il numero di porta da utilizzare per la connessione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-121">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="72a49-122">Il valore predefinito è 25.</span><span class="sxs-lookup"><span data-stu-id="72a49-122">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="72a49-123">Specifica il nome del provider di servizi (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-123">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="72a49-124">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="72a49-124">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="72a49-125">Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-125">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="72a49-126">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="72a49-126">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72a49-127">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="72a49-127">Child Elements</span></span>  
 <span data-ttu-id="72a49-128">No.</span><span class="sxs-lookup"><span data-stu-id="72a49-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72a49-129">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="72a49-129">Parent Elements</span></span>  
  
|<span data-ttu-id="72a49-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="72a49-130">Element</span></span>|<span data-ttu-id="72a49-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="72a49-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="72a49-132">\<smtp>Elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="72a49-132">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="72a49-133">Configura le opzioni di invio di posta elettronica SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="72a49-133">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72a49-134">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="72a49-134">Remarks</span></span>  
 <span data-ttu-id="72a49-135">Per alcuni server SMTP è necessario eseguire l'autenticazione al server prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="72a49-135">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="72a49-136">Se si desidera eseguire l'autenticazione utilizzando le credenziali di rete predefinite nell'host, impostare l' `defaultCredentials` attributo su `true` .</span><span class="sxs-lookup"><span data-stu-id="72a49-136">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="72a49-137"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `defaultCredentials` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="72a49-137">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="72a49-138">È inoltre possibile utilizzare l'autenticazione di base (nome utente e password) per eseguire l'autenticazione al server SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-138">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="72a49-139">Per utilizzare questa opzione, è necessario specificare un nome utente e una password validi per il server SMTP specificato.</span><span class="sxs-lookup"><span data-stu-id="72a49-139">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72a49-140">L'autenticazione di base invia i `userName` `password` valori e al server non crittografato.</span><span class="sxs-lookup"><span data-stu-id="72a49-140">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="72a49-141">Chiunque monitora il traffico di rete può visualizzare le credenziali e usarle per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="72a49-141">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="72a49-142">È consigliabile utilizzare un meccanismo di autenticazione più protetto, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è `true` , verrà utilizzato Kerberos o NTLM se il server supporta questi protocolli.</span><span class="sxs-lookup"><span data-stu-id="72a49-142">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="72a49-143">Le opzioni di autenticazione di base e credenziali di rete predefinite si escludono a vicenda. Se si imposta `defaultCredentials` su `true` e si specifica un nome utente e una password, vengono utilizzate le credenziali di rete predefinite e i dati di autenticazione di base vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="72a49-143">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="72a49-144">Per l'autenticazione di base se si specifica un `userName` , è necessario specificare anche per l' `password` autenticazione al server di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="72a49-144">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="72a49-145"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `userName` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="72a49-145">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="72a49-146"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `password` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="72a49-146">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="72a49-147">Un `password` attributo normalmente non viene immesso nei file di configurazione per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="72a49-147">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="72a49-148">L' `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta di protocollo SMTP iniziale a un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-148">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="72a49-149">L' `clientDomain` attributo può essere impostato sul nome di dominio completo del computer locale, anziché sul nome localhost usato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="72a49-149">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="72a49-150">Questo garantisce una maggiore conformità con gli standard del protocollo SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-150">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="72a49-151">Il valore predefinito è il nome localhost del computer locale che invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="72a49-151">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="72a49-152"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `clientDomain` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="72a49-152">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="72a49-153">L' `targetName` attributo viene utilizzato per l'autenticazione quando si utilizza la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="72a49-153">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="72a49-154">Il formato del valore predefinito è "SMTPSVC/ \<host> ", dove \<host> è il nome host del server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-154">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="72a49-155"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `targetName` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="72a49-155">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="72a49-156">L' `enableSsl` attributo specifica se viene utilizzato SSL per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="72a49-156">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="72a49-157">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per Secure SMTP su Transport Layer Security come definito nella specifica RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="72a49-157">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="72a49-158">In questa modalità, la sessione SMTP inizia su un canale non crittografato, quindi un comando STARTTLS viene emesso dal client al server per passare alla comunicazione protetta tramite SSL.</span><span class="sxs-lookup"><span data-stu-id="72a49-158">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="72a49-159">Per ulteriori informazioni, vedere la RFC 3207 pubblicata da Internet Engineering Task Force (IETF).</span><span class="sxs-lookup"><span data-stu-id="72a49-159">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="72a49-160">Un metodo di connessione alternativo è il punto in cui viene stabilita una sessione SSL prima dell'invio di tutti i comandi del protocollo.</span><span class="sxs-lookup"><span data-stu-id="72a49-160">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="72a49-161">Questo metodo di connessione viene talvolta denominato SMTPs e per impostazione predefinita Usa la porta 465.</span><span class="sxs-lookup"><span data-stu-id="72a49-161">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="72a49-162">Questo metodo di connessione alternativo che usa SSL attualmente non è supportato.</span><span class="sxs-lookup"><span data-stu-id="72a49-162">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="72a49-163"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `enableSsl` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="72a49-163">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72a49-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="72a49-164">Example</span></span>  
 <span data-ttu-id="72a49-165">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="72a49-165">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="72a49-166">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72a49-166">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="72a49-167">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="72a49-167">Network Settings Schema</span></span>](index.md)
