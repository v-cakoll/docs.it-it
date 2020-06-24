---
title: 'Procedura: usare un validator di nome utente e password personalizzato'
description: Informazioni su come incorporare un validator personalizzato delle password per le applicazioni WFC al posto del nome utente e della convalida della password predefiniti di Windows.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 7f69db7bf8248593b64cdae4378983c2460de597
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246792"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="f39ad-103">Procedura: usare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="f39ad-103">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="f39ad-104">Per impostazione predefinita, quando si usa un nome utente e una password per l'autenticazione, Windows Communication Foundation (WCF) usa Windows per convalidare il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="f39ad-104">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="f39ad-105">Tuttavia, WCF consente schemi di autenticazione con nome utente e password personalizzati, noti anche come *validator*.</span><span class="sxs-lookup"><span data-stu-id="f39ad-105">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="f39ad-106">Per incorporare un validator personalizzato di nome utente e password, creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> e configurarla.</span><span class="sxs-lookup"><span data-stu-id="f39ad-106">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="f39ad-107">Per un'applicazione di esempio, vedere [validator nome utente password](../samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="f39ad-107">For a sample application, see [User Name Password Validator](../samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="f39ad-108">Per creare un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="f39ad-108">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="f39ad-109">Creare una classe che deriva da <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="f39ad-109">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="f39ad-110">Implementare lo schema di autenticazione personalizzato eseguendo l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f39ad-110">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="f39ad-111">Non utilizzare il codice contenuto nell'esempio seguente, che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f39ad-111">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="f39ad-112">Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.</span><span class="sxs-lookup"><span data-stu-id="f39ad-112">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="f39ad-113">Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f39ad-113">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="f39ad-114">Per configurare un servizio per l'utilizzo di un validator di nome utente e password personalizzato</span><span class="sxs-lookup"><span data-stu-id="f39ad-114">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="f39ad-115">Configurare un'associazione che utilizza meccanismi di sicurezza a livello di messaggio su qualsiasi trasporto o meccanismi di sicurezza a livello di trasporto su HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="f39ad-115">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="f39ad-116">Quando si utilizza la sicurezza dei messaggi, aggiungere una delle associazioni fornite dal sistema, ad esempio [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) o, [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) che supporta la sicurezza dei messaggi e il `UserName` tipo di credenziale.</span><span class="sxs-lookup"><span data-stu-id="f39ad-116">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="f39ad-117">Quando si utilizza la sicurezza a livello di trasporto su HTTP (S), aggiungere [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) o, o un [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) oggetto [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) che utilizza http (s) e lo `Basic` schema di autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f39ad-117">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f39ad-118">Quando si usa .NET Framework 3,5 o versioni successive, è possibile usare un validator personalizzato di nome utente e password con la sicurezza dei messaggi e del trasporto.</span><span class="sxs-lookup"><span data-stu-id="f39ad-118">When using .NET Framework 3.5 or later versions, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="f39ad-119">Con WinFX, un validator personalizzato di nome utente e password può essere utilizzato solo con la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="f39ad-119">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="f39ad-120">Per ulteriori informazioni sull'utilizzo \<netTcpBinding> di in questo contesto, vedere [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f39ad-120">For more information on using \<netTcpBinding> in this context, see [\<security>](../../configure-apps/file-schema/wcf/security-of-nettcpbinding.md).</span></span>

    1. <span data-ttu-id="f39ad-121">Nel file di configurazione, sotto l' [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f39ad-121">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="f39ad-122">Aggiungere un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) elemento o alla sezione Bindings.</span><span class="sxs-lookup"><span data-stu-id="f39ad-122">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="f39ad-123">Per ulteriori informazioni sulla creazione di un elemento di associazione WCF, vedere [procedura: specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f39ad-123">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="f39ad-124">Impostare l' `mode` attributo dell'oggetto [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) o [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) su `Message` , `Transport` o `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="f39ad-124">Set the `mode` attribute of the [\<security>](../../configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="f39ad-125">Impostare l' `clientCredentialType` attributo dell'oggetto [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) o [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="f39ad-125">Set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="f39ad-126">Quando si utilizza la sicurezza del messaggio, impostare l' `clientCredentialType` attributo di [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) su `UserName` .</span><span class="sxs-lookup"><span data-stu-id="f39ad-126">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="f39ad-127">Quando si utilizza la sicurezza a livello di trasporto su HTTP (S), impostare l' `clientCredentialType` attributo della proprietà [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) o [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) su `Basic` .</span><span class="sxs-lookup"><span data-stu-id="f39ad-127">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="f39ad-128">Quando un servizio WCF è ospitato in Internet Information Services (IIS) utilizzando la sicurezza a livello di trasporto e la <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> proprietà è impostata su <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom> , lo schema di autenticazione personalizzato utilizza un subset dell'autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f39ad-128">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="f39ad-129">Ciò è dovuto al fatto che in questo scenario IIS esegue l'autenticazione di Windows prima che WCF richiami l'autenticatore personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f39ad-129">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="f39ad-130">Per ulteriori informazioni sulla creazione di un elemento di associazione WCF, vedere [procedura: specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="f39ad-130">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="f39ad-131">Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione:</span><span class="sxs-lookup"><span data-stu-id="f39ad-131">The following example shows the configuration code for the binding:</span></span>

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

2. <span data-ttu-id="f39ad-132">Configurare un comportamento che specifica che un validator personalizzato di nome utente e password viene utilizzato per convalidare coppie di nome utente e password per i token di sicurezza <xref:System.IdentityModel.Tokens.UserNameSecurityToken> in arrivo.</span><span class="sxs-lookup"><span data-stu-id="f39ad-132">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="f39ad-133">[\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md)Aggiungere un elemento come figlio dell'elemento [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="f39ad-133">As a child to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="f39ad-134">Aggiungere un oggetto [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f39ad-134">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="f39ad-135">Aggiungere un [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento e impostare l' `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="f39ad-135">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="f39ad-136">Aggiungere un oggetto [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) all' [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="f39ad-136">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="f39ad-137">Aggiungere un oggetto [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) all'oggetto [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="f39ad-137">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="f39ad-138">Impostare `userNamePasswordValidationMode` su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="f39ad-138">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="f39ad-139">Se il `userNamePasswordValidationMode` valore non è impostato, WCF usa l'autenticazione di Windows anziché il validator personalizzato di nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="f39ad-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="f39ad-140">Impostare `customUserNamePasswordValidatorType` sul tipo che rappresenta il validator personalizzato di nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="f39ad-140">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="f39ad-141">Nell'esempio seguente viene illustrato il `<serviceCredentials>` frammento fino a questo punto:</span><span class="sxs-lookup"><span data-stu-id="f39ad-141">The following example shows the `<serviceCredentials>` fragment to this point:</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="f39ad-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="f39ad-142">Example</span></span>

<span data-ttu-id="f39ad-143">Nel codice di esempio seguente viene dimostrato come creare un validator personalizzato di nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="f39ad-143">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="f39ad-144">Non utilizzare il codice che esegue l'override del metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="f39ad-144">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="f39ad-145">Sostituire il codice con lo schema di convalida di nome utente e password personalizzato, operazione che potrebbe comportare il recupero di coppie di nome utente e password da un database.</span><span class="sxs-lookup"><span data-stu-id="f39ad-145">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="f39ad-146">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="f39ad-146">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="f39ad-147">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f39ad-147">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="f39ad-148">autenticazione</span><span class="sxs-lookup"><span data-stu-id="f39ad-148">Authentication</span></span>](authentication-in-wcf.md)
