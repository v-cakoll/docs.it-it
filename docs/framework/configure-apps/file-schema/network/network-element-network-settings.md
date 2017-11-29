---
title: '&lt;rete&gt; elemento (impostazioni di rete)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 679351fd2d6f0727d40bd57c9ef2016738462eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="8479f-102">&lt;rete&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8479f-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="8479f-103">Configura le opzioni di rete per un server SMTP Simple Mail Transport Protocol () esterno.</span><span class="sxs-lookup"><span data-stu-id="8479f-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="8479f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8479f-104">\<configuration></span></span>  
<span data-ttu-id="8479f-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="8479f-105">\<system.net></span></span>  
<span data-ttu-id="8479f-106">\<mailSettings ></span><span class="sxs-lookup"><span data-stu-id="8479f-106">\<mailSettings></span></span>  
<span data-ttu-id="8479f-107">\<SMTP ></span><span class="sxs-lookup"><span data-stu-id="8479f-107">\<smtp></span></span>  
<span data-ttu-id="8479f-108">\<rete ></span><span class="sxs-lookup"><span data-stu-id="8479f-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8479f-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8479f-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8479f-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="8479f-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8479f-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="8479f-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8479f-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="8479f-112">Attributes</span></span>  
  
|<span data-ttu-id="8479f-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="8479f-113">Attribute</span></span>|<span data-ttu-id="8479f-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8479f-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="8479f-115">Specifica il nome di dominio client da utilizzare nella richiesta iniziale di protocollo SMTP per la connessione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="8479f-116">Il valore predefinito è il nome host locale del computer locale, l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8479f-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="8479f-117">Specifica se le credenziali utente predefinite devono essere utilizzate per accedere al server di posta elettronica SMTP per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="8479f-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="8479f-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="8479f-119">Specifica se viene utilizzato SSL per accedere a un server di posta elettronica SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="8479f-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="8479f-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="8479f-121">Specifica il nome host del server di posta elettronica SMTP da utilizzare per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="8479f-122">Questo attributo non è previsto alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8479f-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="8479f-123">Specifica la password da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="8479f-124">Questo attributo non è previsto alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8479f-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="8479f-125">Specifica il numero di porta da utilizzare per connettersi al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="8479f-126">Il valore predefinito è 25.</span><span class="sxs-lookup"><span data-stu-id="8479f-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="8479f-127">Specifica il nome di Provider di servizio (SPN) da utilizzare per l'autenticazione quando si utilizza la protezione estesa per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="8479f-128">Questo attributo non è previsto alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8479f-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="8479f-129">Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="8479f-130">Questo attributo non è previsto alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="8479f-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8479f-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="8479f-131">Child Elements</span></span>  
 <span data-ttu-id="8479f-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="8479f-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8479f-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="8479f-133">Parent Elements</span></span>  
  
