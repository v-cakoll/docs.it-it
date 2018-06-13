---
title: 'Procedura: creare un servizio che usa un validator del certificato personalizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, authentication
ms.assetid: bb0190ff-0738-4e54-8d22-c97d343708bf
ms.openlocfilehash: cc768f5e5086e6eba1ccac9d969eac14e14ceb2f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808143"
---
# <a name="how-to-create-a-service-that-employs-a-custom-certificate-validator"></a><span data-ttu-id="adff5-102">Procedura: creare un servizio che usa un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="adff5-102">How to: Create a Service that Employs a Custom Certificate Validator</span></span>
<span data-ttu-id="adff5-103">In questo argomento viene illustrato come implementare un validator del certificato personalizzato e come configurare le credenziali del client o del servizio per sostituire la logica di convalida del certificato predefinita con il validator del certificato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="adff5-103">This topic shows how to implement a custom certificate validator and how to configure client or service credentials to replace the default certificate validation logic with the custom certificate validator.</span></span>  
  
 <span data-ttu-id="adff5-104">Se il certificato X.509 viene usato per autenticare un client o servizio, Windows Communication Foundation (WCF) per impostazione predefinita utilizza l'archivio certificati di Windows e l'API di crittografia per convalidare il certificato e assicurarsi che sia attendibile.</span><span class="sxs-lookup"><span data-stu-id="adff5-104">If the X.509 certificate is used to authenticate a client or service, Windows Communication Foundation (WCF) by default uses the Windows certificate store and Crypto API to validate the certificate and to ensure that it is trusted.</span></span> <span data-ttu-id="adff5-105">A volte la funzionalità di convalida del certificato predefinita non è sufficiente e deve essere modificata.</span><span class="sxs-lookup"><span data-stu-id="adff5-105">Sometimes the built-in certificate validation functionality is not enough and must be changed.</span></span> <span data-ttu-id="adff5-106">WCF fornisce un modo semplice per modificare la logica di convalida consentendo agli utenti di aggiungere un validator del certificato personalizzato.</span><span class="sxs-lookup"><span data-stu-id="adff5-106">WCF provides an easy way to change the validation logic by allowing users to add a custom certificate validator.</span></span> <span data-ttu-id="adff5-107">Se viene specificato un validator del certificato personalizzato, WCF non utilizza la logica di convalida del certificato incorporata, bensì si basa sul validator personalizzato invece.</span><span class="sxs-lookup"><span data-stu-id="adff5-107">If a custom certificate validator is specified, WCF does not use the built-in certificate validation logic but relies on the custom validator instead.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="adff5-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="adff5-108">Procedures</span></span>  
  
#### <a name="to-create-a-custom-certificate-validator"></a><span data-ttu-id="adff5-109">Per creare un validator del certificato personalizzato</span><span class="sxs-lookup"><span data-stu-id="adff5-109">To create a custom certificate validator</span></span>  
  
1.  <span data-ttu-id="adff5-110">Definire una nuova classe derivata da <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="adff5-110">Define a new class derived from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span>  
  
2.  <span data-ttu-id="adff5-111">Implementare il metodo astratto <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="adff5-111">Implement the abstract <xref:System.IdentityModel.Selectors.X509CertificateValidator.Validate%2A> method.</span></span> <span data-ttu-id="adff5-112">Il certificato che deve essere convalidato viene passato come argomento al metodo.</span><span class="sxs-lookup"><span data-stu-id="adff5-112">The certificate that must be validated is passed as an argument to the method.</span></span> <span data-ttu-id="adff5-113">Se il certificato passato non è valido in base alla logica di convalida, questo metodo genera un'eccezione <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span><span class="sxs-lookup"><span data-stu-id="adff5-113">If the passed certificate is not valid according to the validation logic, this method throws a <xref:System.IdentityModel.Tokens.SecurityTokenValidationException>.</span></span> <span data-ttu-id="adff5-114">Se il certificato è valido, il metodo viene restituito al chiamante.</span><span class="sxs-lookup"><span data-stu-id="adff5-114">If the certificate is valid, the method returns to the caller.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adff5-115">Affinché gli errori di autenticazione vengano restituiti al client, generare una classe <xref:System.ServiceModel.FaultException> nel metodo <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="adff5-115">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#2)]
 [!code-vb[c_CustomCertificateValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#2)]  
  
#### <a name="to-specify-a-custom-certificate-validator-in-service-configuration"></a><span data-ttu-id="adff5-116">Per specificare un validator del certificato personalizzato nella configurazione del servizio</span><span class="sxs-lookup"><span data-stu-id="adff5-116">To specify a custom certificate validator in service configuration</span></span>  
  
1.  <span data-ttu-id="adff5-117">Aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento e un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="adff5-117">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="adff5-118">Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="adff5-118">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="adff5-119">Aggiungere un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) per il `<behavior>` elemento.</span><span class="sxs-lookup"><span data-stu-id="adff5-119">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the `<behavior>` element.</span></span>  
  
4.  <span data-ttu-id="adff5-120">Aggiungere un elemento `<clientCertificate>` all'elemento `<serviceCredentials>`.</span><span class="sxs-lookup"><span data-stu-id="adff5-120">Add a `<clientCertificate>` element to the `<serviceCredentials>` element.</span></span>  
  
5.  <span data-ttu-id="adff5-121">Aggiungere un [ \<autenticazione >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) per il `<clientCertificate>` elemento.</span><span class="sxs-lookup"><span data-stu-id="adff5-121">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md) to the `<clientCertificate>` element.</span></span>  
  
