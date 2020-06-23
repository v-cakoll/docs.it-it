---
title: Protezione del trasporto con l'autenticazione di base
description: Esaminare questo scenario WCF, in cui viene illustrata l'autenticazione di base per un servizio e un client WCF. Il servizio richiede un certificato valido considerato attendibile dal client.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b54f491d-196b-4279-876c-76b83ec0442c
ms.openlocfilehash: f15a19feaed631a76948efd24ee225acf789cb2d
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244855"
---
# <a name="transport-security-with-basic-authentication"></a><span data-ttu-id="cdc95-104">Protezione del trasporto con l'autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="cdc95-104">Transport Security with Basic Authentication</span></span>
<span data-ttu-id="cdc95-105">Nella figura seguente vengono illustrati un client e un servizio Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="cdc95-105">The following illustration shows a Windows Communication Foundation (WCF) service and client.</span></span> <span data-ttu-id="cdc95-106">Il server richiede un certificato X.509 valido che possa essere usato per SSL (Secure Sockets Layer) e i client devono ritenere attendibile il certificato del server.</span><span class="sxs-lookup"><span data-stu-id="cdc95-106">The server needs a valid X.509 certificate that can be used for Secure Sockets Layer (SSL), and the clients must trust the server’s certificate.</span></span> <span data-ttu-id="cdc95-107">Il servizio Web dispone già di un'implementazione SSL usabile.</span><span class="sxs-lookup"><span data-stu-id="cdc95-107">Further, the Web service already has an SSL implementation that can be used.</span></span> <span data-ttu-id="cdc95-108">Per ulteriori informazioni sull'abilitazione dell'autenticazione di base in Internet Information Services (IIS), vedere <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication> .</span><span class="sxs-lookup"><span data-stu-id="cdc95-108">For more information about enabling basic authentication on Internet Information Services (IIS), see <https://docs.microsoft.com/iis/configuration/system.webserver/security/authentication/basicauthentication>.</span></span>  
  
 ![Screenshot che mostra la sicurezza del trasporto con l'autenticazione di base.](./media/transport-security-with-basic-authentication/transport-security-basic-authentication.gif)  
  
|<span data-ttu-id="cdc95-110">Caratteristica</span><span class="sxs-lookup"><span data-stu-id="cdc95-110">Characteristic</span></span>|<span data-ttu-id="cdc95-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cdc95-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="cdc95-112">Modalità di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cdc95-112">Security Mode</span></span>|<span data-ttu-id="cdc95-113">Trasporto</span><span class="sxs-lookup"><span data-stu-id="cdc95-113">Transport</span></span>|  
|<span data-ttu-id="cdc95-114">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="cdc95-114">Interoperability</span></span>|<span data-ttu-id="cdc95-115">Con servizi e client di servizi Web esistenti</span><span class="sxs-lookup"><span data-stu-id="cdc95-115">With existing Web service clients and services</span></span>|  
|<span data-ttu-id="cdc95-116">Autenticazione (server)</span><span class="sxs-lookup"><span data-stu-id="cdc95-116">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="cdc95-117">Autenticazione (client)</span><span class="sxs-lookup"><span data-stu-id="cdc95-117">Authentication (Client)</span></span>|<span data-ttu-id="cdc95-118">Sì (usando HTTPS)</span><span class="sxs-lookup"><span data-stu-id="cdc95-118">Yes (using HTTPS)</span></span><br /><br /> <span data-ttu-id="cdc95-119">Sì (usando nome utente/password).</span><span class="sxs-lookup"><span data-stu-id="cdc95-119">Yes (through User name/Password)</span></span>|  
|<span data-ttu-id="cdc95-120">Integrità</span><span class="sxs-lookup"><span data-stu-id="cdc95-120">Integrity</span></span>|<span data-ttu-id="cdc95-121">Sì</span><span class="sxs-lookup"><span data-stu-id="cdc95-121">Yes</span></span>|  
|<span data-ttu-id="cdc95-122">Riservatezza</span><span class="sxs-lookup"><span data-stu-id="cdc95-122">Confidentiality</span></span>|<span data-ttu-id="cdc95-123">Sì</span><span class="sxs-lookup"><span data-stu-id="cdc95-123">Yes</span></span>|  
|<span data-ttu-id="cdc95-124">Trasporto</span><span class="sxs-lookup"><span data-stu-id="cdc95-124">Transport</span></span>|<span data-ttu-id="cdc95-125">HTTPS</span><span class="sxs-lookup"><span data-stu-id="cdc95-125">HTTPS</span></span>|  
|<span data-ttu-id="cdc95-126">Binding</span><span class="sxs-lookup"><span data-stu-id="cdc95-126">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="cdc95-127">Service</span><span class="sxs-lookup"><span data-stu-id="cdc95-127">Service</span></span>  
 <span data-ttu-id="cdc95-128">Il codice e la configurazione seguenti devono essere eseguiti in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="cdc95-128">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="cdc95-129">Eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdc95-129">Do one of the following:</span></span>  
  
- <span data-ttu-id="cdc95-130">Creare un servizio autonomo usando il codice senza alcuna configurazione.</span><span class="sxs-lookup"><span data-stu-id="cdc95-130">Create a stand-alone service using the code with no configuration.</span></span>  
  
- <span data-ttu-id="cdc95-131">Creare un servizio usando la configurazione fornita, ma non definire alcun endpoint.</span><span class="sxs-lookup"><span data-stu-id="cdc95-131">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cdc95-132">Codice</span><span class="sxs-lookup"><span data-stu-id="cdc95-132">Code</span></span>  
 <span data-ttu-id="cdc95-133">Nel codice seguente viene illustrato come creare un endpoint del servizio che usa un nome utente del dominio di Windows e una password per la protezione del trasferimento.</span><span class="sxs-lookup"><span data-stu-id="cdc95-133">The following code shows how to create a service endpoint that uses a Windows domain user name and password for transfer security.</span></span> <span data-ttu-id="cdc95-134">Si noti che il servizio richiede un certificato X.509 per autenticare il client.</span><span class="sxs-lookup"><span data-stu-id="cdc95-134">Note that the service requires an X.509 certificate to authenticate to the client.</span></span> <span data-ttu-id="cdc95-135">Per altre informazioni, vedere [uso dei certificati](working-with-certificates.md) e [procedura: configurare una porta con un certificato SSL](how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="cdc95-135">For more information, see [Working with Certificates](working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#1)]
 [!code-vb[C_SecurityScenarios#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#1)]  
  
## <a name="configuration"></a><span data-ttu-id="cdc95-136">Configurazione</span><span class="sxs-lookup"><span data-stu-id="cdc95-136">Configuration</span></span>  
 <span data-ttu-id="cdc95-137">Gli elementi seguenti configurano un servizio per l'uso dell'autenticazione di base con protezione a livello di trasporto:</span><span class="sxs-lookup"><span data-stu-id="cdc95-137">The following configures a service to use basic authentication with transport-level security:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <wsHttpBinding>  
                <binding name="UsernameWithTransport">  
                    <security mode="Transport">  
                        <transport clientCredentialType="Basic" />  
                    </security>  
                </binding>  
            </wsHttpBinding>  
        </bindings>  
        <services>  
            <service name="BasicAuthentication.Calculator">  
                <endpoint address="https://localhost/Calculator"  
                          binding="wsHttpBinding"
                          bindingConfiguration="UsernameWithTransport"  
                          name="BasicEndpoint"
                          contract="BasicAuthentication.ICalculator" />  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="cdc95-138">Client</span><span class="sxs-lookup"><span data-stu-id="cdc95-138">Client</span></span>  
  
### <a name="code"></a><span data-ttu-id="cdc95-139">Codice</span><span class="sxs-lookup"><span data-stu-id="cdc95-139">Code</span></span>  
 <span data-ttu-id="cdc95-140">Nell'esempio di codice seguente viene mostrato il codice client che include il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="cdc95-140">The following code shows the client code that includes the user name and password.</span></span> <span data-ttu-id="cdc95-141">Si noti che l'utente deve fornire un nome utente e una password di Windows validi.</span><span class="sxs-lookup"><span data-stu-id="cdc95-141">Note that the user must provide a valid Windows user name and password.</span></span> <span data-ttu-id="cdc95-142">Il codice per restituire il nome utente e la password non è incluso.</span><span class="sxs-lookup"><span data-stu-id="cdc95-142">The code to return the user name and password is not shown here.</span></span> <span data-ttu-id="cdc95-143">Usare una finestra di dialogo o un'altra interfaccia per eseguire una query per ottenere tali informazioni dall'utente.</span><span class="sxs-lookup"><span data-stu-id="cdc95-143">Use a dialog box or other interface to query the user for the information.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cdc95-144">Nome utente e password possono essere impostati solo tramite codice.</span><span class="sxs-lookup"><span data-stu-id="cdc95-144">User name and password can only be set using code.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#2)]
 [!code-vb[C_SecurityScenarios#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#2)]  
  
### <a name="configuration"></a><span data-ttu-id="cdc95-145">Configurazione</span><span class="sxs-lookup"><span data-stu-id="cdc95-145">Configuration</span></span>  
 <span data-ttu-id="cdc95-146">Nel codice seguente viene mostrata la configurazione client.</span><span class="sxs-lookup"><span data-stu-id="cdc95-146">The following code shows the client configuration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cdc95-147">Non è possibile usare la configurazione per impostare il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="cdc95-147">You cannot use configuration to set the user name and password.</span></span> <span data-ttu-id="cdc95-148">La configurazione mostrata deve essere ampliata usando il codice per impostare il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="cdc95-148">The configuration shown here must be augmented using code to set the user name and password.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Transport">  
            <transport clientCredentialType="Basic" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cdc95-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdc95-149">See also</span></span>

- <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- [<span data-ttu-id="cdc95-150">Working with Certificates</span><span class="sxs-lookup"><span data-stu-id="cdc95-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="cdc95-151">Procedura: configurare una porta con un certificato SSL</span><span class="sxs-lookup"><span data-stu-id="cdc95-151">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="cdc95-152">Panoramica della sicurezza</span><span class="sxs-lookup"><span data-stu-id="cdc95-152">Security Overview</span></span>](security-overview.md)
- [\<clientCredentials>](../../configure-apps/file-schema/wcf/clientcredentials.md)
- <span data-ttu-id="cdc95-153">[Sicurezza e protezione](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="cdc95-153">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
