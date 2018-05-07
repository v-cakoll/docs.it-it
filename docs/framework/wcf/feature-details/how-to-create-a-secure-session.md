---
title: 'Procedura: creare una sessione protetta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ce351a87e70b09a2f68654af817e28fa3145d79d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-secure-session"></a>Procedura: creare una sessione protetta
Ad eccezione del [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, le associazioni fornite dal sistema in Windows Communication Foundation (WCF) usano sessioni protette quando è abilitata la protezione dei messaggi.  
  
 Per impostazione predefinita, le sessioni protette non restano attive quando un server Web viene riciclato. Quando si stabilisce una sessione protetta, il client e il servizio memorizzano nella cache la chiave associata alla sessione protetta. Durante lo scambio dei messaggi, viene scambiato solo un identificatore della chiave memorizzata nella cache. Se il server Web viene riciclato, anche la cache viene riciclata, pertanto il server Web non può recuperare la chiave memorizzata nella cache per l'identificatore. In questo caso, al client viene restituita un'eccezione. Le sessioni protette che usano un token del contesto di sicurezza (SCT) con stato possono restare attive quando un server Web viene riciclato. Per ulteriori informazioni sull'utilizzo di un token SCT con stato in una sessione protetta, vedere [procedura: creare un Token di contesto di sicurezza per una sessione protetta](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>Per specificare che un servizio usa sessioni protette mediante una delle associazioni fornite dal sistema  
  
-   Configurare un servizio per l'uso di un'associazione fornita dal sistema che supporta la protezione dei messaggi.  
  
     Ad eccezione del [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, quando le associazioni fornite dal sistema sono configurate per usare automaticamente la protezione dei messaggi WCF Usa sessioni protette. Nella tabella seguente vengono elencate le associazioni fornite dal sistema che supportano la protezione dei messaggi e viene indicato se la protezione del messaggio è il meccanismo di sicurezza predefinito.  
  
    |Binding fornito dal sistema|Elemento Configuration|Sicurezza dei messaggi attivata per impostazione predefinita|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|No|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Yes|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Yes|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Yes|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|No|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|No|  
  
     Esempio di codice seguente utilizza la configurazione per specificare un'associazione denominata `wsHttpBinding_Calculator` che utilizza il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), protezione dei messaggi e proteggere le sessioni.  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     Esempio di codice seguente specifica che il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), protezione dei messaggi e proteggere le sessioni vengono utilizzate per proteggere il `secureCalculator` servizio.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Possano disattivare le sessioni protette per la [ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) impostando il `establishSecurityContext` attributo `false`. Per le altre associazioni fornite dal sistema, è possibile disattivare le sessioni protette solo creando un'associazione personalizzata.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>Per specificare che un servizio usa sessioni protette mediante un'associazione personalizzata  
  
-   Creare un'associazione personalizzata che specifica che i messaggi SOAP sono protetti mediante una sessione protetta.  
  
     Per ulteriori informazioni sulla creazione di un'associazione personalizzata, vedere [procedura: personalizzare un'associazione fornite dal sistema](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
     Nell'esempio di codice seguente viene usata la configurazione per specificare un'associazione personalizzata che protegge i messaggi mediante una sessione protetta.  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     Nell'esempio di codice seguente viene creata un'associazione personalizzata che usa la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> per l'avvio automatico di una sessione protetta.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica delle associazioni WCF](../../../../docs/framework/wcf/bindings-overview.md)
