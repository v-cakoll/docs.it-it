---
title: 'Procedura: Rappresentare un client in un servizio'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
ms.openlocfilehash: 3dd40efe27687b048984c4592db0d3787d061eeb
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402327"
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>Procedura: Rappresentare un client in un servizio
Rappresentazione di un client in un servizio Windows Communication Foundation (WCF) consente al servizio eseguire azioni per conto del client. Per le azioni soggette ai controlli dell'elenco di controllo di accesso (ACL), ad esempio l'accesso a directory e file in un computer o l'accesso a un database SQL Server, il controllo ACL si basa sull'account utente del client. In questo argomento vengono illustrati i passaggi di base necessari che consentono a un client in un dominio Windows di impostare un livello di rappresentazione di client. Per un esempio pratico, vedere [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md). Per altre informazioni sulla rappresentazione di client, vedere [delega e rappresentazione](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
>  Quando il client e il servizio sono in esecuzione nello stesso computer e il client è in esecuzione con un account del sistema (ad esempio `Local System` o `Network Service`), il client non può essere rappresentato quando viene stabilita una sessione protetta con token del contesto di sicurezza con stato. Un'applicazione Windows Form o console viene in genere eseguita con l'account attualmente connesso che quindi può essere rappresentato per impostazione predefinita. Tuttavia, quando il client è una pagina ASP.NET e tale pagina è ospitata in IIS 6.0 o IIS 7.0, quindi il client viene eseguito con il `Network Service` account per impostazione predefinita. Tutte le associazioni fornite dal sistema che supportano le sessioni protette utilizzano un token del contesto di sicurezza senza stato per impostazione predefinita. Tuttavia, se il client è una pagina ASP.NET e vengono utilizzate sessioni protette con token del contesto di sicurezza con stato, il client non può essere rappresentato. Per altre informazioni sull'uso di token del contesto di sicurezza con stato in una sessione protetta, vedere [come: Creare un contesto di sicurezza Token per una sessione protetta](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>Per consentire la rappresentazione di un client da un token di Windows memorizzato nella cache in un servizio  
  
1. Creare il servizio. Per un'esercitazione su questa procedura di base, vedere [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
2. Utilizzare un'associazione che utilizza l'autenticazione di Windows e che crea una sessione, ad esempio <xref:System.ServiceModel.NetTcpBinding> o <xref:System.ServiceModel.WSHttpBinding>.  
  
3. Quando si crea l'implementazione dell'interfaccia del servizio, applicare la classe <xref:System.ServiceModel.OperationBehaviorAttribute> al metodo che richiede la rappresentazione del client. Impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> su <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>Per impostare il livello di rappresentazione consentito nel client  
  
1. Creare un codice client del servizio tramite [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Per altre informazioni, vedere [accesso ai servizi tramite Client WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2. Dopo aver creato il client di WCF, impostare il <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> proprietà del <xref:System.ServiceModel.Security.WindowsClientCredential> classe a una del <xref:System.Security.Principal.TokenImpersonationLevel> valori di enumerazione.  
  
    > [!NOTE]
    >  Per usare <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, deve essere usata l'autenticazione Kerberos negoziata, a volte denominata *multifase* o *in più passaggi* . Per una descrizione di come implementarla, vedere [procedure consigliate per la sicurezza](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.OperationBehaviorAttribute>
- <xref:System.Security.Principal.TokenImpersonationLevel>
- [Rappresentazione del client](../../../docs/framework/wcf/samples/impersonating-the-client.md)
- [Delega e rappresentazione](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
