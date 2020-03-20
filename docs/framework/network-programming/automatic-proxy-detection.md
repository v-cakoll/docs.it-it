---
title: Rilevamento automatico proxy
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- automatic proxy detections
- Web Proxy Auto-Discovery
- Web proxy
- detecting proxies automatically
- WebProxy class, automatic proxy detections
- proxies, automatically detecting
- network
- WPAD (Web Proxy Auto-Discovery)
ms.assetid: fcd9c3bd-93de-4c92-8ff3-837327ad18de
ms.openlocfilehash: 4c5bc9e0efb39032d388d141e8bccf3e520ebd45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180890"
---
# <a name="automatic-proxy-detection"></a><span data-ttu-id="2c063-102">Rilevamento automatico proxy</span><span class="sxs-lookup"><span data-stu-id="2c063-102">Automatic Proxy Detection</span></span>
<span data-ttu-id="2c063-103">Il rilevamento automatico del proxy è un processo con cui un server proxy Web viene identificato dal sistema e usato per inviare richieste per conto del client.</span><span class="sxs-lookup"><span data-stu-id="2c063-103">Automatic proxy detection is a process by which a Web proxy server is identified by the system and used to send requests on behalf of the client.</span></span> <span data-ttu-id="2c063-104">Questa funzionalità è nota anche come Rilevamento automatico proxy Web (WPAD).</span><span class="sxs-lookup"><span data-stu-id="2c063-104">This feature is also known as Web Proxy Auto-Discovery (WPAD).</span></span> <span data-ttu-id="2c063-105">Quando il rilevamento automatico del proxy è abilitato, il sistema tenta di trovare uno script di configurazione del proxy responsabile della restituzione del set di proxy che possono essere usati per la richiesta.</span><span class="sxs-lookup"><span data-stu-id="2c063-105">When automatic proxy detection is enabled, the system attempts to locate a proxy configuration script that is responsible for returning the set of proxies that can be used for the request.</span></span> <span data-ttu-id="2c063-106">Se viene trovato, lo script di configurazione del proxy viene scaricato, compilato ed eseguito nel computer locale quando per una richiesta che usa un'istanza <xref:System.Net.WebProxy> vengono ottenute le informazioni del proxy, la risposta o il flusso di richieste.</span><span class="sxs-lookup"><span data-stu-id="2c063-106">If the proxy configuration script is found, the script is downloaded, compiled, and run on the local computer when proxy information, the request stream, or the response is obtained for a request that uses a <xref:System.Net.WebProxy> instance.</span></span>  
  
 <span data-ttu-id="2c063-107">Il rilevamento automatico del proxy viene eseguito dalla classe <xref:System.Net.WebProxy> e può usare impostazioni a livello di richiesta, impostazioni del file di configurazione e impostazioni specificate tramite la finestra di dialogo **Rete locale (LAN)** di Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c063-107">Automatic proxy detection is performed by the <xref:System.Net.WebProxy> class and can employ request-level settings, settings in configuration files, and settings specified using the Internet Explorer **Local Area Network (LAN)** dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c063-108">È possibile visualizzare la finestra di dialogo di Internet Explorer **Impostazioni rete locale (LAN)** selezionando **Strumenti** dal menu principale di Internet Explorer e quindi scegliendo **Opzioni Internet**.</span><span class="sxs-lookup"><span data-stu-id="2c063-108">You can display the Internet Explorer **Local Area Network (LAN) Settings** dialog box by selecting **Tools** from the Internet Explorer main menu and then selecting **Internet Options**.</span></span> <span data-ttu-id="2c063-109">Selezionare quindi la scheda **Connessioni** e scegliere **Impostazioni LAN**.</span><span class="sxs-lookup"><span data-stu-id="2c063-109">Next, select the **Connections** tab, and click **LAN Settings**.</span></span>  
  
 <span data-ttu-id="2c063-110">Se il rilevamento automatico del proxy è abilitato, la classe <xref:System.Net.WebProxy> tenta di individuare lo script di configurazione del proxy come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="2c063-110">When automatic proxy detection is enabled, the <xref:System.Net.WebProxy> class attempts to locate the proxy configuration script as follows:</span></span>  
  
1. <span data-ttu-id="2c063-111">La funzione di WinINet `InternetQueryOption` consente di individuare l'ultimo script di configurazione del proxy rilevato da Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c063-111">The WinINet `InternetQueryOption` function is used to locate the proxy configuration script most recently detected by Internet Explorer.</span></span>  
  
2. <span data-ttu-id="2c063-112">Se lo script non viene individuato, la classe <xref:System.Net.WebProxy> usa il Dynamic Host Configuration Protocol (DHCP) per trovarlo.</span><span class="sxs-lookup"><span data-stu-id="2c063-112">If the script is not located, the <xref:System.Net.WebProxy> class uses the Dynamic Host Configuration Protocol (DHCP) to locate the script.</span></span> <span data-ttu-id="2c063-113">Il server DHCP può rispondere specificando il percorso (nome host) o l'URL completo dello script.</span><span class="sxs-lookup"><span data-stu-id="2c063-113">The DHCP server can respond either with the location (host name) of the script or with the full URL for the script.</span></span>  
  
3. <span data-ttu-id="2c063-114">Se DHCP non identifica l'host WPAD, viene eseguita una query sul server DNS per trovare un host con WPAD come nome o alias.</span><span class="sxs-lookup"><span data-stu-id="2c063-114">If DHCP does not identify the WPAD host, DNS is queried for a host with WPAD as its name or alias.</span></span>  
  
