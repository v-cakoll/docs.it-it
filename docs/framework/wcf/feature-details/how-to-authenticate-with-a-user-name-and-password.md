---
title: "Procedura: Eseguire l'autenticazione con un nome utente e Password"
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF], user name and password
ms.assetid: a5415be2-0ef3-464c-9f76-c255cb8165a4
ms.openlocfilehash: f6939659249ea40e97f340771017d0587ec6a08f
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412266"
---
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Procedura: Eseguire l'autenticazione con un nome utente e Password

In questo argomento viene illustrato come abilitare un servizio Windows Communication Foundation (WCF) autenticare un client con un nome utente di dominio di Windows e una password. Si presuppone che l'utente disponga di un servizio WCF self-hosted funzionante. Per un esempio di creazione di un base self-hosted WCF service, vedere [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md). In questo argomento si presuppone che il servizio sia configurato tramite codice. Se si vuole vedere un esempio di configurazione di un servizio simile tramite un file di configurazione vedere [sicurezza messaggi tramite nome utente](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 Per configurare un servizio in modo che effettui l'autenticazione dei client mediante il nome utente e la password di dominio Windows, utilizzare l'oggetto <xref:System.ServiceModel.WSHttpBinding> e impostare la relativa proprietà `Security.Mode` su `Message`. Inoltre, è necessario specificare un certificato X509 che verrà utilizzato per crittografare il nome utente e la password quando vengono inviati dal client al servizio.  
  
 Nel client è necessario richiedere all'utente il nome utente e la password e specificare le credenziali dell'utente nel proxy client WCF.  
  
## <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>Per configurare un servizio WCF per l'autenticazione tramite nome utente di dominio di Windows e password
  
1.  Creare un'istanza dell'oggetto <xref:System.ServiceModel.WSHttpBinding>, impostare la modalità di sicurezza dell'associazione su <xref:System.ServiceModel.WSHttpSecurity.Message?displayProperty=nameWithType>, impostare l'oggetto `ClientCredentialType` dell'associazione su <xref:System.ServiceModel.MessageCredentialType.UserName?displayProperty=nameWithType> e aggiungere un endpoint del servizio utilizzando l'associazione configurata all'host del servizio come illustrato nel codice seguente:  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Specificare il certificato del server utilizzato per crittografare le informazioni relative al nome utente e alla password inviate tramite la rete. Questo codice deve seguire immediatamente il codice illustrato sopra. L'esempio seguente usa il certificato creato dal file Setup. bat dal [messaggi tramite nome utente sicurezza](../../../../docs/framework/wcf/samples/message-security-user-name.md) esempio:  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     È possibile utilizzare il proprio certificato; è sufficiente modificare il codice in modo che faccia riferimento a tale certificato. Per altre informazioni sulla creazione e utilizzo dei certificati, vedere [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Assicurarsi che il certificato si trovi nell'archivio certificati Persone attendibili del computer locale. È possibile farlo eseguendo mmc.exe e scegliendo il **File**, **Aggiungi/Rimuovi Snap-in...**  voce di menu. Nel **Aggiungi o Rimuovi Snap-in** finestra di dialogo, seleziona la **snap-in certificati** e fare clic su **Add**. Nella finestra di dialogo Snap-in certificati selezionare **account del Computer**. Per impostazione predefinita, il certificato generato nell'esempio di sicurezza dei messaggi tramite nome utente sarà posizionato nella cartella Personale/Certificati,  Verrà elencata come "localhost" sotto la colonna rilasciato a nella finestra di MMC. Trascinare e rilasciare il certificato nel **persone attendibili** cartella. In questo modo il certificato verrà considerato come attendibile da WCF quando viene effettuata l'autenticazione.  
  
## <a name="to-call-the-service-passing-username-and-password"></a>Per chiamare il servizio passando nome utente e password  
  
1.  L'applicazione client deve richiedere all'utente il nome utente e la password. Il codice seguente richiede all'utente il nome utente e la password.  
  
    > [!WARNING]
    >  Questo codice non deve essere utilizzato in produzione poiché la password viene visualizzata durante l'immissione.  
  
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
  
2.  Creare un'istanza del proxy client specificando le credenziali del client come illustrato nel codice seguente:  
  
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
  
## <a name="see-also"></a>Vedere anche
- <xref:System.ServiceModel.WSHttpBinding>
- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.SecurityMode>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>
- <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>
- <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>
- [Sicurezza del trasporto con autenticazione di base](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)
- [Sicurezza delle applicazioni distribuite](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
