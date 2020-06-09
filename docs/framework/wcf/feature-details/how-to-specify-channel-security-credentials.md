---
title: 'Procedura: specificare credenziali di sicurezza del canale'
ms.date: 03/30/2017
ms.assetid: f8e03f47-9c4f-4dd5-8f85-429e6d876119
ms.openlocfilehash: 45a13460ce94cbacae0465fede4b455a2833ce81
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596942"
---
# <a name="how-to-specify-channel-security-credentials"></a><span data-ttu-id="e561f-102">Procedura: specificare credenziali di sicurezza del canale</span><span class="sxs-lookup"><span data-stu-id="e561f-102">How to: Specify Channel Security Credentials</span></span>
<span data-ttu-id="e561f-103">Il moniker del servizio Windows Communication Foundation (WCF) consente alle applicazioni COM di chiamare i servizi WCF.</span><span class="sxs-lookup"><span data-stu-id="e561f-103">The Windows Communication Foundation (WCF) Service Moniker allows COM applications to call WCF services.</span></span> <span data-ttu-id="e561f-104">Per la maggior parte dei servizi WCF è necessario che il client specifichi le credenziali per l'autenticazione e l'autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="e561f-104">Most WCF services require the client to specify credentials for authentication and authorization.</span></span> <span data-ttu-id="e561f-105">Quando si chiama un servizio WCF da un client WCF, è possibile specificare queste credenziali nel codice gestito o in un file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="e561f-105">When calling a WCF service from a WCF client, you can specify these credentials in managed code or in an application configuration file.</span></span> <span data-ttu-id="e561f-106">Quando si chiama un servizio WCF da un'applicazione COM, è possibile usare l' <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interfaccia per specificare le credenziali.</span><span class="sxs-lookup"><span data-stu-id="e561f-106">When calling a WCF service from a COM application, you can use the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface to specify credentials.</span></span> <span data-ttu-id="e561f-107">In questo argomento vengono illustrate varie modalità di specifica delle credenziali mediante l'interfaccia <xref:System.ServiceModel.ComIntegration.IChannelCredentials>.</span><span class="sxs-lookup"><span data-stu-id="e561f-107">This topic will illustrate various ways to specify credentials using the <xref:System.ServiceModel.ComIntegration.IChannelCredentials> interface.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e561f-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> è un'interfaccia basata su IDispatch nella quale non viene visualizzata la funzionalità IntelliSense nell'ambiente Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e561f-108"><xref:System.ServiceModel.ComIntegration.IChannelCredentials> is an IDispatch-based interface and you will not get IntelliSense functionality in the Visual Studio environment.</span></span>  
  
 <span data-ttu-id="e561f-109">In questo articolo verrà utilizzato il servizio WCF definito nell' [esempio relativo alla sicurezza dei messaggi](../samples/message-security-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e561f-109">This article will use the WCF service defined in the [Message Security Sample](../samples/message-security-sample.md).</span></span>  
  
### <a name="to-specify-a-client-certificate"></a><span data-ttu-id="e561f-110">Per specificare un certificato client</span><span class="sxs-lookup"><span data-stu-id="e561f-110">To specify a client certificate</span></span>  
  
1. <span data-ttu-id="e561f-111">Eseguire il file Setup.bat nella directory della protezione messaggi per creare e installare i certificati di prova obbligatori.</span><span class="sxs-lookup"><span data-stu-id="e561f-111">Run the Setup.bat file in the Message Security directory to create and install the required test certificates.</span></span>  
  
2. <span data-ttu-id="e561f-112">Aprire il progetto Message Security.</span><span class="sxs-lookup"><span data-stu-id="e561f-112">Open the Message Security project.</span></span>  
  
3. <span data-ttu-id="e561f-113">Aggiungere `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` alla `ICalculator` definizione dell'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e561f-113">Add `[ServiceBehavior(Namespace="http://Microsoft.ServiceModel.Samples")]` to the `ICalculator` interface definition.</span></span>  
  
4. <span data-ttu-id="e561f-114">Aggiungere `bindingNamespace="http://Microsoft.ServiceModel.Samples"` al tag dell'endpoint nel file app. config per il servizio.</span><span class="sxs-lookup"><span data-stu-id="e561f-114">Add `bindingNamespace="http://Microsoft.ServiceModel.Samples"` to the endpoint tag in the App.config for the service.</span></span>  
  
5. <span data-ttu-id="e561f-115">Compilare l'esempio di sicurezza dei messaggi ed eseguire Service.exe.</span><span class="sxs-lookup"><span data-stu-id="e561f-115">Build the Message Security Sample and run Service.exe.</span></span> <span data-ttu-id="e561f-116">Utilizzare Internet Explorer e passare all'URI del servizio ( `http://localhost:8000/ServiceModelSamples/Service` ) per assicurarsi che il servizio sia funzionante.</span><span class="sxs-lookup"><span data-stu-id="e561f-116">Use Internet Explorer and browse to the service's URI (`http://localhost:8000/ServiceModelSamples/Service`) to ensure that the service is working.</span></span>  
  