4. <span data-ttu-id="2c063-115">Se l'host non viene identificato ma nelle impostazioni della LAN di Internet Explorer o in un file di configurazione è specificato il percorso di uno script di configurazione del proxy, viene usato questo percorso.</span><span class="sxs-lookup"><span data-stu-id="2c063-115">If the host is not identified and the location of a proxy configuration script is specified by the Internet Explorer LAN settings or a configuration file, this location is used.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c063-116">Le applicazioni in esecuzione come servizio NT o nell'ambito di ASP.NET usano le impostazioni del server proxy configurate dall'utente chiamante in Internet Explorer (se disponibili).</span><span class="sxs-lookup"><span data-stu-id="2c063-116">Applications running as an NT Service or as part of ASP.NET use the Internet Explorer proxy server settings (if available) of the invoking user.</span></span> <span data-ttu-id="2c063-117">È possibile che queste impostazioni non siano disponibili per tutte le applicazioni di servizio.</span><span class="sxs-lookup"><span data-stu-id="2c063-117">These settings may not be available for all service applications.</span></span>  
  
 <span data-ttu-id="2c063-118">I proxy vengono configurati a livello di singolo connettoide.</span><span class="sxs-lookup"><span data-stu-id="2c063-118">Proxies are configured on a per-connectoid basis.</span></span> <span data-ttu-id="2c063-119">Un connettoide è un elemento della finestra di dialogo di connessione di rete e può essere un dispositivo di rete fisico (modem o scheda Ethernet) o un'interfaccia virtuale (ad esempio, una connessione VPN in esecuzione su un dispositivo di rete).</span><span class="sxs-lookup"><span data-stu-id="2c063-119">A connectoid is an item in the network connection dialog, and can be a physical network device (a modem or Ethernet card) or a virtual interface (such as a VPN connection running over a network device).</span></span> <span data-ttu-id="2c063-120">Se un connettoide cambia (ad esempio, una connessione wireless modifica un punto di accesso o viene abilitata una rete VPN), l'algoritmo di rilevamento del proxy viene eseguito nuovamente.</span><span class="sxs-lookup"><span data-stu-id="2c063-120">When a connectoid changes (for example, a wireless connection changes an access point, or a VPN is enabled), the proxy detection algorithm is run again.</span></span>  
  
 <span data-ttu-id="2c063-121">Per impostazione predefinita, per il rilevamento del proxy vengono usate le impostazioni del proxy definite in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="2c063-121">By default, the Internet Explorer proxy settings are used to detect the proxy.</span></span> <span data-ttu-id="2c063-122">Se l'applicazione viene eseguita con un account non interattivo (senza un modo pratico per configurare le impostazioni proxy di Internet Explorer) o se si desidera utilizzare impostazioni proxy diverse da quelle di Internet Explorer, è possibile configurare il proxy creando un file di configurazione con gli [ \<elementi predefinitiElemento> (impostazioni di rete)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) e [ \<elemento> proxy (impostazioni di rete)](../configure-apps/file-schema/network/proxy-element-network-settings.md) definiti.</span><span class="sxs-lookup"><span data-stu-id="2c063-122">If your application is running under a non-interactive account (without a convenient way to configure IE proxy settings), or if you want to use proxy settings different than the IE settings, you can configure your proxy by creating a configuration file with the [\<defaultProxy> Element (Network Settings)](../configure-apps/file-schema/network/defaultproxy-element-network-settings.md) and [\<proxy> Element (Network Settings)](../configure-apps/file-schema/network/proxy-element-network-settings.md) elements defined.</span></span>  
  
 <span data-ttu-id="2c063-123">Per le richieste create, è possibile disabilitare il rilevamento automatico del proxy a livello di richiesta specificando un valore <xref:System.Net.WebRequest.Proxy%2A> null con la richiesta, come illustrato nell'esempio di codice seguente.</span><span class="sxs-lookup"><span data-stu-id="2c063-123">For requests that you create, you can disable automatic proxy detection at the request level by using a null <xref:System.Net.WebRequest.Proxy%2A> with your request, as shown in the following code example.</span></span>  
  
```csharp  
public static void DisableForMyRequest (Uri resource)  
{  
    WebRequest request = WebRequest.Create (resource);  
    request.Proxy = null;  
    WebResponse response = request.GetResponse ();  
}  
```  
  
```vb  
Public Shared Sub DisableForMyRequest(ByVal resource As Uri)  
    Dim request As WebRequest = WebRequest.Create(resource)  
    request.Proxy = Nothing  
    Dim response As WebResponse = request.GetResponse()  
    End Sub
```  
  
 <span data-ttu-id="2c063-124">Le richieste in cui non è specificato un proxy usano il proxy predefinito del dominio dell'applicazione, disponibile nella proprietà <xref:System.Net.WebRequest.DefaultWebProxy%2A>.</span><span class="sxs-lookup"><span data-stu-id="2c063-124">Requests that do not have a proxy use your application domain's default proxy, which is available in the <xref:System.Net.WebRequest.DefaultWebProxy%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c063-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c063-125">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.WebRequest>
- [<span data-ttu-id="2c063-126">\<elemento> system.Net (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="2c063-126">\<system.Net> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/system-net-element-network-settings.md)
