---
title: Protezione del trasporto con l'autenticazione di base
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
author: BrucePerlerMS
ms.openlocfilehash: 4a6ad2746bea9dfea1999e272796d44f0341e64d
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47082344"
---
# <a name="transport-security-with-basic-authentication"></a>Protezione del trasporto con l'autenticazione di base
La figura seguente mostra un servizio Windows Communication Foundation (WCF) e un client. Il server richiede un certificato X.509 valido che possa essere usato per SSL (Secure Sockets Layer) e i client devono ritenere attendibile il certificato del server. Il servizio Web dispone già di un'implementazione SSL usabile. Per altre informazioni sull'abilitazione dell'autenticazione base in Internet Information Services (IIS), vedere [ https://go.microsoft.com/fwlink/?LinkId=83822 ](https://go.microsoft.com/fwlink/?LinkId=83822).  
  
 ![Sicurezza del trasporto con autenticazione di base](../../../../docs/framework/wcf/feature-details/media/securedbyusername.gif "SecuredbyUsername")  
  
|Caratteristica|Descrizione|  
|--------------------|-----------------|  
|Modalità di sicurezza|Trasporto|  
|Interoperabilità|Con servizi e client di servizi Web esistenti|  
|Autenticazione (server)<br /><br /> Autenticazione (client)|Sì (usando HTTPS)<br /><br /> Sì (usando nome utente/password).|  
|Integrità|Sì|  
|Riservatezza|Sì|  
|Trasporto|HTTPS|  
|Binding|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a>Servizio  
 Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente. Eseguire una delle operazioni seguenti:  
  
-   Creare un servizio autonomo usando il codice senza alcuna configurazione.  
  
-   Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.  
  
### <a name="code"></a>Codice  
 Nel codice seguente viene illustrato come creare un endpoint del servizio che usa un nome utente del dominio di Windows e una password per la protezione del trasferimento. Si noti che il servizio richiede un certificato X.509 per autenticare il client. Per altre informazioni, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) e [procedura: configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a>Configurazione  
 Gli elementi seguenti configurano un servizio per l'uso dell'autenticazione di base con protezione a livello di trasporto:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"   
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"   
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a>Client  
  
### <a name="code"></a>Codice  
 Nell'esempio di codice seguente viene mostrato il codice client che include il nome utente e la password. Si noti che l'utente deve fornire un nome utente e una password di Windows validi. Il codice per restituire il nome utente e la password non è incluso. Usare una finestra di dialogo o un'altra interfaccia per eseguire una query per ottenere tali informazioni dall'utente.  
  
> [!NOTE]
>  Nome utente e password possono essere impostati solo tramite codice.  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a>Configurazione  
 Nel codice seguente viene mostrata la configurazione client.  
  
> [!NOTE]
>  Non è possibile usare la configurazione per impostare il nome utente e la password. La configurazione mostrata deve essere ampliata usando il codice per impostare il nome utente e la password.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"   
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 [Uso di certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Procedura: Configurare una porta con un certificato SSL](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)  
 [Panoramica della sicurezza](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)  
 [Modello di sicurezza per Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
