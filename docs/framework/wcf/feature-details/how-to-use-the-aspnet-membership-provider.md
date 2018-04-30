---
title: 'Procedura: usare provider di appartenenza ASP.NET'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 19fb83d21c77f3206c314a2e6c40562fcb75f151
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="18980-102">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="18980-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="18980-103">Il provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] è una funzionalità che consente agli sviluppatori di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] di creare siti Web che consentono agli utenti di creare combinazioni di nome utente e password univoche.</span><span class="sxs-lookup"><span data-stu-id="18980-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="18980-104">Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="18980-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="18980-105">Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="18980-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="18980-106">Qualsiasi utente che fornisca le credenziali (ovvero nome utente e password) può utilizzare il sito e i relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="18980-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="18980-107">Per un'applicazione di esempio, vedere [Provider di appartenenze e ruoli](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="18980-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="18980-108">Per informazioni sull'utilizzo di [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] funzionalità del provider di ruoli, vedere [procedura: utilizzare il Provider di ruoli ASP.NET con un servizio](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="18980-108">For information about using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="18980-109">La funzionalità di appartenenza richiede l'utilizzo di un database SQL Server per archiviare le informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="18980-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="18980-110">La funzionalità include anche metodi per presentare una domanda agli utenti che hanno dimenticato la password.</span><span class="sxs-lookup"><span data-stu-id="18980-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 <span data-ttu-id="18980-111">Gli sviluppatori [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] possono sfruttare queste funzionalità a fini di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="18980-111">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="18980-112">In caso di integrazione in un'applicazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], gli utenti devono fornire una combinazione di nome utente e password all'applicazione client [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18980-112">When integrated into an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="18980-113">Per trasferire i dati per il [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] del servizio, utilizzare un'associazione che supporta le credenziali di nome e password utente, ad esempio il <xref:System.ServiceModel.WSHttpBinding> (nella configurazione, il [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) e impostare le credenziali client tipo di `UserName`.</span><span class="sxs-lookup"><span data-stu-id="18980-113">To transfer the data to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="18980-114">Nel servizio, la sicurezza [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] autentica l'utente sulla base del nome utente e della password, inoltre assegna il ruolo specificato dal ruolo [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18980-114">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security authenticates the user based on the user name and password, and also assigns the role specified by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="18980-115"> non fornisce metodi per popolare il database con combinazioni di nome utente/password o altre informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="18980-115"> does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="18980-116">Per configurare il provider di appartenenza</span><span class="sxs-lookup"><span data-stu-id="18980-116">To configure the membership provider</span></span>  
  
1.  <span data-ttu-id="18980-117">Nel file Web. config sotto il <`system.web`> elemento, creare una <`membership`> elemento.</span><span class="sxs-lookup"><span data-stu-id="18980-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2.  <span data-ttu-id="18980-118">Sotto l'elemento `<membership>`, creare un elemento `<providers>`.</span><span class="sxs-lookup"><span data-stu-id="18980-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3.  <span data-ttu-id="18980-119">Come elemento figlio di <`providers`> elemento, aggiungere un `<clear />` elemento per cancellare la raccolta di provider.</span><span class="sxs-lookup"><span data-stu-id="18980-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4.  <span data-ttu-id="18980-120">Sotto il `<clear />` elemento, creare un' <`add`> elemento con i seguenti attributi impostati su valori appropriati: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, e `passwordFormat`.</span><span class="sxs-lookup"><span data-stu-id="18980-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="18980-121">L'attributo `name` viene utilizzato in seguito come valore nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18980-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="18980-122">Nell'esempio seguente viene impostato su `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="18980-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="18980-123">Nell'esempio che segue viene illustrata la sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="18980-123">The following example shows the configuration section.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Membership Provider -->  
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
      <providers>  
        <clear />  
          <add   
            name="SqlMembershipProvider"   
            type="System.Web.Security.SqlMembershipProvider"   
            connectionStringName="SqlConn"  
            applicationName="MembershipAndRoleProviderSample"  
            enablePasswordRetrieval="false"  
            enablePasswordReset="false"  
            requiresQuestionAndAnswer="false"  
            requiresUniqueEmail="true"  
            passwordFormat="Hashed" />  
      </providers>  
    </membership>  
    ```  
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="18980-124">Per configurare la sicurezza del servizio per accettare la combinazione di nome utente/password</span><span class="sxs-lookup"><span data-stu-id="18980-124">To configure service security to accept the user name/password combination</span></span>  
  
1.  <span data-ttu-id="18980-125">Nel file di configurazione, sotto il [ \<System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [ \<associazioni >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="18980-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2.  <span data-ttu-id="18980-126">Aggiungere un [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) per la sezione delle associazioni.</span><span class="sxs-lookup"><span data-stu-id="18980-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="18980-127">Per ulteriori informazioni sulla creazione di un [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] elemento di associazione vedere [procedura: specificare un'associazione al servizio nella configurazione](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="18980-127">For more information about creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3.  <span data-ttu-id="18980-128">Impostare l'attributo `mode` dell'elemento `<security>` su `Message`.</span><span class="sxs-lookup"><span data-stu-id="18980-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4.  <span data-ttu-id="18980-129">Impostare il `clientCredentialType` attributo di <`message`> elemento `UserName`.</span><span class="sxs-lookup"><span data-stu-id="18980-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="18980-130">Viene in questo modo specificato che un nome utente e una password saranno utilizzati come credenziale del client.</span><span class="sxs-lookup"><span data-stu-id="18980-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="18980-131">Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="18980-131">The following example shows the configuration code for the binding.</span></span>  
  
    ```xml  
    <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
      <!-- Set up a binding that uses UserName as the client credential type -->  
        <binding name="MembershipBinding">  
          <security mode ="Message">  
            <message clientCredentialType ="UserName"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    </system.serviceModel>  
    ```  
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="18980-132">Per configurare un servizio affinché utilizzi il provider di appartenenza</span><span class="sxs-lookup"><span data-stu-id="18980-132">To configure a service to use the membership provider</span></span>  
  
1.  <span data-ttu-id="18980-133">Come elemento figlio di `<system.serviceModel>` elemento, aggiungere un [ \<comportamenti >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) elemento</span><span class="sxs-lookup"><span data-stu-id="18980-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2.  <span data-ttu-id="18980-134">Aggiungere un [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) per il <`behaviors`> elemento.</span><span class="sxs-lookup"><span data-stu-id="18980-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3.  <span data-ttu-id="18980-135">Aggiungere un [ \<comportamento >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare il `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="18980-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="18980-136">Aggiungere un [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) per il <`behavior`> elemento.</span><span class="sxs-lookup"><span data-stu-id="18980-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5.  <span data-ttu-id="18980-137">Aggiungere un [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) per il `<serviceCredentials>` elemento.</span><span class="sxs-lookup"><span data-stu-id="18980-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6.  <span data-ttu-id="18980-138">Impostare l'attributo `userNamePasswordValidationMode` su `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="18980-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="18980-139">Se il valore `userNamePasswordValidationMode` non è impostato, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza l'autenticazione di Windows invece del provider di appartenenza [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="18980-139">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
7.  <span data-ttu-id="18980-140">Impostare l'attributo `membershipProviderName` sul nome del provider (specificato al momento di aggiungere il provider nella prima procedura in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="18980-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="18980-141">Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.</span><span class="sxs-lookup"><span data-stu-id="18980-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
          <behavior name="MyServiceBehavior">  
             <serviceCredentials>  
                <userNameAuthentication   
                userNamePasswordValidationMode="MembershipProvider"  
                membershipProviderName="SqlMembershipProvider" />  
             </serviceCredentials>  
          </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a><span data-ttu-id="18980-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="18980-142">Example</span></span>  
 <span data-ttu-id="18980-143">Nel codice seguente viene mostrata la configurazione per un servizio che utilizza la funzionalità di appartenenza ASP.</span><span class="sxs-lookup"><span data-stu-id="18980-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">  
        <endpoint address="http://microsoft.com/WCFservices/Calculator"  
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"  
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="MyServiceBehavior">  
          <serviceCredentials>  
            <userNameAuthentication   
              userNamePasswordValidationMode="MembershipProvider"  
              membershipProviderName="SqlMembershipProvider" />  
          </serviceCredentials>  
        </behavior>  
          </serviceBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="MembershipBinding">  
          <security mode="Message">  
            <message clientCredentialType="UserName" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="18980-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18980-144">See Also</span></span>  
 [<span data-ttu-id="18980-145">Procedura: Usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="18980-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="18980-146">Provider di appartenenza e di ruoli</span><span class="sxs-lookup"><span data-stu-id="18980-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
