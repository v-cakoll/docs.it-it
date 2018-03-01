---
title: 'Procedura: autenticare con un nome utente e una password'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1554e8594a611aa75876d14ee7ad0689932372e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="a23a6-102">Procedura: autenticare con un nome utente e una password</span><span class="sxs-lookup"><span data-stu-id="a23a6-102">How to: Authenticate with a User Name and Password</span></span>
<span data-ttu-id="a23a6-103">In questo argomento viene illustrato come abilitare l'autenticazione di un client con un nome utente e una password di dominio Windows in un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a23a6-103">This topic demonstrates how to enable a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="a23a6-104">Si presuppone che l'utente disponga di un servizio WCF self-hosted funzionante.</span><span class="sxs-lookup"><span data-stu-id="a23a6-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="a23a6-105">Per un esempio di creazione di base vedere servizio WCF self-hosted, [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="a23a6-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span> <span data-ttu-id="a23a6-106">In questo argomento si presuppone che il servizio sia configurato tramite codice.</span><span class="sxs-lookup"><span data-stu-id="a23a6-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="a23a6-107">Se si desidera vedere un esempio di configurazione di un servizio simile utilizzando un file di configurazione vedere [nome utente di sicurezza messaggio](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span><span class="sxs-lookup"><span data-stu-id="a23a6-107">If you would like to see an example of configuring a similar service using a configuration file see [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md)</span></span>  
  
 <span data-ttu-id="a23a6-108">Per configurare un servizio per l'autenticazione dei client mediante l'utilizzo di nomi utente e password di dominio Windows di <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> e impostare il relativo `Security.Mode` proprietà `Message`.</span><span class="sxs-lookup"><span data-stu-id="a23a6-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="a23a6-109">Inoltre, è necessario specificare un certificato X509 che verrà utilizzato per crittografare il nome utente e la password quando vengono inviati dal client al servizio.</span><span class="sxs-lookup"><span data-stu-id="a23a6-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>  
  
 <span data-ttu-id="a23a6-110">Nel client è necessario richiedere all'utente il nome utente e la password e specificare le credenziali dell'utente nel proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="a23a6-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="a23a6-111">Per configurare un servizio WCF per l'autenticazione tramite nome utente e password di dominio Windows</span><span class="sxs-lookup"><span data-stu-id="a23a6-111">To configure a WCF service to authenticate using Windows domain username and password.</span></span>  
  
1.  <span data-ttu-id="a23a6-112">Creare un'istanza del <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, impostare la modalità di sicurezza dell'associazione `SecurityMode.Message`, impostare il `ClientCredentialType` dell'associazione `MessageCredentialType.UserName`e aggiungere un endpoint del servizio utilizzando l'associazione configurata all'host del servizio, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a23a6-112">Create an instance of the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, set the security mode of the binding to `SecurityMode.Message`, set the `ClientCredentialType` of the binding to `MessageCredentialType.UserName`, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  <span data-ttu-id="a23a6-113">Specificare il certificato del server utilizzato per crittografare le informazioni relative al nome utente e alla password inviate tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="a23a6-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="a23a6-114">Questo codice deve seguire immediatamente il codice illustrato sopra.</span><span class="sxs-lookup"><span data-stu-id="a23a6-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="a23a6-115">L'esempio seguente usa il certificato viene creato per il file setup.bat dal [nome utente di sicurezza messaggio](../../../../docs/framework/wcf/samples/message-security-user-name.md) esempio:</span><span class="sxs-lookup"><span data-stu-id="a23a6-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../../../../docs/framework/wcf/samples/message-security-user-name.md) sample:</span></span>  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     <span data-ttu-id="a23a6-116">È possibile utilizzare il proprio certificato; è sufficiente modificare il codice in modo che faccia riferimento a tale certificato.</span><span class="sxs-lookup"><span data-stu-id="a23a6-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="a23a6-117">Per ulteriori informazioni sulla creazione e utilizzo di certificati vedere [utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="a23a6-117">For more information about creating and using certificates see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="a23a6-118">Assicurarsi che il certificato si trovi nell'archivio certificati Persone attendibili del computer locale.</span><span class="sxs-lookup"><span data-stu-id="a23a6-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="a23a6-119">È possibile farlo eseguendo mmc.exe e scegliendo il **File**, **Aggiungi/Rimuovi Snap-in...**  voce di menu.</span><span class="sxs-lookup"><span data-stu-id="a23a6-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="a23a6-120">Nel **Aggiungi o Rimuovi Snap-in** finestra di dialogo Seleziona il **snap-in certificati** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a23a6-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="a23a6-121">Nella finestra di dialogo Snap-in certificati selezionare **account Computer**.</span><span class="sxs-lookup"><span data-stu-id="a23a6-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="a23a6-122">Per impostazione predefinita, il certificato generato nell'esempio di sicurezza dei messaggi tramite nome utente sarà posizionato nella cartella Personale/Certificati,</span><span class="sxs-lookup"><span data-stu-id="a23a6-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="a23a6-123">Sarà elencato come "localhost" con la colonna rilasciato a della finestra di MMC.</span><span class="sxs-lookup"><span data-stu-id="a23a6-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="a23a6-124">Trascinare e rilasciare il certificato di **persone attendibili** cartella.</span><span class="sxs-lookup"><span data-stu-id="a23a6-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="a23a6-125">In questo modo il certificato verrà considerato come attendibile da WCF quando viene effettuata l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="a23a6-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>  
  
### <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="a23a6-126">Per chiamare il servizio passando nome utente e password</span><span class="sxs-lookup"><span data-stu-id="a23a6-126">To call the service passing username and password</span></span>  
  
1.  <span data-ttu-id="a23a6-127">L'applicazione client deve richiedere all'utente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="a23a6-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="a23a6-128">Il codice seguente richiede all'utente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="a23a6-128">The following code asks the user for username and password.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="a23a6-129">Questo codice non deve essere utilizzato in produzione poiché la password viene visualizzata durante l'immissione.</span><span class="sxs-lookup"><span data-stu-id="a23a6-129">This code should not be used in production as the password is displayed while being entered.</span></span>  
  
    ```  
    public static void GetPassword(out string username, out string password)  
            {  
                Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");  
                Console.WriteLine("   Enter username:");  
                username = Console.ReadLine();  
                Console.WriteLine("   Enter password:");  
                password = Console.ReadLine();             
                return;  
            }  
    ```  
  
2.  <span data-ttu-id="a23a6-130">Creare un'istanza del proxy client specificando le credenziali del client come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="a23a6-130">Create an instance of the client proxy specifying the client’s credentials as shown in the following code:</span></span>  
  
    ```  
    string username;  
    string password;  
  
    // Instantiate the proxy  
    Service1Client proxy = new Service1Client();  
  
    // Prompt the user for username & password  
    GetPassword(out username, out password);  
  
    // Set the user’s credentials on the proxy  
    proxy.ClientCredentials.UserName.UserName = username;  
    proxy.ClientCredentials.UserName.Password = password;  
  
    // Treat the test certificate as trusted  
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;  
    // Call the service operation using the proxy  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a23a6-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a23a6-131">See Also</span></span>  
 <span data-ttu-id="a23a6-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="a23a6-132"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`></span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [<span data-ttu-id="a23a6-133">Sicurezza del trasporto con autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="a23a6-133">Transport Security with Basic Authentication</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [<span data-ttu-id="a23a6-134">Sicurezza delle applicazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="a23a6-134">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="a23a6-135">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a23a6-135">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