6. <span data-ttu-id="e561f-117">Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="e561f-117">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="e561f-118">Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:</span><span class="sxs-lookup"><span data-stu-id="e561f-118">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb  
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
        monString = monString + ", binding=BasicHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
        Set monikerProxy = GetObject(monString)  
  
        'Set the Service Certificate.  
     monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetDefaultServiceCertificateFromStore "CurrentUser", "TrustedPeople", "FindBySubjectName", "localhost"  
  
        'Set the Client Certificate.  
        monikerProxy.ChannelCredentials.SetClientCertificateFromStoreByName "CN=client.com", "CurrentUser", "My"  
        MsgBox monikerProxy.Add(3, 4)  
    ```  
  
7. <span data-ttu-id="e561f-119">Eseguire l'applicazione Visual Basic e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e561f-119">Run the Visual Basic application and verify the results.</span></span>  
  
     <span data-ttu-id="e561f-120">Nell'applicazione Visual Basic verrà visualizzata una finestra di messaggio con il risultato relativo alla chiamata di Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="e561f-120">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span> <span data-ttu-id="e561f-121">Per impostare il certificato client è inoltre possibile usare <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> o <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> al posto di <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29>:</span><span class="sxs-lookup"><span data-stu-id="e561f-121"><xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromFile%28System.String%2CSystem.String%2CSystem.String%29> or <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStoreByName%28System.String%2CSystem.String%2CSystem.String%29> can also be used in place of <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetClientCertificateFromStore%28System.String%2CSystem.String%2CSystem.String%2CSystem.Object%29> to set the Client Certificate:</span></span>  
  
    ```vb  
    monikerProxy.ChannelCredentials.SetClientCertificateFromFile "C:\MyClientCert.pfx", "password", "DefaultKeySet"  
    ```  
  
> [!NOTE]
> <span data-ttu-id="e561f-122">Perché questa chiamata venga eseguita correttamente, il certificato client deve essere considerato attendibile nel computer in cui è in esecuzione il client.</span><span class="sxs-lookup"><span data-stu-id="e561f-122">For this call to work, the client certificate needs to be trusted on the machine the client is running on.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e561f-123">Se il formato del moniker non è valido o se il servizio non è disponibile, la chiamata a `GetObject` restituirà un errore di sintassi non valida.</span><span class="sxs-lookup"><span data-stu-id="e561f-123">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span> <span data-ttu-id="e561f-124">Se si riceve questo errore, verificare che il moniker che si sta usando sia valido e che il servizio sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="e561f-124">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
### <a name="to-specify-user-name-and-password"></a><span data-ttu-id="e561f-125">Per specificare un nome utente e una password</span><span class="sxs-lookup"><span data-stu-id="e561f-125">To specify user name and password</span></span>  
  
1. <span data-ttu-id="e561f-126">Modificare il file Service App.config per usare `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="e561f-126">Modify the Service App.config file to use the `wsHttpBinding`.</span></span> <span data-ttu-id="e561f-127">Questa operazione è necessaria per la convalida del nome utente e della password.</span><span class="sxs-lookup"><span data-stu-id="e561f-127">This is required for user name and password validation:</span></span>  

2. <span data-ttu-id="e561f-128">Impostare `clientCredentialType` su UserName:</span><span class="sxs-lookup"><span data-stu-id="e561f-128">Set the `clientCredentialType` to UserName:</span></span>  

3. <span data-ttu-id="e561f-129">Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="e561f-129">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="e561f-130">Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:</span><span class="sxs-lookup"><span data-stu-id="e561f-130">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set monikerProxy = GetObject(monString)  
  
    monikerProxy.ChannelCredentials.SetServiceCertificateAuthentication "CurrentUser", "NoCheck", "PeerOrChainTrust"  
    monikerProxy.ChannelCredentials.SetUserNameCredential "username", "password"  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
4. <span data-ttu-id="e561f-131">Eseguire l'applicazione Visual Basic e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e561f-131">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="e561f-132">Nell'applicazione Visual Basic verrà visualizzata una finestra di messaggio con il risultato relativo alla chiamata di Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="e561f-132">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e561f-133">L'associazione specificata nel moniker del servizio in questo esempio è stata impostata su WSHttpBinding_ICalculator.</span><span class="sxs-lookup"><span data-stu-id="e561f-133">The binding specified in the service moniker in this sample has been changed to WSHttpBinding_ICalculator.</span></span> <span data-ttu-id="e561f-134">Nella chiamata a <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29> è inoltre necessario fornire un nome utente e una password validi.</span><span class="sxs-lookup"><span data-stu-id="e561f-134">Also note that you must supply a valid user name and password in the call to <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetUserNameCredential%28System.String%2CSystem.String%29>.</span></span>  
  
