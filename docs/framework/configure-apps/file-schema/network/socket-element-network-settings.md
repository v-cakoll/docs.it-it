---
title: Elemento <socket> (impostazioni di rete)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2020
ms.locfileid: "74089085"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="a2a51-102">Elemento \<socket> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="a2a51-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="a2a51-103">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="a2a51-103">Specifies whether socket operations use completion ports.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

## <a name="syntax"></a><span data-ttu-id="a2a51-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a2a51-104">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a2a51-105">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="a2a51-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a2a51-106">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="a2a51-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a2a51-107">Attributi</span><span class="sxs-lookup"><span data-stu-id="a2a51-107">Attributes</span></span>  
  
|<span data-ttu-id="a2a51-108">**Attributo**</span><span class="sxs-lookup"><span data-stu-id="a2a51-108">**Attribute**</span></span>|<span data-ttu-id="a2a51-109">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a2a51-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="a2a51-110">Indica se il socket deve utilizzare sempre le porte di completamento per le chiamate al metodo Accept.</span><span class="sxs-lookup"><span data-stu-id="a2a51-110">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="a2a51-111">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a2a51-111">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="a2a51-112">Indica se il socket deve utilizzare sempre le porte di completamento per le chiamate al metodo Connect.</span><span class="sxs-lookup"><span data-stu-id="a2a51-112">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="a2a51-113">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a2a51-113">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="a2a51-114">Specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="a2a51-114">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="a2a51-115">Il valore predefinito dipende dalla versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a2a51-115">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a2a51-116">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="a2a51-116">Child Elements</span></span>  
 <span data-ttu-id="a2a51-117">No.</span><span class="sxs-lookup"><span data-stu-id="a2a51-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a2a51-118">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="a2a51-118">Parent Elements</span></span>  
  
