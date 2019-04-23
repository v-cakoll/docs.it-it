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
ms.openlocfilehash: ddc4717c873e65311a8502e66f3edaf39dd89ff9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133802"
---
# <a name="configuring-internet-applications"></a>configurazione di applicazioni Internet
L'elemento di configurazione [ \<system.Net> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) contiene le informazioni di configurazione di rete per le applicazioni. Tramite l'elemento [ \<system.Net> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) è possibile impostare i server proxy e i parametri di gestione della connessione e includere moduli personalizzati di richiesta e di autenticazione nell'applicazione.  
  
 L'elemento [ \<defaultProxy> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md) definisce il server proxy restituito dalla classe `GlobalProxySelection`. Qualsiasi <xref:System.Net.HttpWebRequest> la cui proprietà <xref:System.Net.HttpWebRequest.Proxy%2A> non sia impostata su un valore specifico usa il proxy predefinito. Oltre a impostare l'indirizzo del proxy, è possibile creare un elenco di indirizzi di server che non usano il proxy. È anche possibile indicare che il proxy non deve essere usato per gli indirizzi locali.  
  
 È importante notare che le impostazioni di Microsoft Internet Explorer vengono combinate con le impostazioni di configurazione, che hanno la precedenza.  
  
 L'esempio seguente imposta l'indirizzo del server proxy predefinito su `http://proxyserver`, indica che il proxy non deve essere usato per gli indirizzi locali e specifica che tutte le richieste ai server presenti nel dominio contoso.com devono ignorare il proxy.  
  
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
  
 Usare l'elemento [ \<connectionManagement> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md) per configurare il numero di connessioni persistenti che è possibile stabilire con un server specifico o con tutti gli altri server. L'esempio seguente configura l'applicazione in modo da usare due connessioni persistenti al server `www.contoso.com`, quattro connessioni persistenti al server con indirizzo IP 192.168.1.2 e una connessione persistente a tutti gli altri server.  
  
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
  
 I moduli di autenticazione personalizzati vengono configurati tramite l'elemento [ \<authenticationModules> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md). I moduli di autenticazione personalizzati devono implementare l'interfaccia <xref:System.Net.IAuthenticationModule>.  
  
 L'esempio seguente configura un modulo di autenticazione personalizzato.  
  
```xml  
<configuration>  
    <system.net>  
        <authenticationModules>  
            <add type="MyAuthModule, MyAuthModule.dll" />  
        </authenticationModules>  
    </system.net>  
</configuration>  
```  
  
 È possibile usare l'elemento [ \<webRequestModules> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md) per configurare l'applicazione per l'uso di moduli personalizzati specifici del protocollo per richiedere informazioni da risorse Internet. I moduli specificati devono implementare l'interfaccia <xref:System.Net.IWebRequestCreate>. È possibile eseguire l'override dei moduli HTTP, HTTPS e di richiesta di file predefiniti specificando il modulo personalizzato nel file di configurazione, come nell'esempio seguente.  
  
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
  
## <a name="see-also"></a>Vedere anche

- [Programmazione di rete in .NET Framework](../../../docs/framework/network-programming/index.md)
- [Schema delle impostazioni di rete](../../../docs/framework/configure-apps/file-schema/network/index.md)
- [Elemento \<system.Net> (impostazioni di rete)](../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)
