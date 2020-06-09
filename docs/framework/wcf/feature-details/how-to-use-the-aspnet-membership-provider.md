---
title: 'Procedura: usare provider di appartenenza ASP.NET'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 840e4a5d365f2adbaf335c1061a580665a39824d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595323"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="e241d-102">Procedura: usare provider di appartenenza ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e241d-102">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="e241d-103">Il provider di appartenenze ASP.NET è una funzionalità che consente agli sviluppatori ASP.NET di creare siti Web che consentono agli utenti di creare combinazioni univoche di nome utente e password.</span><span class="sxs-lookup"><span data-stu-id="e241d-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="e241d-104">Con questa funzionalità qualsiasi utente può stabilire un account nel sito e accedere in modo esclusivo al sito e ai relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="e241d-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="e241d-105">Si tratta di una funzionalità in contrasto con la protezione di Windows, in base alla quale è necessario che gli utenti dispongano di un account in un dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="e241d-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="e241d-106">Al contrario, qualsiasi utente che fornisce le proprie credenziali (combinazione nome utente/password) può utilizzare il sito e i relativi servizi.</span><span class="sxs-lookup"><span data-stu-id="e241d-106">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="e241d-107">Per un'applicazione di esempio, vedere [appartenenza e provider di ruoli](../samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="e241d-107">For a sample application, see [Membership and Role Provider](../samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="e241d-108">Per informazioni sull'uso della funzionalità del provider di ruoli ASP.NET, vedere [procedura: usare il provider di ruoli ASP.NET con un servizio](how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="e241d-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="e241d-109">La funzionalità di appartenenza richiede l'utilizzo di un database SQL Server per archiviare le informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="e241d-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="e241d-110">La funzionalità include anche metodi per presentare una domanda agli utenti che hanno dimenticato la password.</span><span class="sxs-lookup"><span data-stu-id="e241d-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="e241d-111">Gli sviluppatori Windows Communication Foundation (WCF) possono avvalersi di queste funzionalità per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="e241d-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="e241d-112">Quando integrato in un'applicazione WCF, gli utenti devono fornire una combinazione di nome utente e password all'applicazione client WCF.</span><span class="sxs-lookup"><span data-stu-id="e241d-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="e241d-113">Per trasferire i dati al servizio WCF, utilizzare un'associazione che supporta le credenziali nome utente/password, ad esempio <xref:System.ServiceModel.WSHttpBinding> (in configurazione, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) ) e impostare il tipo di credenziale client su `UserName` .</span><span class="sxs-lookup"><span data-stu-id="e241d-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="e241d-114">Nel servizio, la sicurezza WCF autentica l'utente in base al nome utente e alla password e assegna anche il ruolo specificato dal ruolo ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e241d-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="e241d-115">WCF non fornisce metodi per popolare il database con combinazioni di nome utente/password o altre informazioni utente.</span><span class="sxs-lookup"><span data-stu-id="e241d-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="e241d-116">Per configurare il provider di appartenenza</span><span class="sxs-lookup"><span data-stu-id="e241d-116">To configure the membership provider</span></span>

