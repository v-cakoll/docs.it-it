---
title: 'Procedura: creare un servizio che usa un validator del certificato personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: af1bb9b2ff793f6e6854c1b253dd445a35a5076f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185568"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="d3e98-102">Procedura: creare un servizio che usa un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="d3e98-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="d3e98-103">In questo argomento viene illustrato come implementare un validator del certificato personalizzato e come configurare le credenziali del client o del servizio per sostituire la logica di convalida del certificato predefinita con il validator del certificato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d3e98-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="d3e98-104">Se il certificato X.509 viene usato per autenticare un client o un servizio, Windows Communication Foundation (WCF) per impostazione predefinita usa l'archivio certificati di Windows e l'API di crittografia per convalidare il certificato e assicurarsi che sia attendibile.</span><span class="sxs-lookup"><span data-stu-id="d3e98-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="d3e98-105">A volte la funzionalità di convalida del certificato predefinita non è sufficiente e deve essere modificata.</span><span class="sxs-lookup"><span data-stu-id="d3e98-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="d3e98-106">WCF fornisce un modo semplice per modificare la logica di convalida consentendo agli utenti di aggiungere un validator del certificato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d3e98-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="d3e98-107">Se viene specificato un validator del certificato personalizzato, WCF non utilizza la logica di convalida del certificato incorporata, ma si basa sul validator personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d3e98-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d3e98-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="d3e98-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="d3e98-109">Per creare un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="d3e98-109">To create a custom certificate validator</span></span>  
  
1. <span data-ttu-id="d3e98-110">Definire una nuova classe derivata da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2. <span data-ttu-id="d3e98-111">Implementare il metodo astratto <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="d3e98-112">Il certificato che deve essere convalidato viene passato come argomento al metodo.</span><span class="sxs-lookup"><span data-stu-id="d3e98-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="d3e98-113">Se il certificato passato non è valido in base alla logica di convalida, questo metodo genera un'eccezione <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="d3e98-114">Se il certificato è valido, il metodo viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="d3e98-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="d3e98-115">Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="d3e98-116">Per specificare un validator del certificato personalizzato nella configurazione del servizio</span><span class="sxs-lookup"><span data-stu-id="d3e98-116">To specify a custom certificate validator in service configuration</span></span>  
  
1. <span data-ttu-id="d3e98-117">Aggiungere [ \<](../../configure-apps/file-schema/wcf/behaviors.md) un elemento di>dei comportamenti e un [ \<>serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) all'elemento [ \<system.serviceModel>.](../../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d3e98-117">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="d3e98-118">Aggiungere [ \<](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) un>di `name` comportamento e impostare l'attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e98-118">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3. <span data-ttu-id="d3e98-119">Aggiungere un [ \<>serviceCredentials](../../configure-apps/file-schema/wcf/servicecredentials.md) all'elemento. `<behavior>`</span><span class="sxs-lookup"><span data-stu-id="d3e98-119">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4. <span data-ttu-id="d3e98-120">Aggiungere un elemento `<clientCertificate>` all'elemento `<serviceCredentials>`.</span><span class="sxs-lookup"><span data-stu-id="d3e98-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5. <span data-ttu-id="d3e98-121">Aggiungere [ \<un>di autenticazione](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) all'elemento. `<clientCertificate>`</span><span class="sxs-lookup"><span data-stu-id="d3e98-121">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6. <span data-ttu-id="d3e98-122">Impostare l'attributo `customCertificateValidatorType` sul tipo di validator.</span><span class="sxs-lookup"><span data-stu-id="d3e98-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="d3e98-123">Nell'esempio seguente viene impostato l'attributo sullo spazio dei nomi e sul nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="d3e98-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7. <span data-ttu-id="d3e98-124">Impostare l'attributo `certificateValidationMode` su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="d3e98-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="d3e98-125">Per specificare un validator del certificato personalizzato mediante configurazione sul client</span><span class="sxs-lookup"><span data-stu-id="d3e98-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1. <span data-ttu-id="d3e98-126">Aggiungere [ \<](../../configure-apps/file-schema/wcf/behaviors.md) un elemento di>dei comportamenti e un [ \<>serviceBehaviors](../../configure-apps/file-schema/wcf/servicebehaviors.md) all'elemento [ \<system.serviceModel>.](../../configure-apps/file-schema/wcf/system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="d3e98-126">Add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="d3e98-127">Aggiungere [ \<un elemento endpointBehaviors>.](../../configure-apps/file-schema/wcf/endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d3e98-127">Add an [\<endpointBehaviors>](../../configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3. <span data-ttu-id="d3e98-128">Aggiungere un elemento  e impostare l'attributo  su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="d3e98-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4. <span data-ttu-id="d3e98-129">Aggiungere un [ \<elemento clientCredentials>.Add a clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span><span class="sxs-lookup"><span data-stu-id="d3e98-129">Add a [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5. <span data-ttu-id="d3e98-130">Aggiungere un [ \<>serviceCertificate ](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="d3e98-130">Add a [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6. <span data-ttu-id="d3e98-131">Aggiungere [ \<un>di autenticazione](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d3e98-131">Add an [\<authentication>](../../configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7. <span data-ttu-id="d3e98-132">Impostare l'attributo `customCertificateValidatorType` sul tipo di validator.</span><span class="sxs-lookup"><span data-stu-id="d3e98-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8. <span data-ttu-id="d3e98-133">Impostare l'attributo `certificateValidationMode` su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="d3e98-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="d3e98-134">Nell'esempio seguente viene impostato l'attributo sullo spazio dei nomi e sul nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="d3e98-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="d3e98-135">Per specificare un validator del certificato personalizzato mediante il codice sul servizio</span><span class="sxs-lookup"><span data-stu-id="d3e98-135">To specify a custom certificate validator using code on the service</span></span>  
  
1. <span data-ttu-id="d3e98-136">Specificare il validator del certificato personalizzato sulla proprietà <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="d3e98-137">È possibile accedere alle credenziali del servizio mediante la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2. <span data-ttu-id="d3e98-138">Impostare la proprietà <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="d3e98-139">Per specificare un validator del certificato personalizzato mediante il codice sul client</span><span class="sxs-lookup"><span data-stu-id="d3e98-139">To specify a custom certificate validator using code on the client</span></span>  
  
1. <span data-ttu-id="d3e98-140">Specificare il validator del certificato personalizzato mediante la proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="d3e98-141">È possibile accedere alle credenziali del client mediante la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="d3e98-142">La classe client generata dallo [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) deriva sempre dalla <xref:System.ServiceModel.ClientBase%601> classe.</span><span class="sxs-lookup"><span data-stu-id="d3e98-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2. <span data-ttu-id="d3e98-143">Impostare la proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="d3e98-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3e98-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="d3e98-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d3e98-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3e98-145">Description</span></span>  
 <span data-ttu-id="d3e98-146">Nell'esempio seguente viene illustrata un'implementazione di un validator del certificato personalizzato e l'uso sul servizio.</span><span class="sxs-lookup"><span data-stu-id="d3e98-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d3e98-147">Codice</span><span class="sxs-lookup"><span data-stu-id="d3e98-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d3e98-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3e98-148">See also</span></span>

- <xref:System.IdentityModel.Selectors.X509CertificateValidator>
