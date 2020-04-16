---
title: 'Procedura: creare un token di contesto di sicurezza per una sessione sicura'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
ms.openlocfilehash: 4e91580035d4de23ae90cd0d59a08f321ae70a1c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464145"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a>Procedura: creare un token di contesto di sicurezza per una sessione sicura
Per evitare la perdita di una determinata sessione protetta quando il servizio viene riciclato, è possibile utilizzare in tale sessione un token di contesto di sicurezza (SCT, Security Context Token) con stato. Ad esempio, quando in una sessione protetta si utilizza un token SCT senza stato e si reimposta Internet Information Services (IIS), i dati di sessione associati al servizio vengono persi. Questi dati di sessione comprendono una cache del token SCT. Pertanto, quando un client invia al servizio un token SCT senza stato, viene restituito un errore, in quanto risulta impossibile recuperare la chiave associata al token SCT. Se tuttavia si utilizza un token SCT con stato, la relativa chiave associata è contenuta nel token SCT e quindi nel messaggio. Ne consegue che in questo caso il riciclo del servizio non influisce sulla sessione protetta. Per impostazione predefinita, Windows Communication Foundation (WCF) utilizza SCT senza stato in una sessione protetta. In questo argomento viene descritto in modo dettagliato come utilizzare token SCT con stato in una sessione protetta.  
  
> [!NOTE]
> I token SCT con stato non possono essere utilizzati in una sessione protetta che prevede un contratto derivato dall'interfaccia <xref:System.ServiceModel.Channels.IDuplexChannel>.  
  
> [!NOTE]
> Nelle applicazioni che utilizzano token SCT con stato in una sessione protetta, l'ID del thread del servizio deve essere un account utente a cui è stato associato un profilo utente. Quando il servizio viene eseguito nel contesto di un account privo di profilo utente, ad esempio `Local Service`, è possibile che venga generata un'eccezione.  
  
> [!NOTE]
> Quando la rappresentazione è obbligatoria in Windows XP, utilizzare una sessione protetta priva di token SCT con stato. Infatti, quando i token SCT con stato vengono utilizzati con la rappresentazione, il sistema genera un'eccezione <xref:System.InvalidOperationException>. Per ulteriori informazioni, vedere [Scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a>Per utilizzare token SCT con stato in una sessione protetta  
  
- Creare un'associazione personalizzata che prevede la protezione dei messaggi SOAP mediante una sessione protetta che utilizza un token SCT con stato.  
  
    1. Definire un'associazione personalizzata, aggiungendo un [ \<>customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) al file di configurazione per il servizio.  
  
        ```xml  
        <customBinding>  
        </customBinding>
        ```  
  
    2. Aggiungere [ \<](../../configure-apps/file-schema/wcf/bindings.md) un elemento figlio>di associazione all'>[ \<customBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Specificare il nome dell'associazione impostando l'attributo `name` su un nome univoco all'interno del file di configurazione.  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        </binding>
        ```  
  
    3. Specificare la modalità di autenticazione per [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) i messaggi inviati da e verso questo servizio aggiungendo un elemento figlio di>di sicurezza all'>[ \<customBinding ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).  
  
         Specificare l'utilizzo di una sessione protetta impostando l'attributo `authenticationMode` su `SecureConversation`. Specificare l'utilizzo di token SCT con stato impostando l'attributo `requireSecurityContextCancellation` su `false`.  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">
        </security>
        ```  
  
    4. Specificare la modalità di autenticazione del client mentre viene stabilita [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)la sessione protetta aggiungendo un [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) elemento figlio secureConversationBootstrap>all'elemento figlio security>.  
  
         Specificare la modalità di autenticazione del client impostando l'attributo `authenticationMode`.  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5. Specificare la codifica del messaggio aggiungendo [ \< ](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)un elemento di codifica, ad esempio textMessageEncoding>.  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6. Specificare il trasporto aggiungendo un elemento di trasporto, ad esempio [ \<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).  
  
        ```xml  
        <httpTransport />  
        ```  
  
     Nell'esempio di codice seguente si utilizza la configurazione per specificare un'associazione personalizzata in cui i messaggi possono utilizzare token SCT con stato in una sessione protetta.  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene creata un'associazione personalizzata che usa la modalità di autenticazione <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> per l'avvio automatico di una sessione protetta.  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 Quando l'autenticazione di Windows viene utilizzata in combinazione <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> con un SCT con stato, WCF non popola la proprietà con l'identità del chiamante effettivo, ma imposta invece la proprietà su anonima. Poiché la sicurezza WCF deve ricreare il contenuto del contesto di sicurezza del servizio per ogni richiesta dall'SCT in ingresso, il server non tiene traccia della sessione di sicurezza nella memoria. Inoltre, poiché è impossibile serializzare l'istanza della classe <xref:System.Security.Principal.WindowsIdentity> nel token SCT, la proprietà <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> restituisce un'identità anonima.  
  
 Questo comportamento viene illustrato nella configurazione seguente.  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
        </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a>Vedere anche

- [\<>customBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
