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
# <a name="network-element-network-settings"></a><span data-ttu-id="9e7cc-102">\<network> Element (Impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9e7cc-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="9e7cc-103">Configura le opzioni di rete per un server SMTP (Simple Mail Transport Protocol) esterno.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

<span data-ttu-id="9e7cc-104">[**\<>di configurazione**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9e7cc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9e7cc-105">&nbsp;&nbsp;[**\<>system.net**](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9e7cc-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>\
<span data-ttu-id="9e7cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<>mailSettings**](mailsettings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9e7cc-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)</span></span>\
<span data-ttu-id="9e7cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>smtp**](smtp-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="9e7cc-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)</span></span>\
<span data-ttu-id="9e7cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>di rete**</span><span class="sxs-lookup"><span data-stu-id="9e7cc-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9e7cc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9e7cc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e7cc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="9e7cc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9e7cc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e7cc-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="9e7cc-112">Attributes</span></span>  
  
|<span data-ttu-id="9e7cc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="9e7cc-113">Attribute</span></span>|<span data-ttu-id="9e7cc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e7cc-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="9e7cc-115">Specifica il nome di dominio client da utilizzare nella richiesta iniziale del protocollo SMTP per la connessione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="9e7cc-116">Il valore predefinito è il nome localhost del computer locale che invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="9e7cc-117">Specifica se le credenziali utente predefinite devono essere utilizzate per accedere al server di posta SMTP per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="9e7cc-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="9e7cc-119">Specifica se viene utilizzato SSL per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="9e7cc-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="9e7cc-121">Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="9e7cc-122">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="9e7cc-123">Specifica la password da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="9e7cc-124">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="9e7cc-125">Specifica il numero di porta da utilizzare per connettersi al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="9e7cc-126">Il valore predefinito è 25.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="9e7cc-127">Specifica il nome del provider di servizi (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="9e7cc-128">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="9e7cc-129">Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="9e7cc-130">Questo attributo non ha un valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e7cc-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="9e7cc-131">Child Elements</span></span>  
 <span data-ttu-id="9e7cc-132">No.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e7cc-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="9e7cc-133">Parent Elements</span></span>  
  
|<span data-ttu-id="9e7cc-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e7cc-134">Element</span></span>|<span data-ttu-id="9e7cc-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9e7cc-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e7cc-136">\<Elemento> smtp (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="9e7cc-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="9e7cc-137">Configura le opzioni di invio della posta SMTP (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="9e7cc-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e7cc-138">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="9e7cc-138">Remarks</span></span>  
 <span data-ttu-id="9e7cc-139">Alcuni server SMTP richiedono l'autenticazione al server prima dell'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="9e7cc-140">Se si desidera autenticarsi utilizzando le credenziali di rete `defaultCredentials` predefinite `true`nell'host, impostare l'attributo su .</span><span class="sxs-lookup"><span data-stu-id="9e7cc-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="9e7cc-141">La <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `defaultCredentials` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="9e7cc-142">È inoltre possibile utilizzare l'autenticazione di base (un nome utente e una password) per autenticarsi al server SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="9e7cc-143">Per utilizzare questa opzione, è necessario specificare un nome utente e una password validi per il server SMTP specificato.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e7cc-144">L'autenticazione `userName` `password` di base invia i valori e al server non crittografati.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="9e7cc-145">Chiunque monitori il traffico di rete può visualizzare le tue credenziali e usarle per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="9e7cc-146">È consigliabile utilizzare un meccanismo di autenticazione più sicuro, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` `true`è , verrà utilizzato Kerberos o NTLM se il server supporta questi protocolli.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="9e7cc-147">Le opzioni di autenticazione di base e credenziali di rete predefinite si escludono a vicenda; se si `defaultCredentials` `true` imposta su e si specifica un nome utente e una password, vengono utilizzate le credenziali di rete predefinite e i dati di autenticazione di base vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="9e7cc-148">Per l'autenticazione `userName`di base se `password` si specifica un , è inoltre necessario specificare un per l'autenticazione al server di posta.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="9e7cc-149">La <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `userName` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="9e7cc-150">La <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `password` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="9e7cc-151">Un `password` attributo normalmente non verrebbe immesso nei file di configurazione per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="9e7cc-152">L'attributo `clientDomain` modifica il nome di dominio client utilizzato nella richiesta iniziale del protocollo SMTP in un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="9e7cc-153">L'attributo `clientDomain` può essere impostato sul nome di dominio completo del computer locale, anziché sul nome localhost utilizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="9e7cc-154">Ciò garantisce una maggiore conformità agli standard del protocollo SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="9e7cc-155">Il valore predefinito è il nome localhost del computer locale che invia la richiesta.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="9e7cc-156">La <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `clientDomain` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="9e7cc-157">L'attributo `targetName` viene utilizzato per l'autenticazione quando si utilizza la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="9e7cc-158">Il valore predefinito è nel formato\<"SMTPSVC/ host>" dove \<host> è il nome host del server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="9e7cc-159">La <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `targetName` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="9e7cc-160">L'attributo `enableSsl` specifica se SSL viene utilizzato per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="9e7cc-161">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per Secure SMTP over Transport Layer Security, come definito in RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="9e7cc-162">In questa modalità, la sessione SMTP inizia su un canale non crittografato, quindi un comando STARTTLS viene emesso dal client al server per passare a proteggere la comunicazione tramite SSL.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="9e7cc-163">Vedere RFC 3207 pubblicato dalla Internet Engineering Task Force (IETF) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="9e7cc-164">Un metodo di connessione alternativo è il punto in cui viene stabilita in anticipo una sessione SSL prima dell'invio di qualsiasi comando di protocollo.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="9e7cc-165">Questo metodo di connessione viene talvolta chiamato SMTPS e per impostazione predefinita utilizza la porta 465.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="9e7cc-166">Questo metodo di connessione alternativo tramite SSL non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="9e7cc-167">La <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> proprietà può essere utilizzata per `enableSsl` ottenere il valore corrente dell'attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e7cc-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="9e7cc-168">Example</span></span>  
 <span data-ttu-id="9e7cc-169">Nell'esempio seguente vengono specificati i parametri SMTP appropriati per inviare messaggi di posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="9e7cc-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9e7cc-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9e7cc-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="9e7cc-171">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="9e7cc-171">Network Settings Schema</span></span>](index.md)