1. <span data-ttu-id="e241d-117">Nel file Web. config, sotto l'elemento < `system.web` > creare un `membership` elemento < >.</span><span class="sxs-lookup"><span data-stu-id="e241d-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="e241d-118">Sotto l'elemento `<membership>`, creare un elemento `<providers>`.</span><span class="sxs-lookup"><span data-stu-id="e241d-118">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="e241d-119">Come figlio dell' `providers` elemento> <, aggiungere un `<clear />` elemento per svuotare l'insieme di provider.</span><span class="sxs-lookup"><span data-stu-id="e241d-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="e241d-120">Nell' `<clear />` elemento creare un `add` elemento <> con gli attributi seguenti impostati sui valori appropriati: `name` , `type` , `connectionStringName` , `applicationName` , `enablePasswordRetrieval` , `enablePasswordReset` , `requiresQuestionAndAnswer` , `requiresUniqueEmail` e `passwordFormat` .</span><span class="sxs-lookup"><span data-stu-id="e241d-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="e241d-121">L'attributo `name` viene utilizzato in seguito come valore nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e241d-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="e241d-122">Nell'esempio seguente viene impostato su `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="e241d-122">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="e241d-123">Nell'esempio che segue viene illustrata la sezione di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e241d-123">The following example shows the configuration section.</span></span>

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

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="e241d-124">Per configurare la sicurezza del servizio per accettare la combinazione di nome utente/password</span><span class="sxs-lookup"><span data-stu-id="e241d-124">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="e241d-125">Nel file di configurazione, sotto l' [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) elemento, aggiungere un [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) elemento.</span><span class="sxs-lookup"><span data-stu-id="e241d-125">In the configuration file, under the [\<system.serviceModel>](../../configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="e241d-126">Aggiungere un [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) alla sezione Bindings.</span><span class="sxs-lookup"><span data-stu-id="e241d-126">Add a [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="e241d-127">Per ulteriori informazioni sulla creazione di un elemento di associazione WCF, vedere [procedura: specificare un'associazione al servizio nella configurazione](../how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="e241d-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="e241d-128">Impostare l'attributo `mode` dell'elemento `<security>` su `Message`.</span><span class="sxs-lookup"><span data-stu-id="e241d-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="e241d-129">Impostare l' `clientCredentialType` attributo dell'elemento <`message`> su `UserName` .</span><span class="sxs-lookup"><span data-stu-id="e241d-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="e241d-130">Viene in questo modo specificato che un nome utente e una password saranno utilizzati come credenziale del client.</span><span class="sxs-lookup"><span data-stu-id="e241d-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="e241d-131">Nell'esempio seguente viene illustrato il codice di configurazione per l'associazione.</span><span class="sxs-lookup"><span data-stu-id="e241d-131">The following example shows the configuration code for the binding.</span></span>

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

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="e241d-132">Per configurare un servizio affinché utilizzi il provider di appartenenza</span><span class="sxs-lookup"><span data-stu-id="e241d-132">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="e241d-133">`<system.serviceModel>`Aggiungere un elemento come figlio dell'elemento [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e241d-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="e241d-134">Aggiungere un oggetto [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) all' `behaviors` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="e241d-134">Add a [\<serviceBehaviors>](../../configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="e241d-135">Aggiungere un oggetto [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) e impostare l' `name` attributo su un valore appropriato.</span><span class="sxs-lookup"><span data-stu-id="e241d-135">Add a [\<behavior>](../../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="e241d-136">Aggiungere un oggetto [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) all' `behavior` elemento <>.</span><span class="sxs-lookup"><span data-stu-id="e241d-136">Add a [\<serviceCredentials>](../../configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="e241d-137">Aggiungere un oggetto [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) all' `<serviceCredentials>` elemento.</span><span class="sxs-lookup"><span data-stu-id="e241d-137">Add a [\<userNameAuthentication>](../../configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="e241d-138">Impostare l'attributo `userNamePasswordValidationMode` su `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="e241d-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e241d-139">Se il `userNamePasswordValidationMode` valore non è impostato, WCF usa l'autenticazione di Windows anziché il provider di appartenenze ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e241d-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="e241d-140">Impostare l'attributo `membershipProviderName` sul nome del provider (specificato al momento di aggiungere il provider nella prima procedura in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="e241d-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="e241d-141">Nell'esempio seguente viene illustrato il frammento `<serviceCredentials>` fino a questo punto.</span><span class="sxs-lookup"><span data-stu-id="e241d-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

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

## <a name="example"></a><span data-ttu-id="e241d-142">Esempio</span><span class="sxs-lookup"><span data-stu-id="e241d-142">Example</span></span>

<span data-ttu-id="e241d-143">Nel codice seguente viene mostrata la configurazione per un servizio che utilizza la funzionalità di appartenenza ASP.</span><span class="sxs-lookup"><span data-stu-id="e241d-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="e241d-144">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e241d-144">See also</span></span>

- [<span data-ttu-id="e241d-145">Procedura: usare il provider di ruoli ASP.NET con un servizio</span><span class="sxs-lookup"><span data-stu-id="e241d-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="e241d-146">Provider di appartenenza e di ruoli</span><span class="sxs-lookup"><span data-stu-id="e241d-146">Membership and Role Provider</span></span>](../samples/membership-and-role-provider.md)
