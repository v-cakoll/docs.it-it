---
title: '&lt;socket&gt; elemento (impostazioni di rete)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 995a89dd67664fd6a408f88f20f6837d2dbaaad4
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744239"
---
# <a name="ltsocketgt-element-network-settings"></a><span data-ttu-id="e90fb-102">&lt;socket&gt; elemento (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="e90fb-102">&lt;socket&gt; Element (Network Settings)</span></span>
<span data-ttu-id="e90fb-103">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="e90fb-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="e90fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e90fb-104">\<configuration></span></span>  
<span data-ttu-id="e90fb-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="e90fb-105">\<system.net></span></span>  
<span data-ttu-id="e90fb-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="e90fb-106">\<settings></span></span>  
<span data-ttu-id="e90fb-107">\<socket ></span><span class="sxs-lookup"><span data-stu-id="e90fb-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e90fb-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e90fb-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e90fb-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="e90fb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e90fb-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="e90fb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e90fb-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="e90fb-111">Attributes</span></span>  
  
|<span data-ttu-id="e90fb-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="e90fb-112">**Attribute**</span></span>|<span data-ttu-id="e90fb-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e90fb-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="e90fb-114">Indica se il socket deve utilizzare sempre le porte di completamento per chiamate del metodo Accept.</span><span class="sxs-lookup"><span data-stu-id="e90fb-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="e90fb-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e90fb-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="e90fb-116">Indica se il socket deve utilizzare sempre le porte di completamento per chiamate ai metodi di connessione.</span><span class="sxs-lookup"><span data-stu-id="e90fb-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="e90fb-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e90fb-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="e90fb-118">Specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="e90fb-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="e90fb-119">Il valore predefinito dipende dalla versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e90fb-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e90fb-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="e90fb-120">Child Elements</span></span>  
 <span data-ttu-id="e90fb-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="e90fb-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e90fb-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="e90fb-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e90fb-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e90fb-123">**Element**</span></span>|<span data-ttu-id="e90fb-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e90fb-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e90fb-125">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="e90fb-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="e90fb-126">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="e90fb-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e90fb-127">Note</span><span class="sxs-lookup"><span data-stu-id="e90fb-127">Remarks</span></span>  
 <span data-ttu-id="e90fb-128">Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e90fb-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="e90fb-129">Le porte di completamento sono consigliate per le applicazioni server ad alte prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e90fb-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="e90fb-130">Il valore predefinito per il `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` attributi **false**.</span><span class="sxs-lookup"><span data-stu-id="e90fb-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="e90fb-131">Il <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> può essere utilizzato per ottenere il valore corrente del `alwaysUseCompletionPortsForAccept` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="e90fb-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="e90fb-132">Il <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> può essere utilizzato per ottenere il valore corrente del `alwaysUseCompletionPortsForConnect` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="e90fb-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="e90fb-133">Il `ipProtectionLevel` attributo specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="e90fb-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="e90fb-134">Il <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà consente la configurazione di una restrizione per un socket IPv6 a un ambito specificato, ad esempio gli indirizzi con lo stesso sito prefisso locale o al collegano.</span><span class="sxs-lookup"><span data-stu-id="e90fb-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="e90fb-135">Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6.</span><span class="sxs-lookup"><span data-stu-id="e90fb-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="e90fb-136">Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni.</span><span class="sxs-lookup"><span data-stu-id="e90fb-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="e90fb-137">Questa opzione allarga o restringe l'ambito di un socket in attesa, consentendo l'accesso illimitato di utenti pubblici e privati, laddove appropriato, o limitando l'accesso solo al medesimo sito, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="e90fb-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="e90fb-138">Questo `ipProtectionLevel` impostazione dell'attributo interessa solo il traffico in ingresso iniziale:</span><span class="sxs-lookup"><span data-stu-id="e90fb-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="e90fb-139">Un server TCP in ascolto delle connessioni in ingresso su un socket.</span><span class="sxs-lookup"><span data-stu-id="e90fb-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="e90fb-140">Ricezione di un pacchetto su un socket di un'applicazione di UDP.</span><span class="sxs-lookup"><span data-stu-id="e90fb-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="e90fb-141">Questa impostazione di configurazione non influisce sul già stabilite le connessioni TCP (traffico senza restrizioni in entrambe le direzioni) e non un'applicazione invia pacchetti UDP.</span><span class="sxs-lookup"><span data-stu-id="e90fb-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="e90fb-142">I valori possibili per il `ipProtectionLevel` impostazione dell'attributo corrispondono ai livelli di protezione definiti specificati nel <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumerazione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e90fb-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="e90fb-143">**Valore dell'attributo**</span><span class="sxs-lookup"><span data-stu-id="e90fb-143">**Attribute Value**</span></span>|<span data-ttu-id="e90fb-144">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="e90fb-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="e90fb-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="e90fb-145">EdgeRestricted</span></span>|<span data-ttu-id="e90fb-146">Il livello di protezione IP è limitato dal perimetro.</span><span class="sxs-lookup"><span data-stu-id="e90fb-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="e90fb-147">Questo valore verrà utilizzato dalle applicazioni progettate per funzionare in Internet.</span><span class="sxs-lookup"><span data-stu-id="e90fb-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="e90fb-148">Questa impostazione non consente l'attraversamento Network Address Translation (NAT) tramite l'implementazione di Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="e90fb-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="e90fb-149">Tali applicazioni possono aggirare i firewall IPv4, pertanto le applicazioni devono essere protette da attacchi Internet indirizzati alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="e90fb-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="e90fb-150">In Windows Server 2003 e Windows XP, il valore predefinito per il livello di protezione IP su un socket è limitato dal perimetro.</span><span class="sxs-lookup"><span data-stu-id="e90fb-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="e90fb-151">Con restrizioni</span><span class="sxs-lookup"><span data-stu-id="e90fb-151">Restricted</span></span>|<span data-ttu-id="e90fb-152">Il livello di protezione IP è limitato.</span><span class="sxs-lookup"><span data-stu-id="e90fb-152">The IP protection level is restricted.</span></span> <span data-ttu-id="e90fb-153">Questo valore verrà utilizzato dalle applicazioni intranet che non implementano scenari Internet.</span><span class="sxs-lookup"><span data-stu-id="e90fb-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="e90fb-154">Queste applicazioni non sono in genere eseguito il test o avanzate contro gli attacchi di tipo Internet.</span><span class="sxs-lookup"><span data-stu-id="e90fb-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="e90fb-155">Questa impostazione limiterà il traffico ricevuto solo link-local.</span><span class="sxs-lookup"><span data-stu-id="e90fb-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="e90fb-156">Senza restrizioni</span><span class="sxs-lookup"><span data-stu-id="e90fb-156">Unrestricted</span></span>|<span data-ttu-id="e90fb-157">Il livello di protezione IP è senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="e90fb-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="e90fb-158">Questo valore verrà utilizzato dalle applicazioni progettate per funzionare in Internet, incluse le applicazioni che sfruttano le funzionalità di attraversamento NAT IPv6 integrate in Windows (ad esempio, Teredo).</span><span class="sxs-lookup"><span data-stu-id="e90fb-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="e90fb-159">Tali applicazioni possono aggirare i firewall IPv4, pertanto le applicazioni devono essere protette da attacchi Internet indirizzati alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="e90fb-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="e90fb-160">In Windows Server 2008 R2 e Windows Vista, il valore predefinito per il livello di protezione IP su un socket è senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="e90fb-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="e90fb-161">Non specificato</span><span class="sxs-lookup"><span data-stu-id="e90fb-161">Unspecified</span></span>|<span data-ttu-id="e90fb-162">Il livello di protezione IP non è specificato.</span><span class="sxs-lookup"><span data-stu-id="e90fb-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="e90fb-163">In Windows 7 e Windows Server 2008 R2, il valore predefinito per il livello di protezione IP su un socket non è specificato.</span><span class="sxs-lookup"><span data-stu-id="e90fb-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="e90fb-164">Il valore predefinito per il `ipProtectionLevel` attributo **Unspecified**.</span><span class="sxs-lookup"><span data-stu-id="e90fb-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="e90fb-165">Il <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> utilizzabile per ottenere il valore corrente della proprietà di `ipProtectionLevel` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="e90fb-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e90fb-166">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="e90fb-166">Configuration Files</span></span>  
 <span data-ttu-id="e90fb-167">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="e90fb-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e90fb-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="e90fb-168">Example</span></span>  
 <span data-ttu-id="e90fb-169">Nell'esempio seguente viene illustrato come specificare che le porte di completamento devono essere utilizzate e che il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> deve essere senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="e90fb-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e90fb-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e90fb-170">See Also</span></span>  
 <xref:System.Net?displayProperty=nameWithType>  
 <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>  
 <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>  
 [<span data-ttu-id="e90fb-171">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="e90fb-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
