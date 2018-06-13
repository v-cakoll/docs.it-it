---
title: 'Procedura: creare un gestore autorizzazioni personalizzato per un servizio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: 7fe392b2fcd2f8ccb00bfd6ffd7e917649f8280c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490442"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="1dc64-102">Procedura: creare un gestore autorizzazioni personalizzato per un servizio</span><span class="sxs-lookup"><span data-stu-id="1dc64-102">How to: Create a Custom Authorization Manager for a Service</span></span>
<span data-ttu-id="1dc64-103">L'infrastruttura del modello di identità in Windows Communication Foundation (WCF) supporta un modello di autorizzazione basata sulle attestazioni estensibili.</span><span class="sxs-lookup"><span data-stu-id="1dc64-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="1dc64-104">Le attestazioni vengono estratte dai token, elaborate facoltativamente da criteri di autorizzazione personalizzati e quindi inserite in una classe <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="1dc64-105">Un gestore autorizzazioni esamina le attestazioni contenute nel contesto <xref:System.IdentityModel.Policy.AuthorizationContext> per prendere decisioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1dc64-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>  
  
 <span data-ttu-id="1dc64-106">Per impostazione predefinita, le decisioni di autorizzazione sono prese dalla classe <xref:System.ServiceModel.ServiceAuthorizationManager>. È tuttavia possibile creare un gestore autorizzazioni personalizzato per eseguire l'override di queste decisioni.</span><span class="sxs-lookup"><span data-stu-id="1dc64-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="1dc64-107">Per creare un gestore autorizzazioni personalizzato, creare una classe che deriva da <xref:System.ServiceModel.ServiceAuthorizationManager> e che implementa il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="1dc64-108">Le decisioni di autorizzazione sono prese tramite il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> che restituisce `true` quando l'accesso è concesso e `false` quando l'accesso è negato.</span><span class="sxs-lookup"><span data-stu-id="1dc64-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>  
  
 <span data-ttu-id="1dc64-109">Se la decisione di autorizzazione dipende dal contenuto del corpo del messaggio, utilizzare il metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>  
  
 <span data-ttu-id="1dc64-110">A causa di problemi riguardanti le prestazioni, è consigliabile ridisegnare l'applicazione, se possibile, in modo tale che per la decisione di autorizzazione non sia necessario l'accesso al corpo del messaggio.</span><span class="sxs-lookup"><span data-stu-id="1dc64-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>  
  
 <span data-ttu-id="1dc64-111">La registrazione del gestore autorizzazioni personalizzato per un servizio può essere eseguita in codice o in configurazione.</span><span class="sxs-lookup"><span data-stu-id="1dc64-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>  
  
### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="1dc64-112">Per creare un gestore autorizzazioni personalizzato</span><span class="sxs-lookup"><span data-stu-id="1dc64-112">To create a custom authorization manager</span></span>  
  
1.  <span data-ttu-id="1dc64-113">Derivare una classe dalla classe <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  <span data-ttu-id="1dc64-114">Eseguire l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>  
  
     <span data-ttu-id="1dc64-115">Utilizzare il contesto <xref:System.ServiceModel.OperationContext> passato al metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> per prendere decisioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1dc64-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>  
  
     <span data-ttu-id="1dc64-116">Nell'esempio di codice seguente il metodo <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> viene utilizzato per individuare l'attestazione personalizzata `http://www.contoso.com/claims/allowedoperation` allo scopo di prendere una decisione di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1dc64-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="1dc64-117">Per registrare un gestore autorizzazioni personalizzato in codice</span><span class="sxs-lookup"><span data-stu-id="1dc64-117">To register a custom authorization manager using code</span></span>  
  
