---
title: 'Procedura: Creare un gestore autorizzazioni personalizzato per un servizio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: 9c28cb81b78f80505cfcf5f7e4dfdba083bd0793
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797116"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a>Procedura: Creare un gestore autorizzazioni personalizzato per un servizio

L'infrastruttura del modello di identità in Windows Communication Foundation (WCF) supporta un modello di autorizzazione estendibile basato sulle attestazioni. Le attestazioni vengono estratte dai token, elaborate facoltativamente da criteri di autorizzazione personalizzati e quindi inserite in una classe <xref:System.IdentityModel.Policy.AuthorizationContext>. Un gestore autorizzazioni esamina le attestazioni contenute nel contesto <xref:System.IdentityModel.Policy.AuthorizationContext> per prendere decisioni di autorizzazione.

Per impostazione predefinita, le decisioni di autorizzazione sono prese dalla classe <xref:System.ServiceModel.ServiceAuthorizationManager>. È tuttavia possibile creare un gestore autorizzazioni personalizzato per eseguire l'override di queste decisioni. Per creare un gestore autorizzazioni personalizzato, creare una classe che deriva da <xref:System.ServiceModel.ServiceAuthorizationManager> e che implementa il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Le decisioni di autorizzazione sono prese tramite il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> che restituisce `true` quando l'accesso è concesso e `false` quando l'accesso è negato.

Se la decisione di autorizzazione dipende dal contenuto del corpo del messaggio, utilizzare il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.

A causa di problemi riguardanti le prestazioni, è consigliabile ridisegnare l'applicazione, se possibile, in modo tale che per la decisione di autorizzazione non sia necessario l'accesso al corpo del messaggio.

La registrazione del gestore autorizzazioni personalizzato per un servizio può essere eseguita in codice o in configurazione.

### <a name="to-create-a-custom-authorization-manager"></a>Per creare un gestore autorizzazioni personalizzato

1. Derivare una classe dalla classe <xref:System.ServiceModel.ServiceAuthorizationManager>.

    [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
    [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]

2. Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> .

    Utilizzare il contesto <xref:System.ServiceModel.OperationContext> passato al metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> per prendere decisioni di autorizzazione.

    Nell'esempio di codice seguente il metodo <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> viene utilizzato per individuare l'attestazione personalizzata `http://www.contoso.com/claims/allowedoperation` allo scopo di prendere una decisione di autorizzazione.

    [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
    [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]

### <a name="to-register-a-custom-authorization-manager-using-code"></a>Per registrare un gestore autorizzazioni personalizzato in codice

1. Creare un'istanza del gestore autorizzazioni personalizzato e assegnarla alla proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.

    Per accedere al comportamento <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> è possibile utilizzare la proprietà <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.

    Nell'esempio di codice seguente viene illustrato come registrare il gestore autorizzazioni personalizzato `MyServiceAuthorizationManager`.

    [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
    [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]

### <a name="to-register-a-custom-authorization-manager-using-configuration"></a>Per registrare un gestore autorizzazioni personalizzato in configurazione

1. Aprire il file di configurazione del servizio.

2. Aggiungere un [ \<](../../configure-apps/file-schema/wcf/serviceauthorization-element.md) [ >ServiceAuthorizationaicomportamenti>.\<](../../configure-apps/file-schema/wcf/behaviors.md)

    Al > `serviceAuthorizationManagerType` ServiceAuthorization aggiungere un attributo e impostarne il valore sul tipo che rappresenta il gestore autorizzazioni personalizzato. [ \<](../../configure-apps/file-schema/wcf/serviceauthorization-element.md)

3. Aggiungere un'associazione in grado di proteggere la comunicazione tra client e servizio.

    L'associazione scelta per questa comunicazione determina le attestazioni aggiunte al contesto <xref:System.IdentityModel.Policy.AuthorizationContext> utilizzate dal gestore autorizzazioni personalizzato per prendere le decisioni di autorizzazione. Per ulteriori informazioni sulle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../system-provided-bindings.md).

4. Associare il comportamento a un endpoint di servizio, aggiungendo un [ \<> di servizio](../../configure-apps/file-schema/wcf/service.md) e impostando `behaviorConfiguration` il valore dell'attributo sul valore dell'attributo Name per l' [ \<elemento behavior >](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .

    Per ulteriori informazioni sulla configurazione di un endpoint del servizio [, vedere Procedura: Creare un endpoint del servizio nella](../feature-details/how-to-create-a-service-endpoint-in-configuration.md)configurazione.

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
    > Si noti che quando si specifica l'oggetto serviceAuthorizationManagerType, la stringa deve contenere il nome di tipo completo, una virgola e il nome dell'assembly in cui il tipo è definito. Se si omette il nome dell'assembly, WCF tenterà di caricare il tipo da System.ServiceModel.dll.

## <a name="example"></a>Esempio

Nell'esempio di codice seguente viene descritta un'implementazione di base di una classe <xref:System.ServiceModel.ServiceAuthorizationManager> che prevede l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>. Nell'esempio di codice viene eseguita una ricerca all'interno del contesto <xref:System.IdentityModel.Policy.AuthorizationContext> allo scopo di individuare un'attestazione personalizzata e quindi viene restituito `true` quando la risorsa relativa a tale attestazione personalizzata corrisponde al valore di azione indicato nel contesto <xref:System.ServiceModel.OperationContext>. Per un'implementazione più completa di una <xref:System.ServiceModel.ServiceAuthorizationManager> classe, vedere [criteri di autorizzazione](../samples/authorization-policy.md).

[!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
[!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [Criteri di autorizzazione](../samples/authorization-policy.md)
