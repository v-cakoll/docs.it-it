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
ms.openlocfilehash: ec2c8388411e24940041dc9dcb7f6a6755e89805
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697578"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="4ccb5-102">Elemento > \<socket (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="4ccb5-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="4ccb5-103">Specifica se le operazioni socket utilizzano le porte di completamento.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-103">Specifies whether socket operations use completion ports.</span></span>  
  
[<span data-ttu-id="4ccb5-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="4ccb5-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="4ccb5-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4ccb5-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="4ccb5-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="4ccb5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="4ccb5-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<socket >**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ccb5-108">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4ccb5-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ccb5-109">Attributi ed elementi</span><span class="sxs-lookup"><span data-stu-id="4ccb5-109">Attributes and Elements</span></span>  
 <span data-ttu-id="4ccb5-110">Nelle sezioni seguenti vengono descritti gli attributi, gli elementi figlio e gli elementi padre.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ccb5-111">Attributi</span><span class="sxs-lookup"><span data-stu-id="4ccb5-111">Attributes</span></span>  
  
|<span data-ttu-id="4ccb5-112">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-112">**Attribute**</span></span>|<span data-ttu-id="4ccb5-113">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="4ccb5-114">Indica se il socket deve utilizzare sempre le porte di completamento per le chiamate al metodo Accept.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="4ccb5-115">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="4ccb5-116">Indica se il socket deve utilizzare sempre le porte di completamento per le chiamate al metodo Connect.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="4ccb5-117">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="4ccb5-118">Specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="4ccb5-119">Il valore predefinito dipende dalla versione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ccb5-120">Elementi figlio</span><span class="sxs-lookup"><span data-stu-id="4ccb5-120">Child Elements</span></span>  
 <span data-ttu-id="4ccb5-121">No.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ccb5-122">Elementi padre</span><span class="sxs-lookup"><span data-stu-id="4ccb5-122">Parent Elements</span></span>  
  
|<span data-ttu-id="4ccb5-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-123">**Element**</span></span>|<span data-ttu-id="4ccb5-124">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4ccb5-125">Impostazioni</span><span class="sxs-lookup"><span data-stu-id="4ccb5-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="4ccb5-126">Configura le opzioni di rete di base per lo spazio dei nomi <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ccb5-127">Note</span><span class="sxs-lookup"><span data-stu-id="4ccb5-127">Remarks</span></span>  
 <span data-ttu-id="4ccb5-128">Gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` vengono utilizzati per specificare il comportamento predefinito riguardante l'utilizzo di porte di completamento da parte delle classi nello spazio dei nomi <xref:System.Net.Sockets?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="4ccb5-129">Le porte di completamento sono consigliate per le applicazioni server a prestazioni elevate.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="4ccb5-130">Il valore predefinito per gli attributi `alwaysUseCompletionPortsForAccept` e `alwaysUseCompletionPortsForConnect` è **false**.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="4ccb5-131">È possibile utilizzare <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> per ottenere il valore corrente dell'attributo `alwaysUseCompletionPortsForAccept` dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="4ccb5-132">È possibile utilizzare <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> per ottenere il valore corrente dell'attributo `alwaysUseCompletionPortsForConnect` dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="4ccb5-133">L'attributo `ipProtectionLevel` specifica il valore predefinito <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> da utilizzare per un socket.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="4ccb5-134">La proprietà <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> consente la configurazione di una restrizione per un socket IPv6 in un ambito specificato, ad esempio indirizzi con lo stesso prefisso locale del collegamento o sito locale.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="4ccb5-135">Questa opzione consente alle applicazioni di inserire restrizioni di accesso sui socket IPv6.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="4ccb5-136">Tali restrizioni consentono a un'applicazione in esecuzione su una LAN privata di proteggersi in modo semplice e affidabile da attacchi esterni.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="4ccb5-137">Questa opzione consente di ampliare o limitare l'ambito di un socket in ascolto, abilitando l'accesso illimitato da parte di utenti pubblici e privati, quando appropriato, o limitando l'accesso solo allo stesso sito, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="4ccb5-138">Questa impostazione di attributo `ipProtectionLevel` influisca solo sul traffico in ingresso iniziale:</span><span class="sxs-lookup"><span data-stu-id="4ccb5-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="4ccb5-139">Un server TCP in ascolto delle connessioni in ingresso su un socket.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="4ccb5-140">Un'applicazione UDP che riceve un pacchetto in un socket.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="4ccb5-141">Questa impostazione di configurazione non influisce sulle connessioni TCP già stabilite (il traffico non è limitato in entrambe le direzioni) e non influisce su un'applicazione che invia pacchetti UDP.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="4ccb5-142">I valori possibili per l'impostazione dell'attributo `ipProtectionLevel` corrispondono ai livelli di protezione definiti specificati nell'enumerazione <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4ccb5-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="4ccb5-143">**Valore dell'attributo**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-143">**Attribute Value**</span></span>|<span data-ttu-id="4ccb5-144">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4ccb5-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="4ccb5-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="4ccb5-145">EdgeRestricted</span></span>|<span data-ttu-id="4ccb5-146">Il livello di protezione IP è limitato da Edge.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="4ccb5-147">Questo valore verrebbe utilizzato dalle applicazioni progettate per operare in Internet.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="4ccb5-148">Questa impostazione non consente l'attraversamento NAT (Network Address Translation) tramite l'implementazione di Windows Teredo.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="4ccb5-149">Queste applicazioni possono ignorare i firewall IPv4, quindi le applicazioni devono essere protette da attacchi Internet diretti alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="4ccb5-150">In Windows Server 2003 e Windows XP, il valore predefinito per il livello di protezione IP in un socket è limitato da Edge.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="4ccb5-151">Limitato</span><span class="sxs-lookup"><span data-stu-id="4ccb5-151">Restricted</span></span>|<span data-ttu-id="4ccb5-152">Il livello di protezione IP è limitato.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-152">The IP protection level is restricted.</span></span> <span data-ttu-id="4ccb5-153">Questo valore verrebbe utilizzato dalle applicazioni Intranet che non implementano scenari Internet.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="4ccb5-154">Queste applicazioni in genere non sono testate o finalizzate agli attacchi di tipo Internet.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="4ccb5-155">Questa impostazione consente di limitare il traffico ricevuto solo al collegamento locale.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="4ccb5-156">Senza restrizioni</span><span class="sxs-lookup"><span data-stu-id="4ccb5-156">Unrestricted</span></span>|<span data-ttu-id="4ccb5-157">Il livello di protezione IP è senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="4ccb5-158">Questo valore verrebbe utilizzato dalle applicazioni progettate per operare su Internet, incluse le applicazioni che sfruttano le funzionalità di attraversamento NAT IPv6 incorporate in Windows (ad esempio, Teredo).</span><span class="sxs-lookup"><span data-stu-id="4ccb5-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="4ccb5-159">Queste applicazioni possono ignorare i firewall IPv4, quindi le applicazioni devono essere protette da attacchi Internet diretti alla porta aperta.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="4ccb5-160">In Windows Server 2008 R2 e Windows Vista, il valore predefinito per il livello di protezione IP in un socket è senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="4ccb5-161">Non specificato</span><span class="sxs-lookup"><span data-stu-id="4ccb5-161">Unspecified</span></span>|<span data-ttu-id="4ccb5-162">Il livello di protezione IP non è specificato.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="4ccb5-163">In Windows 7 e Windows Server 2008 R2, il valore predefinito per il livello di protezione IP in un socket non è specificato.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="4ccb5-164">Il valore predefinito per l'attributo `ipProtectionLevel` non è **specificato**.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="4ccb5-165">È possibile utilizzare la proprietà <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> per ottenere il valore corrente dell'attributo `ipProtectionLevel` dai file di configurazione applicabili.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4ccb5-166">File di configurazione</span><span class="sxs-lookup"><span data-stu-id="4ccb5-166">Configuration Files</span></span>  
 <span data-ttu-id="4ccb5-167">Questo elemento può essere usato nel file di configurazione dell'applicazione o nel file di configurazione del computer (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4ccb5-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ccb5-168">Esempio</span><span class="sxs-lookup"><span data-stu-id="4ccb5-168">Example</span></span>  
 <span data-ttu-id="4ccb5-169">Nell'esempio seguente viene illustrato come specificare che devono essere utilizzate le porte di completamento e che l'impostazione predefinita <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> deve essere senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="4ccb5-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4ccb5-170">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4ccb5-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="4ccb5-171">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="4ccb5-171">Network Settings Schema</span></span>](index.md)
