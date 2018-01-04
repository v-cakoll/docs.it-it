---
title: 'Procedura: creare un gestore autorizzazioni personalizzato per un servizio'
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
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1977a26f3185ad1ef85584b0da7d63826b7f93ea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a>Procedura: creare un gestore autorizzazioni personalizzato per un servizio
L'infrastruttura dei modelli di identità di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] supporta un modello di autorizzazione basato su attestazioni estensibili. Le attestazioni vengono estratte dai token, elaborate facoltativamente da criteri di autorizzazione personalizzati e quindi inserite in una classe <xref:System.IdentityModel.Policy.AuthorizationContext>. Un gestore autorizzazioni esamina le attestazioni contenute nel contesto <xref:System.IdentityModel.Policy.AuthorizationContext> per prendere decisioni di autorizzazione.  
  
 Per impostazione predefinita, le decisioni di autorizzazione sono prese dalla classe <xref:System.ServiceModel.ServiceAuthorizationManager>. È tuttavia possibile creare un gestore autorizzazioni personalizzato per eseguire l'override di queste decisioni. Per creare un gestore autorizzazioni personalizzato, creare una classe che deriva da <xref:System.ServiceModel.ServiceAuthorizationManager> e che implementa il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Le decisioni di autorizzazione sono prese tramite il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> che restituisce `true` quando l'accesso è concesso e `false` quando l'accesso è negato.  
  
 Se la decisione di autorizzazione dipende dal contenuto del corpo del messaggio, utilizzare il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.  
  
 A causa di problemi riguardanti le prestazioni, è consigliabile ridisegnare l'applicazione, se possibile, in modo tale che per la decisione di autorizzazione non sia necessario l'accesso al corpo del messaggio.  
  
 La registrazione del gestore autorizzazioni personalizzato per un servizio può essere eseguita in codice o in configurazione.  
  
### <a name="to-create-a-custom-authorization-manager"></a>Per creare un gestore autorizzazioni personalizzato  
  
1.  Derivare una classe dalla classe <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.  
  
     Utilizzare il contesto <xref:System.ServiceModel.OperationContext> passato al metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> per prendere decisioni di autorizzazione.  
  
     Nell'esempio di codice seguente il metodo <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> viene utilizzato per individuare l'attestazione personalizzata `http://www.contoso.com/claims/allowedoperation` allo scopo di prendere una decisione di autorizzazione.  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a>Per registrare un gestore autorizzazioni personalizzato in codice  
  
1.  Creare un'istanza del gestore autorizzazioni personalizzato e assegnarla alla proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.  
  
     Per accedere al comportamento <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> è possibile utilizzare la proprietà <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.  
  
     Nell'esempio di codice seguente viene illustrato come registrare il gestore autorizzazioni personalizzato `MyServiceAuthorizationManager`.  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a>Per registrare un gestore autorizzazioni personalizzato in configurazione  
  
1.  Aprire il file di configurazione del servizio.  
  
2.  Aggiungere un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per il [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
     Per il [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), aggiungere un `serviceAuthorizationManagerType` attributo e impostarne il valore per il tipo che rappresenta il gestore autorizzazioni personalizzato.  
  
3.  Aggiungere un'associazione in grado di proteggere la comunicazione tra client e servizio.  
  
     L'associazione scelta per questa comunicazione determina le attestazioni aggiunte al contesto <xref:System.IdentityModel.Policy.AuthorizationContext> utilizzate dal gestore autorizzazioni personalizzato per prendere le decisioni di autorizzazione. Per ulteriori informazioni sulle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
4.  Associare il comportamento a un endpoint di servizio, aggiungendo un [ \<servizio >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) elemento e impostare il valore della `behaviorConfiguration` attributo sul valore dell'attributo del nome per il [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.  
  
     Per ulteriori informazioni sulla configurazione di un endpoint del servizio, vedere [procedura: creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
     Nell'esempio di codice seguente viene illustrato come registrare il gestore autorizzazioni personalizzato `Samples.MyServiceAuthorizationManager`.  
  
    ```xml  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.CalculatorService"  
              behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <endpoint address=""  
                      binding="wsHttpBinding_Calculator"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <WSHttpBinding>  
           <binding name = "wsHttpBinding_Calculator">  
             <security mode="Message">  
               <message clientCredentialType="Windows"/>  
             </security>  
            </binding>  
          </WSHttpBinding>  
    </bindings>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />  
             </behavior>  
         </serviceBehaviors>  
       </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
    > [!WARNING]
    >  Si noti che quando si specifica l'oggetto serviceAuthorizationManagerType, la stringa deve contenere il nome di tipo completo, una virgola e il nome dell'assembly in cui il tipo è definito. Se si omette il nome dell'assembly, WCF tenterà di caricare il tipo da System.ServiceModel.dll.  
  
## <a name="example"></a>Esempio  
 Nell'esempio di codice seguente viene descritta un'implementazione di base di una classe <xref:System.ServiceModel.ServiceAuthorizationManager> che prevede l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Nell'esempio di codice viene eseguita una ricerca all'interno del contesto <xref:System.IdentityModel.Policy.AuthorizationContext> allo scopo di individuare un'attestazione personalizzata e quindi viene restituito `true` quando la risorsa relativa a tale attestazione personalizzata corrisponde al valore di azione indicato nel contesto <xref:System.ServiceModel.OperationContext>. Per un'implementazione più completa di un <xref:System.ServiceModel.ServiceAuthorizationManager> classe, vedere [criteri di autorizzazione](../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [Criteri di autorizzazione](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [Criteri di autorizzazione](../../../../docs/framework/wcf/samples/authorization-policy.md)
