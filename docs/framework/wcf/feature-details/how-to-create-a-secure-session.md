---
title: 'Procedura: creare una sessione protetta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: 80973a31050cf1ede03d4a3919066c62625ae590
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593412"
---
# <a name="how-to-create-a-secure-session"></a>Procedura: creare una sessione protetta
Ad eccezione dell' [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) associazione, le associazioni fornite dal sistema in Windows Communication Foundation (WCF) utilizzano automaticamente le sessioni protette quando è abilitata la sicurezza dei messaggi.  
  
 Per impostazione predefinita, le sessioni protette non restano attive quando un server Web viene riciclato. Quando si stabilisce una sessione protetta, il client e il servizio memorizzano nella cache la chiave associata alla sessione protetta. Durante lo scambio dei messaggi, viene scambiato solo un identificatore della chiave memorizzata nella cache. Se il server Web viene riciclato, anche la cache viene riciclata, pertanto il server Web non può recuperare la chiave memorizzata nella cache per l'identificatore. In questo caso, al client viene restituita un'eccezione. Le sessioni protette che usano un token del contesto di sicurezza (SCT) con stato possono restare attive quando un server Web viene riciclato. Per altre informazioni sull'uso di un token SCT con stato in una sessione protetta, vedere [procedura: creare un token del contesto di sicurezza per una sessione protetta](how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>Per specificare che un servizio usa sessioni protette mediante una delle associazioni fornite dal sistema  
  
- Configurare un servizio per l'uso di un'associazione fornita dal sistema che supporta la protezione dei messaggi.  
  
     Ad eccezione dell' [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) associazione, quando le associazioni fornite dal sistema sono configurate per l'utilizzo della sicurezza dei messaggi, WCF utilizza automaticamente le sessioni protette. Nella tabella seguente vengono elencate le associazioni fornite dal sistema che supportano la protezione dei messaggi e viene indicato se la protezione del messaggio è il meccanismo di sicurezza predefinito.  
  
    |Associazione fornita dal sistema|Elemento di configurazione|Sicurezza dei messaggi attivata per impostazione predefinita|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)|No|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)|Sì|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Sì|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Sì|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)|No|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)|No|  
  
     Nell'esempio di codice riportato di seguito viene utilizzata la configurazione per specificare un'associazione denominata `wsHttpBinding_Calculator` che utilizza [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , la sicurezza dei messaggi e le sessioni protette.  
  
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
  
     Nell'esempio di codice riportato di seguito [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) viene specificato che, per proteggere il servizio, vengono utilizzate la sicurezza del messaggio e le sessioni protette `secureCalculator` .  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > Le sessioni protette possono essere disattivate impostando [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) l' `establishSecurityContext` attributo su `false` . Per le altre associazioni fornite dal sistema, è possibile disattivare le sessioni protette solo creando un'associazione personalizzata.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>Per specificare che un servizio usa sessioni protette mediante un'associazione personalizzata  
  
- Creare un'associazione personalizzata che specifica che i messaggi SOAP sono protetti mediante una sessione protetta.  
  
     Per ulteriori informazioni sulla creazione di un'associazione personalizzata, vedere [procedura: personalizzare un'associazione fornita dal sistema](../extending/how-to-customize-a-system-provided-binding.md).  
  
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

- [Panoramica delle associazioni WCF](../bindings-overview.md)
