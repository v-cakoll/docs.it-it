---
title: 'Procedura: Usare un validator di nome utente e password personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 593e3e97ad7e5ae65447d8618caacf22f762f9b4
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960069"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="bbad7-102">Procedura: Usare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="bbad7-102">How to: Use a Custom User Name and Password Validator</span></span>
<span data-ttu-id="bbad7-103">Per impostazione predefinita, quando viene utilizzato un nome utente e una password per l'autenticazione, Windows Communication Foundation (WCF) viene utilizzato Windows per convalidare il nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="bbad7-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="bbad7-104">Tuttavia, WCF consente agli utente personalizzata nome e una password schemi di autenticazione, noto anche come *validator*.</span><span class="sxs-lookup"><span data-stu-id="bbad7-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="bbad7-105">Per incorporare un validator personalizzato di nome utente e password, creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> e configurarla.</span><span class="sxs-lookup"><span data-stu-id="bbad7-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>  
  
 <span data-ttu-id="bbad7-106">Per un'applicazione di esempio, vedere [Validator nome utente e Password](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>  
  
### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="bbad7-107">Per creare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="bbad7-107">To create a custom user name and password validator</span></span>  
  
1. <span data-ttu-id="bbad7-108">Creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="bbad7-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]  
  
2. <span data-ttu-id="bbad7-109">Implementare lo schema di autenticazione personalizzato eseguendo l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="bbad7-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     <span data-ttu-id="bbad7-110">Non utilizzare il codice contenuto nell'esempio seguente, che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="bbad7-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="bbad7-111">Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.</span><span class="sxs-lookup"><span data-stu-id="bbad7-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
     <span data-ttu-id="bbad7-112">Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="bbad7-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
     [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
     [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]  
  
### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="bbad7-113">Per configurare un servizio per l'utilizzo di un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="bbad7-113">To configure a service to use a custom user name and password validator</span></span>  
  
1. <span data-ttu-id="bbad7-114">Configurare un'associazione che utilizza meccanismi di sicurezza a livello di messaggio su qualsiasi trasporto o meccanismi di sicurezza a livello di trasporto su HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="bbad7-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>  
  
     <span data-ttu-id="bbad7-115">Quando si usa la sicurezza dei messaggi, aggiungere una delle associazioni fornite dal sistema, ad esempio un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), o un' [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) che supporta la sicurezza dei messaggi e il `UserName` il tipo di credenziale.</span><span class="sxs-lookup"><span data-stu-id="bbad7-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>  
  
     <span data-ttu-id="bbad7-116">Quando si usa la sicurezza a livello di trasporto su HTTP (S), aggiungere il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oppure [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)un [ \< netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) o un [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) che utilizza HTTP (S) e il `Basic` lo schema di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="bbad7-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bbad7-117">Quando si utilizza [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] o versioni successive, è possibile utilizzare un validator di nome utente e password personalizzato con modalità di sicurezza dei messaggi e del trasporto.</span><span class="sxs-lookup"><span data-stu-id="bbad7-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="bbad7-118">Con WinFX, un validator di nome utente e password personalizzato utilizzabile solo con la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="bbad7-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="bbad7-119">Per altre informazioni sull'uso \<netTcpBinding > in questo contesto, vedere [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="bbad7-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>  
  
    1. <span data-ttu-id="bbad7-120">Nel file di configurazione, sotto il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="bbad7-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
    2. <span data-ttu-id="bbad7-121">Aggiungere un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) oppure [ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento alla sezione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="bbad7-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="bbad7-122">Per altre informazioni sulla creazione di un elemento di binding WCF, vedere [come: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
    3. <span data-ttu-id="bbad7-123">Impostare il `mode` attributo del [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [ \<sicurezza >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) a `Message`, `Transport`, o `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="bbad7-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>  
  
    4. <span data-ttu-id="bbad7-124">Impostare il `clientCredentialType` attributo del [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) oppure [ \<trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>  
  
         <span data-ttu-id="bbad7-125">Quando si utilizza la sicurezza dei messaggi, impostare il `clientCredentialType` attributo del [ \<messaggio >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) a `UserName`.</span><span class="sxs-lookup"><span data-stu-id="bbad7-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>  
  
         <span data-ttu-id="bbad7-126">Quando si utilizza la sicurezza a livello di trasporto su HTTP (S), impostare il `clientCredentialType` attributo del [ \<trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [ \<trasporto >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) a `Basic`.</span><span class="sxs-lookup"><span data-stu-id="bbad7-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="bbad7-127">Quando un servizio WCF è ospitato in Internet Information Services (IIS) utilizzando la sicurezza a livello di trasporto e il <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> è impostata su <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, lo schema di autenticazione personalizzato utilizza un subset dell'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="bbad7-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="bbad7-128">Questo avviene perché in questo scenario IIS esegue l'autenticazione di Windows prima di WCF richiamando l'autenticatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="bbad7-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>  
  
     <span data-ttu-id="bbad7-129">Per altre informazioni sulla creazione di un elemento di binding WCF, vedere [come: Specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
     <span data-ttu-id="bbad7-130">Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="bbad7-130">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>   
      <bindings>  
      <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="UserName" />  
            </security>  
          </binding>          
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
2. <span data-ttu-id="bbad7-131">Configurare un comportamento che specifica che un validator personalizzato di nome utente e password viene utilizzato per convalidare coppie di nome utente e password per i token di sicurezza <xref:System.IdentityModel.Tokens.UserNameSecurityToken> in arrivo.</span><span class="sxs-lookup"><span data-stu-id="bbad7-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>  
  
    1. <span data-ttu-id="bbad7-132">Come elemento figlio per il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="bbad7-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    2. <span data-ttu-id="bbad7-133">Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="bbad7-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
    3. <span data-ttu-id="bbad7-134">Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="bbad7-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
    4. <span data-ttu-id="bbad7-135">Aggiungere un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) per il [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="bbad7-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
    5. <span data-ttu-id="bbad7-136">Aggiungere un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) per il [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="bbad7-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
    6. <span data-ttu-id="bbad7-137">Impostare `userNamePasswordValidationMode` su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="bbad7-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="bbad7-138">Se il `userNamePasswordValidationMode` valore non è impostato, WCF Usa l'autenticazione di Windows anziché il validator di nome e una password utente personalizzata.</span><span class="sxs-lookup"><span data-stu-id="bbad7-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>  
  
    7. <span data-ttu-id="bbad7-139">Impostare `customUserNamePasswordValidatorType` sul tipo che rappresenta il validator personalizzato di nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="bbad7-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>  
  
     <span data-ttu-id="bbad7-140">Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.</span><span class="sxs-lookup"><span data-stu-id="bbad7-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <serviceCredentials>  
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />  
    </serviceCredentials>  
    ```  
  
## <a name="example"></a><span data-ttu-id="bbad7-141">Esempio</span><span class="sxs-lookup"><span data-stu-id="bbad7-141">Example</span></span>  
 <span data-ttu-id="bbad7-142">Nel codice di esempio seguente viene dimostrato come creare un validator personalizzato di nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="bbad7-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="bbad7-143">Non utilizzare il codice che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="bbad7-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="bbad7-144">Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.</span><span class="sxs-lookup"><span data-stu-id="bbad7-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>  
  
 [!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
 [!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]  
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bbad7-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbad7-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="bbad7-146">Procedura: Usare il Provider di appartenenze ASP.NET</span><span class="sxs-lookup"><span data-stu-id="bbad7-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="bbad7-147">Autenticazione</span><span class="sxs-lookup"><span data-stu-id="bbad7-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
