---
title: 'Procedura: autenticare con un nome utente e una password'
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: e8dc9177afc590a6467855decfa8450b37c6fc77
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601283"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a><span data-ttu-id="d5254-102">Procedura: autenticare con un nome utente e una password</span><span class="sxs-lookup"><span data-stu-id="d5254-102">How to: Authenticate with a User Name and Password</span></span>

<span data-ttu-id="d5254-103">In questo argomento viene illustrato come abilitare un servizio Windows Communication Foundation (WCF) per autenticare un client con un nome utente e una password di dominio Windows.</span><span class="sxs-lookup"><span data-stu-id="d5254-103">This topic demonstrates how to enable a Windows Communication Foundation (WCF) service to authenticate a client with a Windows domain username and password.</span></span> <span data-ttu-id="d5254-104">Si presuppone che l'utente disponga di un servizio WCF self-hosted funzionante.</span><span class="sxs-lookup"><span data-stu-id="d5254-104">It assumes you have a working, self-hosted WCF service.</span></span> <span data-ttu-id="d5254-105">Per un esempio di creazione di un servizio WCF self-hosted di base, vedere [Introduzione esercitazione](../getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="d5254-105">For an example of creating a basic self-hosted WCF service see, [Getting Started Tutorial](../getting-started-tutorial.md).</span></span> <span data-ttu-id="d5254-106">In questo argomento si presuppone che il servizio sia configurato tramite codice.</span><span class="sxs-lookup"><span data-stu-id="d5254-106">This topic assumes the service is configured in code.</span></span> <span data-ttu-id="d5254-107">Per un esempio di configurazione di un servizio simile usando un file di configurazione, vedere [nome utente](../samples/message-security-user-name.md)per la sicurezza dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="d5254-107">If you would like to see an example of configuring a similar service using a configuration file, see [Message Security User Name](../samples/message-security-user-name.md).</span></span>

<span data-ttu-id="d5254-108">Per configurare un servizio in modo che effettui l'autenticazione dei client mediante il nome utente e la password di dominio Windows, utilizzare l'oggetto <xref:System.ServiceModel.WSHttpBinding> e impostare la relativa proprietà `Security.Mode` su `Message`.</span><span class="sxs-lookup"><span data-stu-id="d5254-108">To configure a service to authenticate its clients using Windows Domain username and passwords use the <xref:System.ServiceModel.WSHttpBinding> and set its `Security.Mode` property to `Message`.</span></span> <span data-ttu-id="d5254-109">Inoltre, è necessario specificare un certificato X509 che verrà utilizzato per crittografare il nome utente e la password quando vengono inviati dal client al servizio.</span><span class="sxs-lookup"><span data-stu-id="d5254-109">In addition you must specify an X509 certificate that will be used to encrypt the username and password as they are sent from the client to the service.</span></span>

<span data-ttu-id="d5254-110">Nel client è necessario richiedere all'utente il nome utente e la password e specificare le credenziali dell'utente nel proxy client WCF.</span><span class="sxs-lookup"><span data-stu-id="d5254-110">On the client, you must prompt the user for the username and password and specify the user’s credentials on the WCF client proxy.</span></span>

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a><span data-ttu-id="d5254-111">Per configurare un servizio WCF per l'autenticazione tramite nome utente e password di dominio Windows</span><span class="sxs-lookup"><span data-stu-id="d5254-111">To configure a WCF service to authenticate using Windows domain username and password</span></span>

