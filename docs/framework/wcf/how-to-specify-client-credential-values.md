---
title: 'Procedura: Specificare valori di credenziali client'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: a1b2627c8e9899a122f27dc652f8c91230fed0b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225131"
---
# <a name="how-to-specify-client-credential-values"></a>Procedura: Specificare valori di credenziali client
Utilizza Windows Communication Foundation (WCF), il servizio può specificare come un client viene autenticato nel servizio. Ad esempio, un servizio può stabilire che il client venga autenticato con un certificato.  
  
### <a name="to-determine-the-client-credential-type"></a>Per determinare il tipo di credenziale client  
  
1.  Recuperare i metadati dall'endpoint dei metadati di servizio. I metadati sono in genere costituiti da due file: il codice client del linguaggio di programmazione selezionato (l'impostazione predefinita è Visual C#) e un file di configurazione XML. Un modo per recuperare i metadati consiste nell'utilizzare lo strumento Svcutil.exe per restituire il codice e la configurazione client. Per altre informazioni, vedere [recupero di metadati](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) e [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Aprire il file di configurazione XML. Se si utilizza lo strumento Svcutil.exe, il nome predefinito del file è Output.config.  
  
3.  Trovare il  **\<sicurezza >** elemento con il **modalità** attributo (**< modalità di sicurezza =** `MessageOrTransport` **>** in cui `MessageOrTransport` è impostato su una delle modalità di sicurezza.  
  
4.  Trovare l'elemento figlio che corrisponda al valore della modalità. Ad esempio, se la modalità è impostata su **messaggi**, trovare il  **\<messaggio >** elemento contenuto nel  **\<sicurezza >** elemento.  
  
5.  Si noti il valore assegnato per il **clientCredentialType** attributo. Il valore effettivo dipende dalla modalità utilizzata, trasporto o messaggio.  
  
 Nel codice XML seguente viene mostrata la configurazione di un client per cui viene utilizzata la sicurezza dei messaggi e viene richiesto un certificato per autenticare il client.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Esempio: Modalità di trasporto TCP con certificato come credenziale Client  
 In questo esempio la modalità di sicurezza viene impostata sulla modalità Trasporto e il valore delle credenziali client su un certificato X.509. Nelle procedure seguenti viene descritto come impostare il valore delle credenziali client sul client nel codice e nella configurazione. Ciò presuppone che sia stato usato il [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per restituire i metadati (codice e configurazione) dal servizio. Per altre informazioni, vedere [Procedura: Creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>Per specificare il valore delle credenziali client nel client nel codice  
  
1.  Usare la [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare il codice e la configurazione dal servizio.  
  
2.  Creare un'istanza del client WCF usando il codice generato.  
  
3.  Nella classe del client impostare la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> su un valore appropriato. In questo esempio la proprietà viene impostata su un certificato X.509 utilizzando il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     È possibile utilizzare qualsiasi enumerazione della classe <xref:System.Security.Cryptography.X509Certificates.X509FindType>. Il nome del soggetto viene qui utilizzato nel caso in cui il certificato venga modificato (a causa di una data di scadenza). L'utilizzo del nome del soggetto consente all'infrastruttura di cercare nuovamente il certificato.  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>Per specificare il valore delle credenziali client nel client nella configurazione  
  
1.  Aggiungere un [ \<comportamento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento per il [ \<comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
2.  Aggiungere un [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento per il [ \<comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento. Avere cura di impostare l'attributo `name` obbligatorio su un valore appropriato.  
  
3.  Aggiungere un [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elemento per il [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.  
  
4.  Impostare gli attributi seguenti sui valori appropriati: `storeLocation`, `storeName`, `x509FindType` e `findValue`, come illustrato nel codice seguente. Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
    ```xml  
    <behaviors>  
       <endpointBehaviors>  
          <behavior name="endpointCredentialBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="Contoso.com"   
                                 storeLocation="LocalMachine"  
                                 storeName="TrustedPeople"  
                                 x509FindType="FindBySubjectName" />  
            </clientCredentials>  
          </behavior>  
       </endpointBehaviors>  
    </behaviors>  
    ```  
  
5.  Quando si configura il client, specificare il comportamento impostando l'attributo `behaviorConfiguration` dell'elemento `<endpoint>`, come illustrato nel codice seguente. L'elemento endpoint è figlio di [ \<client >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento. Specificare inoltre il nome della configurazione dell'associazione impostando l'attributo `bindingConfiguration` sull'associazione per il client. Se si utilizza un file di configurazione generato, il nome dell'associazione viene generato automaticamente. In questo esempio il nome è `"tcpBindingWithCredential"`.  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [Programmazione delle funzionalità di sicurezza di WCF](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)
- [Selezione di un tipo di credenziale](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [Utilizzo dei certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Procedura: Creare un client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)
- [\<security>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [\<messaggio >](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
- [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