6.  <span data-ttu-id="adff5-122">Impostare l'attributo `customCertificateValidatorType` sul tipo di validator.</span><span class="sxs-lookup"><span data-stu-id="adff5-122">Set the `customCertificateValidatorType` attribute to the validator type.</span></span> <span data-ttu-id="adff5-123">Nell'esempio seguente viene impostato l'attributo sullo spazio dei nomi e sul nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="adff5-123">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
7.  <span data-ttu-id="adff5-124">Impostare l'attributo `certificateValidationMode` su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="adff5-124">Set the `certificateValidationMode` attribute to `Custom`.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-configuration-on-the-client"></a><span data-ttu-id="adff5-125">Per specificare un validator del certificato personalizzato mediante configurazione sul client</span><span class="sxs-lookup"><span data-stu-id="adff5-125">To specify a custom certificate validator using configuration on the client</span></span>  
  
1.  <span data-ttu-id="adff5-126">Aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento e un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="adff5-126">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element and a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="adff5-127">Aggiungere un [ \<endpointBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="adff5-127">Add an [\<endpointBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md) element.</span></span>  
  
3.  <span data-ttu-id="adff5-128">Aggiungere un elemento `<behavior>` e impostare l'attributo `name` su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="adff5-128">Add a `<behavior>` element and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="adff5-129">Aggiungere un [ \<clientCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="adff5-129">Add a [\<clientCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
5.  <span data-ttu-id="adff5-130">Aggiungere un [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span><span class="sxs-lookup"><span data-stu-id="adff5-130">Add a [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md).</span></span>  
  
6.  <span data-ttu-id="adff5-131">Aggiungere un [ \<autenticazione >](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="adff5-131">Add an [\<authentication>](../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md) as shown on the following example.</span></span>  
  
7.  <span data-ttu-id="adff5-132">Impostare l'attributo `customCertificateValidatorType` sul tipo di validator.</span><span class="sxs-lookup"><span data-stu-id="adff5-132">Set the `customCertificateValidatorType` attribute to the validator type.</span></span>  
  
8.  <span data-ttu-id="adff5-133">Impostare l'attributo `certificateValidationMode` su `Custom`.</span><span class="sxs-lookup"><span data-stu-id="adff5-133">Set the `certificateValidationMode` attribute to `Custom`.</span></span> <span data-ttu-id="adff5-134">Nell'esempio seguente viene impostato l'attributo sullo spazio dei nomi e sul nome del tipo.</span><span class="sxs-lookup"><span data-stu-id="adff5-134">The following example sets the attribute to the namespace and name of the type.</span></span>  
  
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
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-service"></a><span data-ttu-id="adff5-135">Per specificare un validator del certificato personalizzato mediante il codice sul servizio</span><span class="sxs-lookup"><span data-stu-id="adff5-135">To specify a custom certificate validator using code on the service</span></span>  
  
1.  <span data-ttu-id="adff5-136">Specificare il validator del certificato personalizzato sulla proprietà <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>.</span><span class="sxs-lookup"><span data-stu-id="adff5-136">Specify the custom certificate validator on the <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A> property.</span></span> <span data-ttu-id="adff5-137">È possibile accedere alle credenziali del servizio mediante la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="adff5-137">You can access the service credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span>  
  
2.  <span data-ttu-id="adff5-138">Impostare la proprietà <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="adff5-138">Set the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
 [!code-csharp[c_CustomCertificateValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#1)]
 [!code-vb[c_CustomCertificateValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#1)]  
  
#### <a name="to-specify-a-custom-certificate-validator-using-code-on-the-client"></a><span data-ttu-id="adff5-139">Per specificare un validator del certificato personalizzato mediante il codice sul client</span><span class="sxs-lookup"><span data-stu-id="adff5-139">To specify a custom certificate validator using code on the client</span></span>  
  
1.  <span data-ttu-id="adff5-140">Specificare il validator del certificato personalizzato mediante la proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A>.</span><span class="sxs-lookup"><span data-stu-id="adff5-140">Specify the custom certificate validator using the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CustomCertificateValidator%2A> property.</span></span> <span data-ttu-id="adff5-141">È possibile accedere alle credenziali del client mediante la proprietà <xref:System.ServiceModel.ServiceHostBase.Credentials%2A>.</span><span class="sxs-lookup"><span data-stu-id="adff5-141">You can access the client credentials using the <xref:System.ServiceModel.ServiceHostBase.Credentials%2A> property.</span></span> <span data-ttu-id="adff5-142">(La classe client generata da [strumento ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) sempre deriva il <xref:System.ServiceModel.ClientBase%601> classe.)</span><span class="sxs-lookup"><span data-stu-id="adff5-142">(The client class generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) always derives from the <xref:System.ServiceModel.ClientBase%601> class.)</span></span>  
  
2.  <span data-ttu-id="adff5-143">Impostare la proprietà <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> su <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span><span class="sxs-lookup"><span data-stu-id="adff5-143">Set the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property to <xref:System.ServiceModel.Security.X509CertificateValidationMode.Custom>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="adff5-144">Esempio</span><span class="sxs-lookup"><span data-stu-id="adff5-144">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="adff5-145">Descrizione</span><span class="sxs-lookup"><span data-stu-id="adff5-145">Description</span></span>  
 <span data-ttu-id="adff5-146">Nell'esempio seguente viene illustrata un'implementazione di un validator del certificato personalizzato e l'uso sul servizio.</span><span class="sxs-lookup"><span data-stu-id="adff5-146">The following sample shows an implementation of a custom certificate validator and its usage on the service.</span></span>  
  
### <a name="code"></a><span data-ttu-id="adff5-147">Codice</span><span class="sxs-lookup"><span data-stu-id="adff5-147">Code</span></span>  
 [!code-csharp[c_CustomCertificateValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcertificatevalidator/cs/source.cs#3)]
 [!code-vb[c_CustomCertificateValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcertificatevalidator/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="adff5-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="adff5-148">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>
