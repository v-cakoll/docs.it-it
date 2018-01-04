---
title: 'Procedura: specificare valori di credenziali client'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cd818a2342ff5b44e4e8ab1b237f7c657d3bf438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-client-credential-values"></a>Procedura: specificare valori di credenziali client
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] consente al servizio di specificare la modalità di autenticazione di un client nel servizio. Ad esempio, un servizio può stabilire che il client venga autenticato con un certificato.  
  
### <a name="to-determine-the-client-credential-type"></a>Per determinare il tipo di credenziale client  
  
1.  Recuperare i metadati dall'endpoint dei metadati di servizio. I metadati sono in genere costituiti da due file: il codice client del linguaggio di programmazione selezionato (l'impostazione predefinita è Visual C#) e un file di configurazione XML. Un modo per recuperare i metadati consiste nell'utilizzare lo strumento Svcutil.exe per restituire il codice e la configurazione client. Per ulteriori informazioni, vedere [recupero di metadati](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) e [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
2.  Aprire il file di configurazione XML. Se si utilizza lo strumento Svcutil.exe, il nome predefinito del file è Output.config.  
  
3.  Trovare il  **\<sicurezza >** elemento con la **modalità** attributo (**< modalità di sicurezza =** `MessageOrTransport`  **>**  dove `MessageOrTransport` è impostata su una delle modalità di sicurezza.  
  
4.  Trovare l'elemento figlio che corrisponda al valore della modalità. Ad esempio, se la modalità è impostata su **messaggio**, trovare il  **\<messaggio >** contenuto nell'elemento di  **\<sicurezza >** elemento.  
  
5.  Si noti il valore assegnato al **clientCredentialType** attributo. Il valore effettivo dipende dalla modalità utilizzata, trasporto o messaggio.  
  
 Nel codice XML seguente viene mostrata la configurazione di un client per cui viene utilizzata la sicurezza dei messaggi e viene richiesto un certificato per autenticare il client.  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a>Esempio: Modalità di trasporto TCP con certificato come credenziale client  
 In questo esempio la modalità di sicurezza viene impostata sulla modalità Trasporto e il valore delle credenziali client su un certificato X.509. Nelle procedure seguenti viene descritto come impostare il valore delle credenziali client sul client nel codice e nella configurazione. Si presuppone che si usa il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per restituire i metadati (codice e la configurazione) dal servizio. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Procedura: creare un Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a>Per specificare il valore delle credenziali client nel client nel codice  
  
1.  Utilizzare il [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) per generare codice e la configurazione dal servizio.  
  
2.  Crea un'istanza del client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] utilizzando il codice generato.  
  
3.  Nella classe del client impostare la proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601> su un valore appropriato. In questo esempio la proprietà viene impostata su un certificato X.509 utilizzando il metodo <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> della classe <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     È possibile utilizzare qualsiasi enumerazione della classe <xref:System.Security.Cryptography.X509Certificates.X509FindType>. Il nome del soggetto viene qui utilizzato nel caso in cui il certificato venga modificato (a causa di una data di scadenza). L'utilizzo del nome del soggetto consente all'infrastruttura di cercare nuovamente il certificato.  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a>Per specificare il valore delle credenziali client nel client nella configurazione  
  
1.  Aggiungere un [ \<comportamento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) elemento per il [ \<comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.  
  
2.  Aggiungere un [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento per il [ \<comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento. Avere cura di impostare l'attributo `name` obbligatorio su un valore appropriato.  
  
3.  Aggiungere un [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) elemento per il [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.  
  
4.  Impostare gli attributi seguenti sui valori appropriati: `storeLocation`, `storeName`, `x509FindType` e `findValue`, come illustrato nel codice seguente. [!INCLUDE[crabout](../../../includes/crabout-md.md)]i certificati, vedere [utilizzo dei certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md).  
  
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
  
5.  Quando si configura il client, specificare il comportamento impostando l'attributo `behaviorConfiguration` dell'elemento `<endpoint>`, come illustrato nel codice seguente. L'endpoint è un elemento figlio del [ \<client >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) elemento. Specificare inoltre il nome della configurazione dell'associazione impostando l'attributo `bindingConfiguration` sull'associazione per il client. Se si utilizza un file di configurazione generato, il nome dell'associazione viene generato automaticamente. In questo esempio il nome è `"tcpBindingWithCredential"`.  
  
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
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [Programmazione delle funzionalità di sicurezza di WCF](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [Selezione di un tipo di credenziale](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [Strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Uso di certificati](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Procedura: Creare un client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [\<netTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [\<sicurezza >](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [\<messaggio >](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [\<comportamento >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [\<i comportamenti >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [\<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [\<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
