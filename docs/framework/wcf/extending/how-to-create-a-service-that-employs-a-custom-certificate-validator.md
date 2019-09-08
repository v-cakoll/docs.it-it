---
title: 'Procedura: Creare un servizio che usa un validator del certificato personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: b2407c293de7f11b90586f5a55bd759a4ea734aa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795687"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a>Procedura: Creare un servizio che usa un validator del certificato personalizzato
In questo argomento viene illustrato come implementare un validator del certificato personalizzato e come configurare le credenziali del client o del servizio per sostituire la logica di convalida del certificato predefinita con il validator del certificato personalizzato.  
  
 Se il certificato X. 509 viene usato per autenticare un client o un servizio, per impostazione predefinita Windows Communication Foundation (WCF) usa l'archivio certificati di Windows e l'API Crypto per convalidare il certificato e verificare che sia attendibile. A volte la funzionalità di convalida del certificato predefinita non è sufficiente e deve essere modificata. WCF fornisce un modo semplice per modificare la logica di convalida consentendo agli utenti di aggiungere un validator del certificato personalizzato. Se viene specificato un validator del certificato personalizzato, WCF non usa la logica di convalida del certificato incorporata, ma si basa invece sul validator personalizzato.  
  
## <a name="procedures"></a>Procedure  
  
#### <a name="to-create-a-custom-certificate-validator"></a>Per creare un validator del certificato personalizzato  
  
1. Definire una nuova classe derivata da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
2. Implementare il metodo astratto <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>. Il certificato che deve essere convalidato viene passato come argomento al metodo. Se il certificato passato non è valido in base alla logica di convalida, questo metodo genera un'eccezione <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>. Se il certificato è valido, il metodo viene restituito al chiamante.  
  
    > [!NOTE]
    > Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a>Per specificare un validator del certificato personalizzato nella configurazione del servizio  
  
1. Aggiungere un [ \<elemento behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) e un [ \<> serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' [ \<elemento > System. ServiceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) .  
  
2. Aggiungere un [ \<comportamento >](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare l' `name` attributo su un valore appropriato.  
  
3. Aggiungere [ \<](../../configure-apps/file-schema/wcf/servicecredentials.md) un`<behavior>` > ServiceCredentials all'elemento.  
  
4. Aggiungere un elemento `<clientCertificate>` all'elemento `<serviceCredentials>`.  
  
5. Aggiungere [ \<](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) un`<clientCertificate>` > di autenticazione all'elemento.  
  
6. Impostare l'attributo `customCertificateValidatorType` sul tipo di validator. Nell'esempio seguente viene impostato l'attributo sullo spazio dei nomi e sul nome del tipo.  
  
7. Impostare l'attributo `certificateValidationMode` su `Custom`.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <serviceBehaviors>  
        <behavior name="ServiceBehavior">  
         <serviceCredentials>  
          <clientCertificate>  
          <authentication certificateValidationMode="Custom" customCertificateValidatorType="Samples.MyValidator, service" />  
          </clientCertificate>  
         </serviceCredentials>  
        </behavior>  
       </serviceBehaviors>  
      </behaviors>  
    </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a>Per specificare un validator del certificato personalizzato mediante configurazione sul client  
  
1. Aggiungere un [ \<elemento behaviors >](../../configure-apps/file-schema/wcf/behaviors.md) e un [ \<> serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' [ \<elemento > System. ServiceModel](../../configure-apps/file-schema/wcf/system-servicemodel.md) .  
  
2. Aggiungere un [ \<elemento > endpointBehaviors](../../configure-apps/file-schema/wcf/endpointbehaviors.md) .  
  
3. Aggiungere un elemento `<behavior>` e impostare l'attributo `name` su un valore appropriato.  
  
4. Aggiungere un [ \<elemento ClientCredentials >](../../configure-apps/file-schema/wcf/clientcredentials.md) .  
  
5. Aggiungere un [ \<> ServiceCertificate](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).  
  
6. Aggiungere un [ \<> di autenticazione](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) come illustrato nell'esempio seguente.  
  
7. Impostare l'attributo `customCertificateValidatorType` sul tipo di validator.  
  
8. Impostare l'attributo `certificateValidationMode` su `Custom`. Nell'esempio seguente viene impostato l'attributo sullo spazio dei nomi e sul nome del tipo.  
  
    ```xml  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
       <endpointBehaviors>  
        <behavior name="clientBehavior">  
         <clientCredentials>  
          <serviceCertificate>  
           <authentication certificateValidationMode="Custom"   
                  customCertificateValidatorType=  
             "Samples.CustomX509CertificateValidator, client"/>  
          </serviceCertificate>  
         </clientCredentials>  
        </behavior>  
       </endpointBehaviors>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a>Per specificare un validator del certificato personalizzato mediante il codice sul servizio  
  
1. Specificare il validator del certificato personalizzato sulla proprietà <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>. È possibile accedere alle credenziali del servizio mediante la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.  
  
2. Impostare la proprietà <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a>Per specificare un validator del certificato personalizzato mediante il codice sul client  
  
1. Specificare il validator del certificato personalizzato mediante la proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>. È possibile accedere alle credenziali del client mediante la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>. La classe client generata dallo [strumento ServiceModel Metadata Utility Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) deriva sempre dalla <xref:System.ServiceModel.ClientBase%601> classe.  
  
2. Impostare la proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
 Nell'esempio seguente viene illustrata un'implementazione di un validator del certificato personalizzato e l'uso sul servizio.  
  
### <a name="code"></a>Codice  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