### <a name="to-specify-windows-credentials"></a><span data-ttu-id="e561f-135">Per specificare credenziali di Windows.</span><span class="sxs-lookup"><span data-stu-id="e561f-135">To specify Windows Credentials</span></span>  
  
1. <span data-ttu-id="e561f-136">Impostare `clientCredentialType` su Windows nel file App.config del servizio:</span><span class="sxs-lookup"><span data-stu-id="e561f-136">Set `clientCredentialType` to Windows in the Service App.config file:</span></span>  

2. <span data-ttu-id="e561f-137">Aprire Visual Basic 6.0 e creare un nuovo file standard con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="e561f-137">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="e561f-138">Aggiungere un pulsante al form e fare doppio clic su di esso per aggiungere il codice seguente al gestore Click:</span><span class="sxs-lookup"><span data-stu-id="e561f-138">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
    monString = monString + ", address=http://localhost:8000/ServiceModelSamples/Service"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", upnidentity=domain\userID"  
  
    Set monikerProxy = GetObject(monString)  
     monikerProxy.ChannelCredentials.SetWindowsCredential "domain", "userID", "password", 1, True  
  
    MsgBox monikerProxy.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="e561f-139">Eseguire l'applicazione Visual Basic e verificare i risultati.</span><span class="sxs-lookup"><span data-stu-id="e561f-139">Run the Visual Basic application and verify the results.</span></span> <span data-ttu-id="e561f-140">Nell'applicazione Visual Basic verrà visualizzata una finestra di messaggio con il risultato relativo alla chiamata di Add(3, 4).</span><span class="sxs-lookup"><span data-stu-id="e561f-140">The Visual Basic application will display a message box with the result from calling Add(3, 4).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e561f-141">È necessario sostituire "dominio", "IDUtente" e "password" con valori validi.</span><span class="sxs-lookup"><span data-stu-id="e561f-141">You must replace "domain", "userID", and "password" with valid values.</span></span>  
  
### <a name="to-specify-an-issue-token"></a><span data-ttu-id="e561f-142">Per specificare un token di pubblicazione</span><span class="sxs-lookup"><span data-stu-id="e561f-142">To specify an issue token</span></span>  
  
1. <span data-ttu-id="e561f-143">I token di pubblicazione vengono usati soltanto per applicazioni che usano la protezione federata.</span><span class="sxs-lookup"><span data-stu-id="e561f-143">Issue tokens are used only for applications using federated security.</span></span> <span data-ttu-id="e561f-144">Per altre informazioni sulla sicurezza federata, vedere [Federazione e token emessi](federation-and-issued-tokens.md) ed [esempio di Federazione](../samples/federation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="e561f-144">For more information about federated security, see [Federation and Issued Tokens](federation-and-issued-tokens.md) and [Federation Sample](../samples/federation-sample.md).</span></span>  
  
     <span data-ttu-id="e561f-145">L'esempio di codice Visual Basic seguente mostra come chiamare il metodo <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>:</span><span class="sxs-lookup"><span data-stu-id="e561f-145">The following Visual Basic code example illustrates how to call the <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29> method:</span></span>  
  
    ```vb
        monString = "service:mexAddress=http://localhost:8000/ServiceModelSamples/Service?wsdl"  
        monString = monString + ", address=http://localhost:8000/SomeService/Service"  
        monString = monString + ", contract=ICalculator, contractNamespace=http://SomeService.Samples"  
        monString = monString + ", binding=WSHttpBinding_ISomeContract, bindingNamespace=http://SomeService.Samples"  
  
        Set monikerProxy = GetObject(monString)  
    monikerProxy.SetIssuedToken("http://somemachine/sts", "bindingType", "binding")  
    ```  
  
     <span data-ttu-id="e561f-146">Per altre informazioni sui parametri relativi a questo metodo, vedere <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span><span class="sxs-lookup"><span data-stu-id="e561f-146">For more information about the parameters for this method, see <xref:System.ServiceModel.ComIntegration.IChannelCredentials.SetIssuedToken%28System.String%2CSystem.String%2CSystem.String%29>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e561f-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e561f-147">See also</span></span>

- [<span data-ttu-id="e561f-148">Federazione</span><span class="sxs-lookup"><span data-stu-id="e561f-148">Federation</span></span>](federation.md)
- [<span data-ttu-id="e561f-149">Procedura: configurare le credenziali in un servizio federativo</span><span class="sxs-lookup"><span data-stu-id="e561f-149">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)
- [<span data-ttu-id="e561f-150">Procedura: creare un client federato</span><span class="sxs-lookup"><span data-stu-id="e561f-150">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)
- [<span data-ttu-id="e561f-151">Sicurezza dei messaggi</span><span class="sxs-lookup"><span data-stu-id="e561f-151">Message Security</span></span>](message-security-in-wcf.md)
- [<span data-ttu-id="e561f-152">Associazioni e protezione</span><span class="sxs-lookup"><span data-stu-id="e561f-152">Bindings and Security</span></span>](bindings-and-security.md)
