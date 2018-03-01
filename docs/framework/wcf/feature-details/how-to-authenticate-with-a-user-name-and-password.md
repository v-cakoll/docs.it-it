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
# <a name="how-to-authenticate-with-a-user-name-and-password"></a>Procedura: autenticare con un nome utente e una password
In questo argomento viene illustrato come abilitare l'autenticazione di un client con un nome utente e una password di dominio Windows in un servizio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Si presuppone che l'utente disponga di un servizio WCF self-hosted funzionante. Per un esempio di creazione di base vedere servizio WCF self-hosted, [esercitazione introduttiva](../../../../docs/framework/wcf/getting-started-tutorial.md). In questo argomento si presuppone che il servizio sia configurato tramite codice. Se si desidera vedere un esempio di configurazione di un servizio simile utilizzando un file di configurazione vedere [nome utente di sicurezza messaggio](../../../../docs/framework/wcf/samples/message-security-user-name.md)  
  
 Per configurare un servizio per l'autenticazione dei client mediante l'utilizzo di nomi utente e password di dominio Windows di <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> e impostare il relativo `Security.Mode` proprietà `Message`. Inoltre, è necessario specificare un certificato X509 che verrà utilizzato per crittografare il nome utente e la password quando vengono inviati dal client al servizio.  
  
 Nel client è necessario richiedere all'utente il nome utente e la password e specificare le credenziali dell'utente nel proxy client WCF.  
  
### <a name="to-configure-a-wcf-service-to-authenticate-using-windows-domain-username-and-password"></a>Per configurare un servizio WCF per l'autenticazione tramite nome utente e password di dominio Windows  
  
1.  Creare un'istanza del <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>, impostare la modalità di sicurezza dell'associazione `SecurityMode.Message`, impostare il `ClientCredentialType` dell'associazione `MessageCredentialType.UserName`e aggiungere un endpoint del servizio utilizzando l'associazione configurata all'host del servizio, come illustrato nel codice seguente:  
  
    ```  
    // ...  
    WSHttpBinding userNameBinding = new WSHttpBinding();  
    userNameBinding.Security.Mode = SecurityMode.Message;  
    userNameBinding.Security.Message.ClientCredentialType = MessageCredentialType.UserName;  
    svcHost.AddServiceEndpoint(typeof(IService1), userNameBinding, "");  
    // ...  
    ```  
  
2.  Specificare il certificato del server utilizzato per crittografare le informazioni relative al nome utente e alla password inviate tramite la rete. Questo codice deve seguire immediatamente il codice illustrato sopra. L'esempio seguente usa il certificato viene creato per il file setup.bat dal [nome utente di sicurezza messaggio](../../../../docs/framework/wcf/samples/message-security-user-name.md) esempio:  
  
    ```  
    // ...  
    svcHost.Credentials.ServiceCertificate.SetCertificate(StoreLocation.LocalMachine, StoreName.My, X509FindType.FindBySubjectName, "localhost");  
    // ...  
    ```  
  
     È possibile utilizzare il proprio certificato; è sufficiente modificare il codice in modo che faccia riferimento a tale certificato. Per ulteriori informazioni sulla creazione e utilizzo di certificati vedere [utilizzo dei certificati](../../../../docs/framework/wcf/feature-details/working-with-certificates.md). Assicurarsi che il certificato si trovi nell'archivio certificati Persone attendibili del computer locale. È possibile farlo eseguendo mmc.exe e scegliendo il **File**, **Aggiungi/Rimuovi Snap-in...**  voce di menu. Nel **Aggiungi o Rimuovi Snap-in** finestra di dialogo Seleziona il **snap-in certificati** e fare clic su **Aggiungi**. Nella finestra di dialogo Snap-in certificati selezionare **account Computer**. Per impostazione predefinita, il certificato generato nell'esempio di sicurezza dei messaggi tramite nome utente sarà posizionato nella cartella Personale/Certificati,  Sarà elencato come "localhost" con la colonna rilasciato a della finestra di MMC. Trascinare e rilasciare il certificato di **persone attendibili** cartella. In questo modo il certificato verrà considerato come attendibile da WCF quando viene effettuata l'autenticazione.  
  
### <a name="to-call-the-service-passing-username-and-password"></a>Per chiamare il servizio passando nome utente e password  
  
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
 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.SecurityMode>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.UserName%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential.Password%2A>  
 <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>  
 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A>  
 <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A>  
 [Sicurezza del trasporto con autenticazione di base](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 [Sicurezza delle applicazioni distribuite](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [\<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
