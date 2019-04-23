---
title: Panoramica sulla sicurezza del trasporto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
ms.openlocfilehash: 04526e8aea09b412de4d3a94f17938b02ad6527b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105274"
---
# <a name="transport-security-overview"></a>Panoramica sulla sicurezza del trasporto
Meccanismi di sicurezza del trasporto in Windows Communication Foundation (WCF) dipendono l'associazione e il trasporto utilizzato. Ad esempio, quando si utilizza la classe <xref:System.ServiceModel.WSHttpBinding>, il trasporto è HTTP e il meccanismo principale per la sicurezza del trasporto è SSL (Secure Sockets Layer) su HTTP, comunemente noto come HTTP. Questo argomento descrive i meccanismi di sicurezza di trasporto principali utilizzati nelle associazioni fornite dal sistema di WCF.  
  
> [!NOTE]
>  Quando si usa la protezione SSL con .NET Framework 3.5 e versioni successive un client WCF Usa entrambi i certificati intermedi nel proprio archivio certificati e i certificati intermedi ricevuti durante la negoziazione SSL per eseguire la convalida di catena di certificati del servizio certificato. In .NET Framework 3.0 vengono usati solo i certificati intermedi installati nell'archivio certificati locale.  
  
> [!WARNING]
>  Quando viene utilizzata la sicurezza del trasporto, è possibile che la proprietà <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> venga sovrascritta. Per evitare questo problema, impostare il <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A?displayProperty=nameWithType> a <xref:System.ServiceModel.Description.PrincipalPermissionMode.None?displayProperty=nameWithType>. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> è un comportamento del servizio che può essere impostato sulla descrizione del servizio.  
  
## <a name="basichttpbinding"></a>BasicHttpBinding  
 Per impostazione predefinita, la classe <xref:System.ServiceModel.BasicHttpBinding> non fornisce sicurezza. Questa associazione è progettata per essere interoperabile con i provider di servizi Web che non implementano funzionalità di sicurezza. La sicurezza può essere tuttavia attivata impostando la proprietà <xref:System.ServiceModel.BasicHttpSecurity.Mode%2A> su qualsiasi valore diverso da <xref:System.ServiceModel.BasicHttpSecurityMode.None>. Per abilitare la sicurezza del trasporto, impostare tale proprietà su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.  
  
