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
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 96a6c8a3c2d7114004278d3c40daf4d01b6c1d90
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47170022"
---
# <a name="ltnetworkgt-element-network-settings"></a><span data-ttu-id="7d4bc-102">&lt;rete&gt; (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-102">&lt;network&gt; Element (Network Settings)</span></span>
<span data-ttu-id="7d4bc-103">Consente di configurare le opzioni di rete per un server SMTP Simple Mail Transport Protocol () esterno.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="7d4bc-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7d4bc-104">\<configuration></span></span>  
<span data-ttu-id="7d4bc-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7d4bc-105">\<system.net></span></span>  
<span data-ttu-id="7d4bc-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="7d4bc-106">\<mailSettings></span></span>  
<span data-ttu-id="7d4bc-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="7d4bc-107">\<smtp></span></span>  
<span data-ttu-id="7d4bc-108">\<network></span><span class="sxs-lookup"><span data-stu-id="7d4bc-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d4bc-109">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7d4bc-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7d4bc-110">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="7d4bc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7d4bc-111">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7d4bc-112">Attributi</span><span class="sxs-lookup"><span data-stu-id="7d4bc-112">Attributes</span></span>  
  
|<span data-ttu-id="7d4bc-113">Attributo</span><span class="sxs-lookup"><span data-stu-id="7d4bc-113">Attribute</span></span>|<span data-ttu-id="7d4bc-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d4bc-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="7d4bc-115">Specifica il nome di dominio client da usare nella richiesta iniziale di protocollo SMTP per connettersi al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="7d4bc-116">Il valore predefinito è il nome host locale del computer locale l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="7d4bc-117">Specifica se le credenziali dell'utente predefinito devono essere utilizzate per accedere al server di posta elettronica SMTP per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="7d4bc-118">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="7d4bc-119">Specifica se SSL viene utilizzato per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="7d4bc-120">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="7d4bc-121">Specifica il nome host del server di posta SMTP da utilizzare per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="7d4bc-122">Questo attributo non ha alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="7d4bc-123">Specifica la password da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="7d4bc-124">Questo attributo non ha alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="7d4bc-125">Specifica il numero di porta da usare per connettersi al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="7d4bc-126">Il valore predefinito è 25.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="7d4bc-127">Specifica il nome di Provider di servizio (SPN) da usare per l'autenticazione quando si usa la protezione estesa per le transazioni SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="7d4bc-128">Questo attributo non ha alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="7d4bc-129">Specifica il nome utente da utilizzare per l'autenticazione al server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="7d4bc-130">Questo attributo non ha alcun valore predefinito.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7d4bc-131">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="7d4bc-131">Child Elements</span></span>  
 <span data-ttu-id="7d4bc-132">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7d4bc-133">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="7d4bc-133">Parent Elements</span></span>  
  
|<span data-ttu-id="7d4bc-134">Elemento</span><span class="sxs-lookup"><span data-stu-id="7d4bc-134">Element</span></span>|<span data-ttu-id="7d4bc-135">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d4bc-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7d4bc-136">\<SMTP > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7d4bc-136">\<smtp> Element (Network Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/smtp-element-network-settings.md)|<span data-ttu-id="7d4bc-137">Consente di configurare le opzioni di invio della posta elettronica SMTP Simple Mail Transport Protocol ().</span><span class="sxs-lookup"><span data-stu-id="7d4bc-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7d4bc-138">Note</span><span class="sxs-lookup"><span data-stu-id="7d4bc-138">Remarks</span></span>  
 <span data-ttu-id="7d4bc-139">Alcuni server SMTP richiedono autenticarsi al server prima dell'uso.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="7d4bc-140">Se si desidera eseguire l'autenticazione manualmente usando le credenziali di rete predefinite nell'host, impostare il `defaultCredentials` dell'attributo `true`.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="7d4bc-141">Il <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `defaultCredentials` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="7d4bc-142">È anche possibile usare l'autenticazione di base (nome utente e password) per autenticarsi presso il server SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="7d4bc-143">Per usare questa opzione, è necessario specificare un nome utente valido e una password per il server SMTP specificato.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7d4bc-144">L'autenticazione di base invia le `userName` e `password` valori per il server non crittografati.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="7d4bc-145">Chiunque monitoraggio del traffico di rete può visualizzare le credenziali e usarli per connettersi al server.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="7d4bc-146">È consigliabile usare un meccanismo di autenticazione più sicuro, ad esempio Kerberos o NT LAN Manager (NTLM). Se `defaultCredentials` è `true`, Kerberos o NTLM da utilizzare se il server supporta questi protocolli.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="7d4bc-147">La base predefinita rete credenziali opzioni di autenticazione e si escludono a vicenda; Se si imposta `defaultCredentials` a `true` e specificare un nome utente e password, viene utilizzata la credenziale di rete predefinito e i dati di autenticazione di base viene ignorati.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="7d4bc-148">Per l'autenticazione di base se si specifica un `userName`, è necessario specificare anche un `password` all'autenticazione di se stessi al server di posta.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="7d4bc-149">Il <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `userName` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="7d4bc-150">Il <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `password` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="7d4bc-151">Oggetto `password` attributo non sarebbe in genere essere immesso nel file di configurazione per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="7d4bc-152">Il `clientDomain` attributo modifica il nome di dominio client utilizzato nella richiesta iniziale di protocollo SMTP a un server SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="7d4bc-153">Il `clientDomain` attributo può essere impostato per il nome di dominio completo del computer locale, anziché il nome di localhost viene usato per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="7d4bc-154">Questo fornisce maggiore conformità agli standard del protocollo SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="7d4bc-155">Il valore predefinito è il nome host locale del computer locale l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="7d4bc-156">Il <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `clientDomain` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="7d4bc-157">Il `targetName` viene usato per l'autenticazione quando si usa la protezione estesa.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="7d4bc-158">Il valore predefinito è nel formato "SMTPSVC /\<host >" dove \<host > è il nome host del server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="7d4bc-159">Il <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `targetName` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="7d4bc-160">Il `enableSsl` attributo specifica se SSL viene utilizzato per accedere a un server di posta SMTP.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="7d4bc-161">Il <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> classe supporta solo l'estensione del servizio SMTP per il protocollo SMTP protetto tramite Transport Layer Security come definito in RFC 3207.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="7d4bc-162">In questa modalità, la sessione SMTP inizia in un canale non crittografato, quindi viene eseguito un comando STARTTLS dal client al server per passare alla comunicazione sicura tramite SSL.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="7d4bc-163">3207 RFC pubblicate dalla Internet Engineering Task Force (IETF) per altre informazioni, vedere.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="7d4bc-164">Un metodo alternativo di connessione è in una sessione SSL viene stabilita fin dall'inizio prima di qualsiasi protocollo i comandi vengono inviati.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="7d4bc-165">Questo metodo di connessione, talvolta chiamato SMTPS, per impostazione predefinita Usa la porta 465.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="7d4bc-166">Questo metodo alternativo di connessione mediante SSL non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="7d4bc-167">Il <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> proprietà può essere utilizzata per ottenere il valore corrente del `enableSsl` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d4bc-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d4bc-168">Example</span></span>  
 <span data-ttu-id="7d4bc-169">Nell'esempio seguente specifica i parametri appropriati di SMTP per inviare posta elettronica usando le credenziali di rete predefinite.</span><span class="sxs-lookup"><span data-stu-id="7d4bc-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7d4bc-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d4bc-170">See Also</span></span>  
 <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>  
 <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>  
 [<span data-ttu-id="7d4bc-171">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="7d4bc-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
