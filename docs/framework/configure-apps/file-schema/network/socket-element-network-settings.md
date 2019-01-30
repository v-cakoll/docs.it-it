---
title: Elemento <socket> (Impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 3f599d6ada288db861f69fc64e6b84ee326b5830
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55256894"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="05247-102">\<socket > (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="05247-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="05247-103">Specifica se le operazioni socket usano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="05247-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="05247-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="05247-104">\<configuration></span></span>  
<span data-ttu-id="05247-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="05247-105">\<system.net></span></span>  
<span data-ttu-id="05247-106">\<Impostazioni ></span><span class="sxs-lookup"><span data-stu-id="05247-106">\<settings></span></span>  
<span data-ttu-id="05247-107">\<socket></span><span class="sxs-lookup"><span data-stu-id="05247-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05247-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05247-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05247-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="05247-109">Attributes and Elements</span></span>  
 <span data-ttu-id="05247-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="05247-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05247-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="05247-111">Attributes</span></span>  
  
|<span data-ttu-id="05247-112">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="05247-112">**Attribute**</span></span>|<span data-ttu-id="05247-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="05247-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="05247-114">Indica se il socket deve utilizzare sempre le porte di completamento delle chiamate al metodo Accept.</span><span class="sxs-lookup"><span data-stu-id="05247-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="05247-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="05247-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="05247-116">Indica se il socket deve utilizzare sempre le porte di completamento delle chiamate al metodo Connect.</span><span class="sxs-lookup"><span data-stu-id="05247-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="05247-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="05247-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="05247-118">Specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="05247-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="05247-119">Il valore predefinito dipende dalla versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="05247-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05247-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="05247-120">Child Elements</span></span>  
 <span data-ttu-id="05247-121">Nessuno.</span><span class="sxs-lookup"><span data-stu-id="05247-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05247-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="05247-122">Parent Elements</span></span>  
  
|<span data-ttu-id="05247-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="05247-123">**Element**</span></span>|<span data-ttu-id="05247-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="05247-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="05247-125">settings</span><span class="sxs-lookup"><span data-stu-id="05247-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="05247-126">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="05247-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05247-127">Note</span><span class="sxs-lookup"><span data-stu-id="05247-127">Remarks</span></span>  
 <span data-ttu-id="05247-128">Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="05247-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="05247-129">Le porte di completamento sono consigliate per le applicazioni server ad alte prestazioni.</span><span class="sxs-lookup"><span data-stu-id="05247-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="05247-130">Il valore predefinito per il `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` attributi viene **false**.</span><span class="sxs-lookup"><span data-stu-id="05247-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="05247-131">Il <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> può essere utilizzato per ottenere il valore corrente del `alwaysUseCompletionPortsForAccept` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="05247-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="05247-132">Il <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> può essere utilizzato per ottenere il valore corrente del `alwaysUseCompletionPortsForConnect` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="05247-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="05247-133">Il `ipProtectionLevel` attributo specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="05247-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="05247-134">Il <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà consente la configurazione di una restrizione per un socket IPv6 in un ambito specificato, ad esempio indirizzi con lo stesso prefisso locale del sito o al collegano.</span><span class="sxs-lookup"><span data-stu-id="05247-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="05247-135">Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6.</span><span class="sxs-lookup"><span data-stu-id="05247-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="05247-136">Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni.</span><span class="sxs-lookup"><span data-stu-id="05247-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="05247-137">Questa opzione allarga o restringe l'ambito di un socket di ascolto, consentendo l'accesso illimitato di utenti pubblici e privati, laddove appropriato, o limitando l'accesso solo allo stesso sito, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="05247-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="05247-138">Ciò `ipProtectionLevel` impostazione dell'attributo interessa solo il traffico in ingresso iniziale:</span><span class="sxs-lookup"><span data-stu-id="05247-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
-   <span data-ttu-id="05247-139">Un server TCP in ascolto delle connessioni in ingresso su un socket.</span><span class="sxs-lookup"><span data-stu-id="05247-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
-   <span data-ttu-id="05247-140">Un'applicazione di UDP ricezione di un pacchetto su un socket.</span><span class="sxs-lookup"><span data-stu-id="05247-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="05247-141">Questa impostazione di configurazione non influisce sulle già stabilite le connessioni TCP (il traffico è senza restrizioni in entrambe le direzioni) e non un'applicazione che invia i pacchetti UDP.</span><span class="sxs-lookup"><span data-stu-id="05247-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="05247-142">I valori possibili per il `ipProtectionLevel` impostazione dell'attributo corrispondono ai livelli di protezione definiti specificati nella <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumerazione come illustrato di seguito:</span><span class="sxs-lookup"><span data-stu-id="05247-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="05247-143">**Valore dell'attributo**</span><span class="sxs-lookup"><span data-stu-id="05247-143">**Attribute Value**</span></span>|<span data-ttu-id="05247-144">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="05247-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="05247-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="05247-145">EdgeRestricted</span></span>|<span data-ttu-id="05247-146">Il livello di protezione IP è limitato dal perimetro.</span><span class="sxs-lookup"><span data-stu-id="05247-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="05247-147">Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet.</span><span class="sxs-lookup"><span data-stu-id="05247-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="05247-148">Questa impostazione non consente l'attraversamento Network Address Translation (NAT) usando l'implementazione di Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="05247-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="05247-149">Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi Internet indirizzati alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="05247-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="05247-150">In Windows Server 2003 e Windows XP, il valore predefinito per il livello di protezione IP in un socket è limitato dal perimetro.</span><span class="sxs-lookup"><span data-stu-id="05247-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="05247-151">con restrizioni</span><span class="sxs-lookup"><span data-stu-id="05247-151">Restricted</span></span>|<span data-ttu-id="05247-152">Il livello di protezione IP è limitato.</span><span class="sxs-lookup"><span data-stu-id="05247-152">The IP protection level is restricted.</span></span> <span data-ttu-id="05247-153">Questo valore verrebbe utilizzato dalle applicazioni intranet che non implementano scenari Internet.</span><span class="sxs-lookup"><span data-stu-id="05247-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="05247-154">Queste applicazioni non sono in genere testate o protette contro gli attacchi di tipo Internet.</span><span class="sxs-lookup"><span data-stu-id="05247-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="05247-155">Questa impostazione limiterà il traffico ricevuto solo link-local.</span><span class="sxs-lookup"><span data-stu-id="05247-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="05247-156">Senza restrizioni</span><span class="sxs-lookup"><span data-stu-id="05247-156">Unrestricted</span></span>|<span data-ttu-id="05247-157">Il livello di protezione IP è illimitato.</span><span class="sxs-lookup"><span data-stu-id="05247-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="05247-158">Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet, incluse le applicazioni sfruttando i vantaggi delle funzionalità di attraversamento NAT IPv6 compilate in Windows (ad esempio, Teredo).</span><span class="sxs-lookup"><span data-stu-id="05247-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="05247-159">Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi Internet indirizzati alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="05247-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="05247-160">In Windows Server 2008 R2 e Windows Vista, il valore predefinito per il livello di protezione IP in un socket è illimitato.</span><span class="sxs-lookup"><span data-stu-id="05247-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="05247-161">Non specificato</span><span class="sxs-lookup"><span data-stu-id="05247-161">Unspecified</span></span>|<span data-ttu-id="05247-162">Il livello di protezione IP non è specificato.</span><span class="sxs-lookup"><span data-stu-id="05247-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="05247-163">In Windows 7 e Windows Server 2008 R2, il valore predefinito per il livello di protezione IP in un socket non è specificato.</span><span class="sxs-lookup"><span data-stu-id="05247-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="05247-164">Il valore predefinito per il `ipProtectionLevel` attributo è **Unspecified**.</span><span class="sxs-lookup"><span data-stu-id="05247-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="05247-165">Il <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà può essere utilizzata per ottenere il valore corrente del `ipProtectionLevel` attributo dal file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="05247-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="05247-166">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="05247-166">Configuration Files</span></span>  
 <span data-ttu-id="05247-167">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="05247-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="05247-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="05247-168">Example</span></span>  
 <span data-ttu-id="05247-169">Nell'esempio seguente viene illustrato come specificare che le porte di completamento devono essere utilizzate e che il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> devono essere senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="05247-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05247-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="05247-170">See also</span></span>
- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="05247-171">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="05247-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