|<span data-ttu-id="8479f-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="8479f-134">Element</span></span>|<span data-ttu-id="8479f-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8479f-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8479f-136">\<SMTP > elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="8479f-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="8479f-137">Configura posta elettronica SMTP Simple Mail Transport Protocol (), le opzioni di invio.</span><span class="sxs-lookup"><span data-stu-id="8479f-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8479f-138">Note</span><span class="sxs-lookup"><span data-stu-id="8479f-138">Remarks</span></span>  
 <span data-ttu-id="8479f-139">Alcuni server SMTP richiedono autenticarsi al server prima dell'uso.</span><span class="sxs-lookup"><span data-stu-id="8479f-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="8479f-140">Se si desidera eseguire l'autenticazione utilizzando le credenziali di rete predefinite sull'host, impostare il `defaultCredentials` attributo `true`.</span><span class="sxs-lookup"><span data-stu-id="8479f-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="8479f-141">Il <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `defaultCredentials` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="8479f-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="8479f-142">È inoltre possibile utilizzare l'autenticazione di base (nome utente e password) per autenticarsi presso il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="8479f-143">Per utilizzare questa opzione, è necessario specificare un nome utente valido e una password per il server SMTP specificato.</span><span class="sxs-lookup"><span data-stu-id="8479f-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8479f-144">Autenticazione di base invia le `userName` e `password` i valori per il server non crittografato.</span><span class="sxs-lookup"><span data-stu-id="8479f-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="8479f-145">Chiunque monitoraggio del traffico di rete può visualizzare le credenziali e utilizzarle per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="8479f-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="8479f-146">È consigliabile utilizzare un meccanismo di autenticazione più sicuro, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è `true`, Kerberos o NTLM da utilizzare se il server supporta questi protocolli.</span><span class="sxs-lookup"><span data-stu-id="8479f-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="8479f-147">L'autenticazione e l'impostazione predefinita rete credenziali opzioni di base si escludono a vicenda; Se si imposta `defaultCredentials` a `true` e specificare un nome utente e una password, viene utilizzata la credenziale di rete predefinito e i dati di autenticazione di base viene ignorati.</span><span class="sxs-lookup"><span data-stu-id="8479f-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="8479f-148">L'autenticazione di base se si specifica un `userName`, è necessario specificare anche un `password` all'autenticazione per il server di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8479f-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="8479f-149">Il <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `userName` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="8479f-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="8479f-150">Il <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `password` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="8479f-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="8479f-151">Oggetto `password` attributo non verrebbe normalmente immesso nei file di configurazione per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8479f-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="8479f-152">Il `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta iniziale di protocollo SMTP a un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="8479f-153">Il `clientDomain` attributo può essere impostato per il nome di dominio completo del computer locale, anziché il nome host locale utilizzato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="8479f-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="8479f-154">Questo fornisce maggiore conformità agli standard del protocollo SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="8479f-155">Il valore predefinito è il nome host locale del computer locale, l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8479f-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="8479f-156">Il <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `clientDomain` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="8479f-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="8479f-157">Il `targetName` attributo viene utilizzato per l'autenticazione quando si utilizza la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="8479f-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="8479f-158">Il valore predefinito è nel formato "SMTPSVC /\<host >" dove \<host > è il nome host del server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="8479f-159">Il <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `targetName` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="8479f-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="8479f-160">Il `enableSsl` attributo specifica se viene utilizzato SSL per accedere a un server di posta elettronica SMTP.</span><span class="sxs-lookup"><span data-stu-id="8479f-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="8479f-161">La <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per il protocollo SMTP protetto su Transport Layer Security come definito in RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="8479f-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="8479f-162">In questa modalità, la sessione SMTP inizia in un canale non crittografato, quindi viene eseguito un comando STARTTLS dal client al server per passare alla comunicazione protetta con SSL.</span><span class="sxs-lookup"><span data-stu-id="8479f-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="8479f-163">Vedere RFC 3207 pubblicato da Internet Engineering Task Force (IETF) per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="8479f-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="8479f-164">Un metodo di connessione alternativo è in una sessione SSL viene stabilita in anticipo prima di qualsiasi protocollo di comandi vengono inviati.</span><span class="sxs-lookup"><span data-stu-id="8479f-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="8479f-165">Questo metodo di connessione, talvolta chiamato SMTPS, per impostazione predefinita utilizza la porta 465.</span><span class="sxs-lookup"><span data-stu-id="8479f-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="8479f-166">Questo metodo di connessione alternativo tramite SSL non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="8479f-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="8479f-167">Il <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> utilizzabile per ottenere il valore corrente della proprietà di `enableSsl` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="8479f-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8479f-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="8479f-168">Example</span></span>  
 <span data-ttu-id="8479f-169">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica utilizzando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="8479f-169">The following example specifies the appropriate SMTP parameters to send e-mail using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8479f-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8479f-170">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [<span data-ttu-id="8479f-171">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="8479f-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
