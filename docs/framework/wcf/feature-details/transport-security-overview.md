---
title: Panoramica sulla sicurezza del trasporto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 00959326-aa9d-44d0-af61-54933d4adc7f
ms.openlocfilehash: f30b2c587d7f9b21c1f19fa1c3943621fc2607cd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184333"
---
# <a name="transport-security-overview"></a>Panoramica sulla sicurezza del trasporto
I meccanismi di sicurezza del trasporto in Windows Communication Foundation (WCF) dipendono dall'associazione e dal trasporto in uso. Ad esempio, quando si utilizza la classe <xref:System.ServiceModel.WSHttpBinding>, il trasporto è HTTP e il meccanismo principale per la sicurezza del trasporto è SSL (Secure Sockets Layer) su HTTP, comunemente noto come HTTP. In questo argomento vengono illustrati i principali meccanismi di sicurezza del trasporto utilizzati nelle associazioni fornite dal sistema WCF.  
  
> [!NOTE]
> Quando la sicurezza SSL viene utilizzata con .NET Framework 3.5 e versioni successive, un client WCF utilizza sia i certificati intermedi nel relativo archivio certificati che i certificati intermedi ricevuti durante la negoziazione SSL per eseguire la convalida della catena di certificati nel servizio Certificato. In .NET Framework 3.0 vengono usati solo i certificati intermedi installati nell'archivio certificati locale.  
  
> [!WARNING]
> Quando viene utilizzata la sicurezza del trasporto, è possibile che la proprietà <xref:System.Threading.Thread.CurrentPrincipal%2A?displayProperty=nameWithType> venga sovrascritta. Per evitare che <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A?displayProperty=nameWithType> ciò accada, impostare il su <xref:System.ServiceModel.Description.PrincipalPermissionMode.None?displayProperty=nameWithType>. <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> è un comportamento del servizio che può essere impostato sulla descrizione del servizio.  
  
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
 Questo tipo corrisponde al metodo di autenticazione di base di IIS. Quando si utilizza questa modalità, il server IIS deve essere configurato con gli account utente di Windows e le autorizzazioni del file system NTFS appropriate. Per ulteriori informazioni su IIS 6.0, vedere [Abilitazione dell'autenticazione di base e Configurazione del nome dell'area di autenticazione](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc785293(v=ws.10)). Per ulteriori informazioni su IIS 7.0, vedere [Configure Basic Authentication (IIS 7)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772009(v=ws.10)).  
  
#### <a name="certificate"></a>Certificato  
 In IIS è disponibile un'opzione affinché i client debbano eseguire l'accesso con un certificato. Questa funzionalità consente inoltre di eseguire il mapping di un certificato client a un account di Windows. Per ulteriori informazioni su IIS 6.0, vedere [Abilitazione dei certificati client in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc727994(v=ws.10)). Per ulteriori informazioni su IIS 7.0, vedere [Configurazione dei certificati server in IIS 7](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).  
  
#### <a name="digest"></a>Digest  
 L'autenticazione digest è simile all'autenticazione di base, ma offre il vantaggio di inviare le credenziali come un hash, anziché in testo non crittografato. Per ulteriori informazioni su IIS 6.0, vedere [Autenticazione del digest in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc782661(v=ws.10)). Per ulteriori informazioni su IIS 7.0, vedere [Configure Digest Authentication (IIS 7)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc754104(v=ws.10)).  
  
#### <a name="windows"></a>Windows  
 Questo tipo corrisponde al metodo di autenticazione integrata di Windows di IIS. In caso di impostazione su questo valore, si prevede inoltre che il server sia in un dominio Windows che utilizza il protocollo Kerberos come controller di dominio. Se il server non è in un dominio con supporto Kerberos o se il sistema Kerberos ha esito negativo, è possibile utilizzare il valore NTLM (NT LAN Manager) descritto nella sezione successiva. Per ulteriori informazioni su IIS 6.0, vedere [Autenticazione integrata di Windows in IIS 6.0](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc738016(v=ws.10)). Per ulteriori informazioni su IIS 7.0, vedere [Configurazione dei certificati server in IIS 7](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10)).
  
#### <a name="ntlm"></a>NTLM  
 Consente al server di utilizzare NTLM per l'autenticazione se il protocollo Kerberos ha esito negativo. Per ulteriori informazioni sulla configurazione di IIS in IIS 6.0, vedere [Forzatura dell'autenticazione NTLM](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc786486(v=ws.10)). Per IIS 7.0, l'autenticazione di Windows include l'autenticazione NTLM. Per altre informazioni, vedere [Configuring Server Certificates in IIS 7](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732230(v=ws.10))(Configurazione dei certificati del server in IIS 7).
  
## <a name="wshttpbinding"></a>WsHttpBinding  
 La classe <xref:System.ServiceModel.WSHttpBinding> è progettata per essere interoperabile con i servizi che implementano le specifiche WS - *. La sicurezza basata sul trasporto di questa associazione è SSL (Secure Sockets Layer) su HTTP, ovvero HTTPS. Per creare un'applicazione WCF che utilizza SSL, utilizzare IIS per ospitare l'applicazione. In alternativa, se si sta creando un'applicazione indipendente, utilizzare lo strumento HttpCfg.exe per associare un certificato X.509 a una porta specifica in un computer. Il numero di porta viene specificato come parte dell'applicazione WCF come indirizzo endpoint. Quando si utilizza la modalità di trasporto, l'indirizzo dell'endpoint deve includere il protocollo HTTPS; in caso contrario verrà generata un'eccezione in fase di esecuzione. Per ulteriori informazioni, vedere [Protezione del trasporto HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
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
> Se si utilizza la sicurezza di Windows, non è necessario un certificato.  
  
 Nel codice seguente viene utilizzata l'identificazione digitale del certificato, che lo identifica in modo univoco. Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
 [!code-csharp[c_ProgrammingSecurity#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#13)]
 [!code-vb[c_ProgrammingSecurity#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#13)]  
  
 In alternativa, specificare il certificato nella [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) configurazione del client usando un elemento clientCredentials>nella sezione behaviors.  
  
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
 Quando si utilizza la sicurezza del trasporto, in questa associazione viene utilizzato SSL su HTTP, noto come HTTPS, con un token emesso (<xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential>). Per ulteriori informazioni sulle applicazioni federative, vedere [Federazione e token emessi](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md).  
  
## <a name="netpeertcpbinding"></a>NetPeerTcpBinding  
 La classe <xref:System.ServiceModel.NetPeerTcpBinding> costituisce un trasporto protetto progettato per consentire una comunicazione efficiente utilizzando la funzionalità di rete peer-to-peer. Come indicato dal nome della classe e dell'associazione, il protocollo è TCP. Quando la modalità di sicurezza è impostata su Trasporto, l'associazione implementa TLS su TCP. Per ulteriori informazioni sulla funzionalità peer-to-peer, vedere [Peer-to-Peer Networking](../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).  
  
## <a name="msmqintegrationbinding-and-netmsmqbinding"></a>MsmqIntegrationBinding e NetMsmqBinding  
 Per una descrizione completa della protezione del trasporto con Accodamento messaggi (precedentemente denominato MSMQ), vedere [Protezione dei messaggi mediante](../../../../docs/framework/wcf/feature-details/securing-messages-using-transport-security.md)la protezione del trasporto .  
  
## <a name="see-also"></a>Vedere anche

- [Programmazione delle funzionalità di sicurezza di WCF](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