1. <span data-ttu-id="d5254-112">Creare un'istanza dell'oggetto <xref:System.ServiceModel.WSHttpBinding>, impostare la modalità di sicurezza dell'associazione su <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, impostare l'oggetto `ClientCredentialType` dell'associazione su <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> e aggiungere un endpoint del servizio utilizzando l'associazione configurata all'host del servizio come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d5254-112">Create an instance of the <xref:System.ServiceModel.WSHttpBinding>, set the security mode of the binding to <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, set the `ClientCredentialType` of the binding to <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType>, and add a service endpoint using the configured binding to the service host as shown in the following code:</span></span>

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. <span data-ttu-id="d5254-113">Specificare il certificato del server utilizzato per crittografare le informazioni relative al nome utente e alla password inviate tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="d5254-113">Specify the server certificate used to encrypt the username and password information sent over the wire.</span></span> <span data-ttu-id="d5254-114">Questo codice deve seguire immediatamente il codice illustrato sopra.</span><span class="sxs-lookup"><span data-stu-id="d5254-114">This code should immediately follow the code above.</span></span> <span data-ttu-id="d5254-115">Nell'esempio seguente viene utilizzato il certificato creato dal file Setup. bat dall'esempio di [nome utente](../samples/message-security-user-name.md) per la sicurezza dei messaggi:</span><span class="sxs-lookup"><span data-stu-id="d5254-115">The following example uses the certificate that is created by the setup.bat file from the [Message Security User Name](../samples/message-security-user-name.md) sample:</span></span>

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    <span data-ttu-id="d5254-116">È possibile utilizzare il proprio certificato; è sufficiente modificare il codice in modo che faccia riferimento a tale certificato.</span><span class="sxs-lookup"><span data-stu-id="d5254-116">You can use your own certificate, just modify the code to refer to your certificate.</span></span> <span data-ttu-id="d5254-117">Per ulteriori informazioni sulla creazione e sull'utilizzo di certificati, vedere [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="d5254-117">For more information about creating and using certificates see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="d5254-118">Assicurarsi che il certificato si trovi nell'archivio certificati Persone attendibili del computer locale.</span><span class="sxs-lookup"><span data-stu-id="d5254-118">Make sure the certificate is in the Trusted People certificate store for the Local Machine.</span></span> <span data-ttu-id="d5254-119">Per eseguire questa operazione, è possibile eseguire MMC. exe e selezionare la voce di menu **file**, **Aggiungi/Rimuovi snap-in** .</span><span class="sxs-lookup"><span data-stu-id="d5254-119">You can do this by running mmc.exe and selecting the **File**, **Add/Remove Snap-in...** menu item.</span></span> <span data-ttu-id="d5254-120">Nella finestra di dialogo **Aggiungi o Rimuovi snap-** in selezionare lo **snap-in certificati** e fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="d5254-120">In the **Add or Remove Snap-ins** dialog, select the **Certificates snap-in** and click **Add**.</span></span> <span data-ttu-id="d5254-121">Nella finestra di dialogo snap-in certificati selezionare **account computer**.</span><span class="sxs-lookup"><span data-stu-id="d5254-121">In the Certificates Snap-in dialog select **Computer account**.</span></span> <span data-ttu-id="d5254-122">Per impostazione predefinita, il certificato generato nell'esempio di sicurezza dei messaggi tramite nome utente sarà posizionato nella cartella Personale/Certificati,</span><span class="sxs-lookup"><span data-stu-id="d5254-122">By default the certificate generated from the Message Security User name sample will be located in the Personal/Certificates folder.</span></span>  <span data-ttu-id="d5254-123">Verrà elencato come "localhost" nella colonna rilasciato a nella finestra MMC.</span><span class="sxs-lookup"><span data-stu-id="d5254-123">It will be listed as "localhost" under the Issued to column in the MMC window.</span></span> <span data-ttu-id="d5254-124">Trascinare e rilasciare il certificato nella cartella **persone attendibili** .</span><span class="sxs-lookup"><span data-stu-id="d5254-124">Drag and drop the certificate into the **Trusted People** folder.</span></span> <span data-ttu-id="d5254-125">In questo modo il certificato verrà considerato come attendibile da WCF quando viene effettuata l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="d5254-125">This will allow WCF to treat the certificate as a trusted certificate when performing authentication.</span></span>

## <a name="to-call-the-service-passing-username-and-password"></a><span data-ttu-id="d5254-126">Per chiamare il servizio passando nome utente e password</span><span class="sxs-lookup"><span data-stu-id="d5254-126">To call the service passing username and password</span></span>

1. <span data-ttu-id="d5254-127">L'applicazione client deve richiedere all'utente il nome utente e la password.</span><span class="sxs-lookup"><span data-stu-id="d5254-127">The client application must prompt the user for their username and password.</span></span> <span data-ttu-id="d5254-128">Il codice seguente chiede all'utente il nome utente e la password:</span><span class="sxs-lookup"><span data-stu-id="d5254-128">The following code asks the user for username and password:</span></span>

    > [!WARNING]
    > <span data-ttu-id="d5254-129">Questo codice non deve essere utilizzato in produzione poiché la password viene visualizzata durante l'immissione.</span><span class="sxs-lookup"><span data-stu-id="d5254-129">This code should not be used in production as the password is displayed while being entered.</span></span>

    ```csharp
    public static void GetPassword(out string username, out string password)
    {
        Console.WriteLine("Provide a valid machine or domain account. [domain\\user]");
        Console.WriteLine("   Enter username:");
        username = Console.ReadLine();
        Console.WriteLine("   Enter password:");
        password = Console.ReadLine();
    }
    ```

2. <span data-ttu-id="d5254-130">Creare un'istanza del proxy client specificando le credenziali del client, come illustrato nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="d5254-130">Create an instance of the client proxy specifying the client's credentials as shown in the following code:</span></span>

    ```csharp
    string username;
    string password;

    // Instantiate the proxy.
    var proxy = new Service1Client();

    // Prompt the user for username & password.
    GetPassword(out username, out password);

    // Set the user's credentials on the proxy.
    proxy.ClientCredentials.UserName.UserName = username;
    proxy.ClientCredentials.UserName.Password = password;

    // Treat the test certificate as trusted.
    proxy.ClientCredentials.ServiceCertificate.Authentication.CertificateValidationMode = System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust;
    // Call the service operation using the proxy
    ```

## <a name="see-also"></a><span data-ttu-id="d5254-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5254-131">See also</span></span>

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [<span data-ttu-id="d5254-132">Protezione del trasporto con l'autenticazione di base</span><span class="sxs-lookup"><span data-stu-id="d5254-132">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)
- [<span data-ttu-id="d5254-133">Protezione delle applicazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="d5254-133">Distributed Application Security</span></span>](distributed-application-security.md)
- [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