|<span data-ttu-id="a2a51-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="a2a51-119">**Element**</span></span>|<span data-ttu-id="a2a51-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a2a51-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a2a51-121">impostazioni</span><span class="sxs-lookup"><span data-stu-id="a2a51-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="a2a51-122">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="a2a51-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a2a51-123">Commenti</span><span class="sxs-lookup"><span data-stu-id="a2a51-123">Remarks</span></span>  
 <span data-ttu-id="a2a51-124">Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a2a51-124">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="a2a51-125">Le porte di completamento sono consigliate per le applicazioni server a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="a2a51-125">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="a2a51-126">Il valore predefinito per gli `alwaysUseCompletionPortsForAccept` `alwaysUseCompletionPortsForConnect` attributi e è **false**.</span><span class="sxs-lookup"><span data-stu-id="a2a51-126">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="a2a51-127"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>È possibile utilizzare l'oggetto per ottenere il valore corrente dell' `alwaysUseCompletionPortsForAccept` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="a2a51-127">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="a2a51-128"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>È possibile utilizzare l'oggetto per ottenere il valore corrente dell' `alwaysUseCompletionPortsForConnect` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="a2a51-128">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="a2a51-129">L' `ipProtectionLevel` attributo specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="a2a51-129">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="a2a51-130">La <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> proprietà consente la configurazione di una restrizione per un socket IPv6 in un ambito specificato, ad esempio indirizzi con lo stesso prefisso locale del collegamento o del sito.</span><span class="sxs-lookup"><span data-stu-id="a2a51-130">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="a2a51-131">Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6.</span><span class="sxs-lookup"><span data-stu-id="a2a51-131">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="a2a51-132">Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni.</span><span class="sxs-lookup"><span data-stu-id="a2a51-132">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="a2a51-133">Questa opzione consente di ampliare o limitare l'ambito di un socket in ascolto, abilitando l'accesso illimitato da parte di utenti pubblici e privati, quando appropriato, o limitando l'accesso solo allo stesso sito, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a2a51-133">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="a2a51-134">Questa `ipProtectionLevel` impostazione di attributo influisca solo sul traffico in ingresso iniziale:</span><span class="sxs-lookup"><span data-stu-id="a2a51-134">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="a2a51-135">Un server TCP in ascolto delle connessioni in ingresso su un socket.</span><span class="sxs-lookup"><span data-stu-id="a2a51-135">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="a2a51-136">Un'applicazione UDP che riceve un pacchetto in un socket.</span><span class="sxs-lookup"><span data-stu-id="a2a51-136">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="a2a51-137">Questa impostazione di configurazione non influisce sulle connessioni TCP già stabilite (il traffico non è limitato in entrambe le direzioni) e non influisce su un'applicazione che invia pacchetti UDP.</span><span class="sxs-lookup"><span data-stu-id="a2a51-137">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="a2a51-138">I valori possibili per l' `ipProtectionLevel` impostazione dell'attributo corrispondono ai livelli di protezione definiti specificati nell' <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumerazione, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="a2a51-138">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="a2a51-139">**Valore dell'attributo**</span><span class="sxs-lookup"><span data-stu-id="a2a51-139">**Attribute Value**</span></span>|<span data-ttu-id="a2a51-140">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a2a51-140">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="a2a51-141">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="a2a51-141">EdgeRestricted</span></span>|<span data-ttu-id="a2a51-142">Il livello di protezione IP è limitato dal perimetro.</span><span class="sxs-lookup"><span data-stu-id="a2a51-142">The IP protection level is edge restricted.</span></span> <span data-ttu-id="a2a51-143">Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet.</span><span class="sxs-lookup"><span data-stu-id="a2a51-143">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="a2a51-144">Questa impostazione non consente l'attraversamento NAT (Network Address Translation) tramite l'implementazione di Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="a2a51-144">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="a2a51-145">Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi provenienti da Internet diretti alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="a2a51-145">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="a2a51-146">In Windows Server 2003 e in Windows XP, il valore predefinito per il livello di protezione IP in un socket è limitato dal perimetro.</span><span class="sxs-lookup"><span data-stu-id="a2a51-146">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="a2a51-147">Con restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2a51-147">Restricted</span></span>|<span data-ttu-id="a2a51-148">Il livello di protezione IP è limitato.</span><span class="sxs-lookup"><span data-stu-id="a2a51-148">The IP protection level is restricted.</span></span> <span data-ttu-id="a2a51-149">Questo valore verrebbe utilizzato da applicazioni Intranet che non implementano scenari Internet.</span><span class="sxs-lookup"><span data-stu-id="a2a51-149">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="a2a51-150">Queste applicazioni non sono in genere testate o protette da attacchi analoghi a quelli provenienti da Internet.</span><span class="sxs-lookup"><span data-stu-id="a2a51-150">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="a2a51-151">Questa impostazione limiterà il traffico ricevuto solo a quello locale rispetto al collegamento.</span><span class="sxs-lookup"><span data-stu-id="a2a51-151">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="a2a51-152">Senza restrizioni</span><span class="sxs-lookup"><span data-stu-id="a2a51-152">Unrestricted</span></span>|<span data-ttu-id="a2a51-153">Il livello di protezione IP è illimitato.</span><span class="sxs-lookup"><span data-stu-id="a2a51-153">The IP protection level is unrestricted.</span></span> <span data-ttu-id="a2a51-154">Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet, incluse la applicazioni che usufruiscono delle funzionalità di attraversamento NAT IPv6 compilate in Windows (ad esempio, Teredo).</span><span class="sxs-lookup"><span data-stu-id="a2a51-154">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="a2a51-155">Tali applicazioni possono aggirare i firewall IPv4 e pertanto le applicazioni devono essere protette contro gli attacchi provenienti da Internet diretti alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="a2a51-155">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="a2a51-156">In Windows Server 2008 R2 e in Windows Vista, il valore predefinito per il livello di protezione IP in un socket è illimitato.</span><span class="sxs-lookup"><span data-stu-id="a2a51-156">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="a2a51-157">Non specificata</span><span class="sxs-lookup"><span data-stu-id="a2a51-157">Unspecified</span></span>|<span data-ttu-id="a2a51-158">Il livello di protezione IP non è specificato.</span><span class="sxs-lookup"><span data-stu-id="a2a51-158">The IP protection level is unspecified.</span></span> <span data-ttu-id="a2a51-159">In Windows 7 e in Windows Server 2008 R2, il valore predefinito per il livello di protezione IP in un socket non è specificato.</span><span class="sxs-lookup"><span data-stu-id="a2a51-159">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="a2a51-160">Il valore predefinito per l' `ipProtectionLevel` attributo non è **specificato**.</span><span class="sxs-lookup"><span data-stu-id="a2a51-160">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="a2a51-161"><xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>È possibile utilizzare la proprietà per ottenere il valore corrente dell' `ipProtectionLevel` attributo dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="a2a51-161">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a2a51-162">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="a2a51-162">Configuration Files</span></span>  
 <span data-ttu-id="a2a51-163">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a2a51-163">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2a51-164">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2a51-164">Example</span></span>  
 <span data-ttu-id="a2a51-165">Nell'esempio seguente viene illustrato come specificare che devono essere utilizzate le porte di completamento e che l'impostazione predefinita <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> deve essere senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="a2a51-165">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a2a51-166">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="a2a51-166">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="a2a51-167">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="a2a51-167">Network Settings Schema</span></span>](index.md)
