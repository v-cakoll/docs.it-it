---
title: 'Procedura: rappresentare un client in un servizio'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, impersonation
- impersonation
- WCF, security
ms.assetid: 431db851-a75b-4009-9fe2-247243d810d3
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de7bfb7d926f9aa75ccfcfe8a550a0dbae4e12ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-impersonate-a-client-on-a-service"></a>Procedura: rappresentare un client in un servizio
La rappresentazione di un client in un servizio [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] consente a quest'ultimo di eseguire azioni per conto del client. Per le azioni soggette ai controlli dell'elenco di controllo di accesso (ACL), ad esempio l'accesso a directory e file in un computer o l'accesso a un database SQL Server, il controllo ACL si basa sull'account utente del client. In questo argomento vengono illustrati i passaggi di base necessari che consentono a un client in un dominio Windows di impostare un livello di rappresentazione di client. Per un esempio pratico, vedere [Impersonating the Client](../../../docs/framework/wcf/samples/impersonating-the-client.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]la rappresentazione del client, vedere [delega e rappresentazione](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
> [!NOTE]
>  Quando il client e il servizio sono in esecuzione nello stesso computer e il client è in esecuzione con un account del sistema (ad esempio `Local System` o `Network Service`), il client non può essere rappresentato quando viene stabilita una sessione protetta con token del contesto di sicurezza con stato. Un'applicazione Windows Form o console viene in genere eseguita con l'account attualmente connesso che quindi può essere rappresentato per impostazione predefinita. Tuttavia, quando il client è una pagina [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] ospitata in [!INCLUDE[iis601](../../../includes/iis601-md.md)] o IIS 7.0, il client viene eseguito con l'account `Network Service` per impostazione predefinita. Tutte le associazioni fornite dal sistema che supportano le sessioni protette utilizzano un token del contesto di sicurezza senza stato per impostazione predefinita. Tuttavia, se il client è una pagina [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] e si utilizzano sessioni protette con token del contesto di sicurezza con stato, non è possibile eseguire la rappresentazione del client. [!INCLUDE[crabout](../../../includes/crabout-md.md)]uso di token di contesto di sicurezza con stato in una sessione protetta, vedere [procedura: creare un Token di contesto di sicurezza per una sessione protetta](../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-enable-impersonation-of-a-client-from-a-cached-windows-token-on-a-service"></a>Per consentire la rappresentazione di un client da un token di Windows memorizzato nella cache in un servizio  
  
1.  Creare il servizio. Per un'esercitazione su questa procedura di base, vedere [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
2.  Utilizzare un'associazione che utilizza l'autenticazione di Windows e che crea una sessione, ad esempio <xref:System.ServiceModel.NetTcpBinding> o <xref:System.ServiceModel.WSHttpBinding>.  
  
3.  Quando si crea l'implementazione dell'interfaccia del servizio, applicare la classe <xref:System.ServiceModel.OperationBehaviorAttribute> al metodo che richiede la rappresentazione del client. Impostare la proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> su <xref:System.ServiceModel.ImpersonationOption.Required>.  
  
     [!code-csharp[c_SimpleImpersonation#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#2)]
     [!code-vb[c_SimpleImpersonation#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#2)]  
  
### <a name="to-set-the-allowed-impersonation-level-on-the-client"></a>Per impostare il livello di rappresentazione consentito nel client  
  
1.  Creare un codice client del servizio tramite [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][L'accesso ai servizi tramite Client WCF](../../../docs/framework/wcf/accessing-services-using-a-wcf-client.md).  
  
2.  Dopo la creazione del client [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] , impostare la proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> della classe <xref:System.ServiceModel.Security.WindowsClientCredential> su uno dei valori di enumerazione di <xref:System.Security.Principal.TokenImpersonationLevel> .  
  
    > [!NOTE]
    >  Per usare <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>, deve essere usata l'autenticazione Kerberos negoziata, a volte denominata *multifase* o *in più passaggi* . Per una descrizione di come implementare questo, vedere [le procedure consigliate per la sicurezza](../../../docs/framework/wcf/feature-details/best-practices-for-security-in-wcf.md).  
  
     [!code-csharp[c_SimpleImpersonation#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_simpleimpersonation/cs/source.cs#1)]
     [!code-vb[c_SimpleImpersonation#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_simpleimpersonation/vb/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.OperationBehaviorAttribute>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 [Rappresentazione del Client](../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 [Delega e rappresentazione](../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)
