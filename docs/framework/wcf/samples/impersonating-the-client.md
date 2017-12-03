---
title: Rappresentazione di client
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 15f0b0427dcbf12f476470369945044815cb3269
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="impersonating-the-client"></a>Rappresentazione di client
L'esempio Rappresentazione di client mostra come rappresentare l'applicazione del chiamante al servizio così che il servizio possa accedere a risorse di sistema per conto del chiamante.  
  
 Questo esempio è basato sul [indipendente](../../../../docs/framework/wcf/samples/self-host.md) esempio. File di configurazione del servizio e client sono uguali a quelli del [indipendente](../../../../docs/framework/wcf/samples/self-host.md) esempio.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 Il codice del servizio è stato modificato in modo tale che il metodo `Add` nel servizio rappresenta il chiamante utilizzando <xref:System.ServiceModel.OperationBehaviorAttribute> come mostra il codice di esempio seguente.  
  
```  
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 Di conseguenza, il contesto di sicurezza del thread in esecuzione passa a rappresentare il chiamante prima di immettere il metodo `Add` ed essere ripristinato sul metodo esistente.  
  
 Il metodo `DisplayIdentityInformation` illustrato nel codice di esempio seguente è una funzione di utilità che visualizza l'identità del chiamante.  
  
```  
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",   
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 Il metodo `Subtract` nel servizio rappresenta il chiamante utilizzando chiamate imperative come mostra il codice di esempio seguente.  
  
```  
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
Console.WriteLine("Before impersonating");  
DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs   
            // on the system resource are enforced in the caller's context.   
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
Console.WriteLine("After reverting");  
DisplayIdentityInformation();  
    return result;  
}  
```  
  
 Notare che in questo caso che il chiamante non è rappresentato per la chiamata intera ma è rappresentato solo per una parte della chiamata. In generale, la rappresentazione di ambiti più piccoli, è preferibile alla rappresentazione dell'intera operazione.  
  
 Gli altri metodi non rappresentano il chiamante.  
  
 Il codice client è stato modificato per impostare il livello di rappresentazione su <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>. Il client specifica il livello di rappresentazione che il servizio deve utilizzare, utilizzando l'enumerazione <xref:System.Security.Principal.TokenImpersonationLevel>. L'enumerazione supporta i seguenti i seguenti valori: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> e <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. Per eseguire una verifica di accesso quando si accede a una risorsa di sistema sul computer locale protetto utilizzando Windows ACL, il livello di rappresentazione deve essere impostato su <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation>, come mostra il codice di esempio seguente.  
  
```  
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 Quando si esegue l'esempio, le richieste e le risposte dell'operazione vengono visualizzate nelle finestre della console client e del servizio. Premere INVIO in tutte le finestre della console per arrestare il servizio e il client.  
  
> [!NOTE]
>  Il servizio deve essere eseguito a partire da un account amministrativo o l'account sotto cui viene eseguito deve avere diritti per iscrivere l'URI http://localhost:8000/ServiceModelSamples con il livello HTTP. È possibile assegnare tali diritti configurando un [prenotazione Namespace](http://go.microsoft.com/fwlink/?LinkId=95012) utilizzando il [strumento Httpcfg.exe](http://go.microsoft.com/fwlink/?LinkId=95010).  
  
> [!NOTE]
>  In computer che eseguono [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], la rappresentazione è supportata solo se l'applicazione Host.exe ha il privilegio di rappresentazione. Per impostazione predefinita, solo gli amministratori dispongono di questa autorizzazione. Per aggiungere questo privilegio a un account è in esecuzione il servizio, passare a **strumenti di amministrazione**aprire **criteri di sicurezza locali**aprire **criteri locali**, fare clic su **Assegnazione diritti utente**e selezionare **rappresenta un Client dopo l'autenticazione** fare doppio clic su **proprietà** per aggiungere un utente o gruppo.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4.  Per dimostrare che il servizio rappresenta il chiamante, eseguire il client sotto un account diverso rispetto a quello sotto cui il servizio è in esecuzione. A tale scopo, al prompt dei comandi, digitare:  
  
    ```  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     Viene richiesta una password. Immettere la password per l'account precedentemente specificata.  
  
5.  Quando si esegue il client, notare l'identità prima e dopo aver eseguito credenziali diverse.  
  
## <a name="see-also"></a>Vedere anche