### <a name="interoperation-with-iis"></a>Interazione con IIS  
 La classe <xref:System.ServiceModel.BasicHttpBinding> viene utilizzata principalmente per interagire con i servizi Web esistenti, molti dei quali sono ospitati da Internet Information Services (IIS). Di conseguenza, la sicurezza del trasporto per questa associazione è progettata per interagire senza difficoltà con i siti IIS. Questo risultato si ottiene impostando la modalità di sicurezza su <xref:System.ServiceModel.BasicHttpSecurityMode.Transport> e quindi specificando il tipo di credenziale client. I valori relativi al tipo di credenziale corrispondono ai meccanismi di sicurezza directory ISS. Nel codice seguente viene illustrata l'impostazione della modalità e del tipo di credenziale su Windows. È possibile utilizzare questa configurazione quando il client e il server si trovano nello stesso dominio Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#10)] 
 [!code-vb[c_ProgrammingSecurity#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#10)]  
  
 oppure in configurazione:  
  
```xml  
<bindings>  
  <basicHttpBinding>  
    <binding name="SecurityByTransport">  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" />  
       </security>  
     </binding>  
  </basicHttpBinding>  
</bindings>  
```  
  
 Nelle sezioni seguenti vengono illustrati altri tipi di credenziali client.  
  
#### <a name="basic"></a>Basic  
 Questo tipo corrisponde al metodo di autenticazione di base di IIS. Quando si utilizza questa modalità, il server IIS deve essere configurato con gli account utente di Windows e le autorizzazioni del file system NTFS appropriate. Per altre informazioni sulle [!INCLUDE[iis601](../../../../includes/iis601-md.md)], vedere [abilitazione dell'autenticazione di base e configurazione del nome dell'area di autenticazione](https://go.microsoft.com/fwlink/?LinkId=88592). Per altre informazioni sulle [!INCLUDE[iisver](../../../../includes/iisver-md.md)], vedere [IIS 7.0 Beta: Configurare l'autenticazione di base](https://go.microsoft.com/fwlink/?LinkId=88593).  
  
#### <a name="certificate"></a>Certificato  
 In IIS è disponibile un'opzione affinché i client debbano eseguire l'accesso con un certificato. Questa funzionalità consente inoltre di eseguire il mapping di un certificato client a un account di Windows. Per altre informazioni sulle [!INCLUDE[iis601](../../../../includes/iis601-md.md)], vedere [abilitazione dei certificati in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88594). Per altre informazioni sulle [!INCLUDE[iisver](../../../../includes/iisver-md.md)], vedere [IIS 7.0 Beta: Configurazione dei certificati del Server in IIS 7.0](https://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="digest"></a>Digest  
 L'autenticazione digest è simile all'autenticazione di base, ma offre il vantaggio di inviare le credenziali come un hash, anziché in testo non crittografato. Per altre informazioni sulle [!INCLUDE[iis601](../../../../includes/iis601-md.md)], vedere [l'autenticazione del Digest in IIS 6.0](https://go.microsoft.com/fwlink/?LinkID=88443). Per altre informazioni sulle [!INCLUDE[iisver](../../../../includes/iisver-md.md)], vedere [IIS 7.0 Beta: Configurare l'autenticazione del Digest](https://go.microsoft.com/fwlink/?LinkId=88596).  
  
#### <a name="windows"></a>WINDOWS  
 Questo tipo corrisponde al metodo di autenticazione integrata di Windows di IIS. In caso di impostazione su questo valore, si prevede inoltre che il server sia in un dominio Windows che utilizza il protocollo Kerberos come controller di dominio. Se il server non è in un dominio con supporto Kerberos o se il sistema Kerberos ha esito negativo, è possibile utilizzare il valore NTLM (NT LAN Manager) descritto nella sezione successiva. Per altre informazioni sulle [!INCLUDE[iis601](../../../../includes/iis601-md.md)], vedere [l'autenticazione integrata di Windows in IIS 6.0](https://go.microsoft.com/fwlink/?LinkId=88597). Per altre informazioni sulle [!INCLUDE[iisver](../../../../includes/iisver-md.md)], vedere [IIS 7.0 Beta: Configurazione dei certificati del Server in IIS 7.0](https://go.microsoft.com/fwlink/?LinkId=88595).  
  
#### <a name="ntlm"></a>NTLM  
 Consente al server di utilizzare NTLM per l'autenticazione se il protocollo Kerberos ha esito negativo. Per altre informazioni sulla configurazione di IIS in [!INCLUDE[iis601](../../../../includes/iis601-md.md)], vedere [forzatura dell'autenticazione NTLM](https://go.microsoft.com/fwlink/?LinkId=88598). Per [!INCLUDE[iisver](../../../../includes/iisver-md.md)], l'autenticazione di Windows include l'autenticazione NTLM. Per altre informazioni, vedere [IIS 7.0 Beta: Configurazione dei certificati del Server in IIS 7.0](https://go.microsoft.com/fwlink/?LinkID=88595).  
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 La classe <xref:System.ServiceModel.WSHttpBinding> è progettata per essere interoperabile con i servizi che implementano le specifiche WS - *. La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS. Per creare un'applicazione WCF che usa SSL, utilizzare IIS per ospitare l'applicazione. In alternativa, se si sta creando un'applicazione indipendente, utilizzare lo strumento HttpCfg.exe per associare un certificato X.509 a una porta specifica in un computer. Il numero di porta viene specificato come parte dell'applicazione WCF come indirizzo dell'endpoint. Quando si utilizza la modalità di trasporto, l'indirizzo dell'endpoint deve includere il protocollo HTTPS; in caso contrario verrà generata un'eccezione in fase di esecuzione. Per altre informazioni, vedere [protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 L'autenticazione client, impostare la proprietà <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> della classe <xref:System.ServiceModel.HttpTransportSecurity> su uno dei valori di enumerazione di <xref:System.ServiceModel.HttpClientCredentialType>. I valori di enumerazione corrispondono ai tipi di credenziali client per <xref:System.ServiceModel.BasicHttpBinding> e sono progettati per essere ospitati nei servizi IIS.  
  
 Nell'esempio seguente viene illustrata l'associazione utilizzata con un tipo di credenziale client di Windows.  
  
 [!code-csharp[c_ProgrammingSecurity#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#11)]
 [!code-vb[c_ProgrammingSecurity#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#11)]  
  
## <a name="wsdualhttpbinding"></a>WSDualHttpBinding  
 Questa associazione fornisce sicurezza solo a livello di messaggio, non a livello di trasporto.  
  
## <a name="nettcpbinding"></a>NetTcpBinding  
 La classe <xref:System.ServiceModel.NetTcpBinding> utilizza il protocollo TCP per il trasporto dei messaggi. La sicurezza per la modalità di trasporto viene fornita implementando il protocollo TLS (Transport Layer Security) su TCP. L'implementazione di TLS viene fornita dal sistema operativo.  
  
 È inoltre possibile specificare il tipo di credenziale del client impostando la proprietà <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> della classe <xref:System.ServiceModel.TcpTransportSecurity> su uno dei valori di <xref:System.ServiceModel.TcpClientCredentialType>, come illustrato nel codice seguente.  
  
 [!code-csharp[c_ProgrammingSecurity#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#12)]
 [!code-vb[c_ProgrammingSecurity#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#12)]  
  
#### <a name="client"></a>Client  
 Sul client è necessario specificare un certificato utilizzando il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
> [!NOTE]
>  Se si utilizza la sicurezza di Windows, non è necessario un certificato.  
  
 Nel codice seguente viene utilizzata l'identificazione digitale del certificato, che lo identifica in modo univoco. Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 In alternativa, specificare il certificato nella configurazione del client utilizzando un [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento nella sezione dei comportamenti.  
  
```xml  
<behaviors>  
  <behavior>  
   <clientCredentials>  
     <clientCertificate findValue= "101010101010101010101010101010000000000"   
      storeLocation="LocalMachine" storeName="My"   
      X509FindType="FindByThumbPrint"/>  
     </clientCertificate>  
   </clientCredentials>  
 </behavior>  
</behaviors>    
```  
  
## <a name="netnamedpipebinding"></a>NetNamedPipeBinding  
 La classe <xref:System.ServiceModel.NetNamedPipeBinding> è progettata per consentire una comunicazione efficiente intra-computer, ovvero per i processi in esecuzione sullo stesso computer, sebbene sia possibile creare canali named pipe tra due computer sulla stessa rete. Questa associazione fornisce sicurezza solo a livello di trasporto. Quando si creano applicazioni utilizzando questa associazione, gli indirizzi di endpoint devono includere "net.pipe" come protocollo.  
  
## <a name="wsfederationhttpbinding"></a>WSFederationHttpBinding  
 Quando si utilizza la sicurezza del trasporto, in questa associazione viene utilizzato SSL su HTTP, noto come HTTPS, con un token emesso (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). Per altre informazioni sulle applicazioni di federazione, vedere [federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 La classe <xref:System.ServiceModel.NetPeerTcpBinding> costituisce un trasporto protetto progettato per consentire una comunicazione efficiente utilizzando la funzionalità di rete peer-to-peer. Come indicato dal nome della classe e dell'associazione, il protocollo è TCP. Quando la modalità di sicurezza è impostata su Trasporto, l'associazione implementa TLS su TCP. Per altre informazioni sulla funzionalità peer-to-peer, vedere [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding e NetMsmqBinding  
 Per una descrizione completa del trasporto della protezione con Accodamento messaggi (precedentemente chiamato MSMQ), vedere [protezione dei messaggi mediante protezione del trasporto](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md).  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione delle funzionalità di sicurezza di WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