1.  <span data-ttu-id="1dc64-118">Creare un'istanza del gestore autorizzazioni personalizzato e assegnarla alla proprietà <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>  
  
     <span data-ttu-id="1dc64-119">Per accedere al comportamento <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> è possibile utilizzare la proprietà <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>  
  
     <span data-ttu-id="1dc64-120">Nell'esempio di codice seguente viene illustrato come registrare il gestore autorizzazioni personalizzato `MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="1dc64-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="1dc64-121">Per registrare un gestore autorizzazioni personalizzato in configurazione</span><span class="sxs-lookup"><span data-stu-id="1dc64-121">To register a custom authorization manager using configuration</span></span>  
  
1.  <span data-ttu-id="1dc64-122">Aprire il file di configurazione del servizio.</span><span class="sxs-lookup"><span data-stu-id="1dc64-122">Open the configuration file for the service.</span></span>  
  
2.  <span data-ttu-id="1dc64-123">Aggiungere un [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) per il [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="1dc64-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span>  
  
     <span data-ttu-id="1dc64-124">Per il [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), aggiungere un `serviceAuthorizationManagerType` attributo e impostarne il valore per il tipo che rappresenta il gestore autorizzazioni personalizzato.</span><span class="sxs-lookup"><span data-stu-id="1dc64-124">To the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>  
  
3.  <span data-ttu-id="1dc64-125">Aggiungere un'associazione in grado di proteggere la comunicazione tra client e servizio.</span><span class="sxs-lookup"><span data-stu-id="1dc64-125">Add a binding that secures the communication between the client and service.</span></span>  
  
     <span data-ttu-id="1dc64-126">L'associazione scelta per questa comunicazione determina le attestazioni aggiunte al contesto <xref:System.IdentityModel.Policy.AuthorizationContext> utilizzate dal gestore autorizzazioni personalizzato per prendere le decisioni di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="1dc64-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="1dc64-127">Per ulteriori informazioni sulle associazioni fornite dal sistema, vedere [associazioni fornite dal sistema](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="1dc64-127">For more details about the system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
4.  <span data-ttu-id="1dc64-128">Associare il comportamento a un endpoint di servizio, aggiungendo un [ \<servizio >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) elemento e impostare il valore della `behaviorConfiguration` attributo sul valore dell'attributo del nome per il [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="1dc64-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
     <span data-ttu-id="1dc64-129">Per ulteriori informazioni sulla configurazione di un endpoint del servizio, vedere [procedura: creare un Endpoint del servizio nella configurazione](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1dc64-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
     <span data-ttu-id="1dc64-130">Nell'esempio di codice seguente viene illustrato come registrare il gestore autorizzazioni personalizzato `Samples.MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="1dc64-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>  
  
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
    >  <span data-ttu-id="1dc64-131">Si noti che quando si specifica l'oggetto serviceAuthorizationManagerType, la stringa deve contenere il nome di tipo completo,</span><span class="sxs-lookup"><span data-stu-id="1dc64-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="1dc64-132">una virgola e il nome dell'assembly in cui il tipo è definito.</span><span class="sxs-lookup"><span data-stu-id="1dc64-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="1dc64-133">Se si omette il nome dell'assembly, WCF tenterà di caricare il tipo da System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="1dc64-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dc64-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="1dc64-134">Example</span></span>  
 <span data-ttu-id="1dc64-135">Nell'esempio di codice seguente viene descritta un'implementazione di base di una classe <xref:System.ServiceModel.ServiceAuthorizationManager> che prevede l'override del metodo <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="1dc64-136">Nell'esempio di codice viene eseguita una ricerca all'interno del contesto <xref:System.IdentityModel.Policy.AuthorizationContext> allo scopo di individuare un'attestazione personalizzata e quindi viene restituito `true` quando la risorsa relativa a tale attestazione personalizzata corrisponde al valore di azione indicato nel contesto <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="1dc64-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="1dc64-137">Per un'implementazione più completa di un <xref:System.ServiceModel.ServiceAuthorizationManager> classe, vedere [criteri di autorizzazione](../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="1dc64-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1dc64-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1dc64-138">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 [<span data-ttu-id="1dc64-139">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1dc64-139">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [<span data-ttu-id="1dc64-140">Criteri di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="1dc64-140">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
