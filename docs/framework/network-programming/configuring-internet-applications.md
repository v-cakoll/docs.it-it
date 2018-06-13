---
title: configurazione di applicazioni Internet
ms.date: 03/30/2017
helpviewer_keywords:
- downloading Internet resources, default proxy
- sending data, default proxy
- receiving data, default proxy
- downloading Internet resources, configuring Internet applications
- protocol-specific modules
- custom authentication modules
- receiving data, configuring Internet applications
- configuration settings [.NET Framework], Internet applications
- requesting data from Internet, configuring Internet applications
- requesting data from Internet, default proxy
- response to Internet request, default proxy
- Internet, configuring Internet applications
- response to Internet request, configuring Internet applications
- default proxy
- network resources, default proxy
- sending data, configuring Internet applications
- network resources, configuring Internet applications
- Internet, default proxy
ms.assetid: bb707c72-eed2-4a82-8800-c9e68df2fd4f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7c4755e13202f60df5704f6faefb3b279a30ce58
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33395060"
---
# <a name="configuring-internet-applications"></a><span data-ttu-id="7ce0a-102">configurazione di applicazioni Internet</span><span class="sxs-lookup"><span data-stu-id="7ce0a-102">Configuring Internet Applications</span></span>
<span data-ttu-id="7ce0a-103">L'elemento di configurazione [ \<system.Net> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) contiene le informazioni di configurazione di rete per le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-103">The [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) configuration element contains network configuration information for applications.</span></span> <span data-ttu-id="7ce0a-104">Tramite l'elemento [ \<system.Net> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) è possibile impostare i server proxy e i parametri di gestione della connessione e includere moduli personalizzati di richiesta e di autenticazione nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-104">Using the [\<system.Net> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element, you can set proxy servers, set connection management parameters, and include custom authentication and request modules in your application.</span></span>  
  
 <span data-ttu-id="7ce0a-105">L'elemento [ \<defaultProxy> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) definisce il server proxy restituito dalla classe `GlobalProxySelection`.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-105">The [\<defaultProxy> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) element defines the proxy server returned by the `GlobalProxySelection` class.</span></span> <span data-ttu-id="7ce0a-106">Qualsiasi <xref:System.Net.HttpWebRequest> la cui proprietà <xref:System.Net.HttpWebRequest.Proxy%2A> non sia impostata su un valore specifico usa il proxy predefinito.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-106">Any <xref:System.Net.HttpWebRequest> that does not have its own <xref:System.Net.HttpWebRequest.Proxy%2A> property set to a specific value uses the default proxy.</span></span> <span data-ttu-id="7ce0a-107">Oltre a impostare l'indirizzo del proxy, è possibile creare un elenco di indirizzi di server che non usano il proxy. È anche possibile indicare che il proxy non deve essere usato per gli indirizzi locali.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-107">In addition to setting the proxy address, you can create a list of server addresses that will not use the proxy, and you can indicate that the proxy should not be used for local addresses.</span></span>  
  
 <span data-ttu-id="7ce0a-108">È importante notare che le impostazioni di Microsoft Internet Explorer vengono combinate con le impostazioni di configurazione, che hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-108">It is important to note that the Microsoft Internet Explorer settings are combined with the configuration settings, with the latter taking precedence.</span></span>  
  
 <span data-ttu-id="7ce0a-109">L'esempio seguente imposta l'indirizzo del server proxy predefinito su http://proxyserver, indica che il proxy non deve essere usato per gli indirizzi locali e specifica che tutte le richieste ai server presenti nel dominio contoso.com devono ignorare il proxy.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-109">The following example sets the default proxy server address to http://proxyserver, indicates that the proxy should not be used for local addresses, and specifies that all requests to servers located in the contoso.com domain should bypass the proxy.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <defaultProxy>  
            <proxy  
                usesystemdefault = "false"  
                proxyaddress = "http://proxyserver:80"  
                bypassonlocal = "true"  
            />  
            <bypasslist>  
                <add address="http://[a-z]+\.contoso\.com/" />  
            </bypasslist>  
        </defaultProxy>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="7ce0a-110">Usare l'elemento [ \<connectionManagement> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) per configurare il numero di connessioni persistenti che è possibile stabilire con un server specifico o con tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-110">Use the [\<connectionManagement> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) element to configure the number of persistent connections that can be made to a specific server or to all other servers.</span></span> <span data-ttu-id="7ce0a-111">L'esempio seguente configura l'applicazione in modo che usi due connessioni persistenti al server www.contoso.com, quattro connessioni persistenti al server con l'indirizzo IP 192.168.1.2 e una connessione persistente a tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-111">The following example configures the application to use two persistent connections to the server www.contoso.com, four persistent connections to the server with the IP address 192.168.1.2, and one persistent connection to all other servers.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <connectionManagement>  
            <add address="http://www.contoso.com" maxconnection="2" />  
            <add address="192.168.1.2" maxconnection="4" />  
            <add address="*" maxconnection="1" />  
        </connectionManagement>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="7ce0a-112">I moduli di autenticazione personalizzati vengono configurati tramite l'elemento [ \<authenticationModules> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7ce0a-112">Custom authentication modules are configured with the [\<authenticationModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md) element.</span></span> <span data-ttu-id="7ce0a-113">I moduli di autenticazione personalizzati devono implementare l'interfaccia <xref:System.Net.IAuthenticationModule>.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-113">Custom authentication modules must implement the <xref:System.Net.IAuthenticationModule> interface.</span></span>  
  
 <span data-ttu-id="7ce0a-114">L'esempio seguente configura un modulo di autenticazione personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-114">The following example configures a custom authentication module.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 <span data-ttu-id="7ce0a-115">È possibile usare l'elemento [ \<webRequestModules> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) per configurare l'applicazione per l'uso di moduli personalizzati specifici del protocollo per richiedere informazioni da risorse Internet.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-115">You can use the [\<webRequestModules> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) element to configure your application to use custom protocol-specific modules to request information from Internet resources.</span></span> <span data-ttu-id="7ce0a-116">I moduli specificati devono implementare l'interfaccia <xref:System.Net.IWebRequestCreate>.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-116">The specified modules must implement the <xref:System.Net.IWebRequestCreate> interface.</span></span> <span data-ttu-id="7ce0a-117">È possibile eseguire l'override dei moduli HTTP, HTTPS e di richiesta di file predefiniti specificando il modulo personalizzato nel file di configurazione, come nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="7ce0a-117">You can override the default HTTP, HTTPS, and file request modules by specifying your custom module in the configuration file, as in the following example.</span></span>  
  
```xml  
<configuration>  
    <system.net>  
        <webRequestModules>  
            <add  
                prefix="HTTP"  
                type = "MyHttpRequest.dll, MyHttpRequestCreator"  
            />  
        </webRequestModules>  
    </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ce0a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7ce0a-118">See Also</span></span>  
 [<span data-ttu-id="7ce0a-119">Programmazione di rete in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7ce0a-119">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)  
 [<span data-ttu-id="7ce0a-120">Schema delle impostazioni di rete</span><span class="sxs-lookup"><span data-stu-id="7ce0a-120">Network Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/network/index.md)  
 [<span data-ttu-id="7ce0a-121">Elemento \<system.Net> (impostazioni di rete)</span><span class="sxs-lookup"><span data-stu-id="7ce0a-121">\<system.Net> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)
