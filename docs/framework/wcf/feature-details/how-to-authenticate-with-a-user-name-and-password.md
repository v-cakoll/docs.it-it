---
title: 'Procedura: autenticare con un nome utente e una password'
description: Informazioni su come abilitare un servizio WCF per autenticare un client usando un nome utente e una password di dominio Windows, con codice di esempio.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: 1f938f8041b2577b3705266948f29b42f23a6fd7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247247"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Procedura: autenticare con un nome utente e una password

In questo argomento viene illustrato come abilitare un servizio Windows Communication Foundation (WCF) per autenticare un client con un nome utente e una password di dominio Windows. Si presuppone che l'utente disponga di un servizio WCF self-hosted funzionante. Per un esempio di creazione di un servizio WCF self-hosted di base, vedere [Introduzione esercitazione](../getting-started-tutorial.md). In questo argomento si presuppone che il servizio sia configurato tramite codice. Per un esempio di configurazione di un servizio simile usando un file di configurazione, vedere [nome utente](../samples/message-security-user-name.md)per la sicurezza dei messaggi.

Per configurare un servizio in modo che effettui l'autenticazione dei client mediante il nome utente e la password di dominio Windows, utilizzare l'oggetto <xref:System.ServiceModel.WSHttpBinding> e impostare la relativa proprietà `Security.Mode` su `Message`. Inoltre, è necessario specificare un certificato X509 che verrà utilizzato per crittografare il nome utente e la password quando vengono inviati dal client al servizio.

Nel client è necessario richiedere all'utente il nome utente e la password e specificare le credenziali dell'utente nel proxy client WCF.

## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>Per configurare un servizio WCF per l'autenticazione tramite nome utente e password di dominio Windows

1. Creare un'istanza dell'oggetto <xref:System.ServiceModel.WSHttpBinding>, impostare la modalità di sicurezza dell'associazione su <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, impostare l'oggetto `ClientCredentialType` dell'associazione su <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> e aggiungere un endpoint del servizio utilizzando l'associazione configurata all'host del servizio come illustrato nel codice seguente:

    ```csharp
    // ...
    var userNameBinding = new WSHttpBinding();
    userNameBinding.Security.Mode = SecurityMode.Message;
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");
    // ...
    ```

2. Specificare il certificato del server utilizzato per crittografare le informazioni relative al nome utente e alla password inviate tramite la rete. Questo codice deve seguire immediatamente il codice illustrato sopra. Nell'esempio seguente viene utilizzato il certificato creato dal file di setup.bat dall'esempio [relativo al nome utente](../samples/message-security-user-name.md) per la sicurezza dei messaggi:

    ```csharp
    // ...
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");
    // ...
    ```

    È possibile utilizzare il proprio certificato; è sufficiente modificare il codice in modo che faccia riferimento a tale certificato. Per ulteriori informazioni sulla creazione e sull'utilizzo di certificati, vedere [Working with Certificates](working-with-certificates.md). Assicurarsi che il certificato si trovi nell'archivio certificati Persone attendibili del computer locale. Per eseguire questa operazione, è possibile eseguire mmc.exe e selezionare la voce di menu **file**, **Aggiungi/Rimuovi snap-in** . Nella finestra di dialogo **Aggiungi o Rimuovi snap-** in selezionare lo **snap-in certificati** e fare clic su **Aggiungi**. Nella finestra di dialogo snap-in certificati selezionare **account computer**. Per impostazione predefinita, il certificato generato nell'esempio di sicurezza dei messaggi tramite nome utente sarà posizionato nella cartella Personale/Certificati,  Verrà elencato come "localhost" nella colonna rilasciato a nella finestra MMC. Trascinare e rilasciare il certificato nella cartella **persone attendibili** . In questo modo il certificato verrà considerato come attendibile da WCF quando viene effettuata l'autenticazione.

## <a name="to-call-the-service-passing-username-and-password"></a>Per chiamare il servizio passando nome utente e password

1. L'applicazione client deve richiedere all'utente il nome utente e la password. Il codice seguente chiede all'utente il nome utente e la password:

    > [!WARNING]
    > Questo codice non deve essere utilizzato in produzione poiché la password viene visualizzata durante l'immissione.

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

2. Creare un'istanza del proxy client specificando le credenziali del client, come illustrato nel codice seguente:

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

## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [Protezione del trasporto con l'autenticazione di base](transport-security-with-basic-authentication.md)
- [Protezione delle applicazioni distribuite](distributed-application-security.md)
- [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)
