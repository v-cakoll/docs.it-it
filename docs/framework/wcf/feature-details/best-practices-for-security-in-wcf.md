---
title: Procedure consigliate per la protezione in WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- best practices [WCF], security
ms.assetid: 3639de41-1fa7-4875-a1d7-f393e4c8bd69
ms.openlocfilehash: c99ab5e1e72aefc688df1692091e60caf930d5e4
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597618"
---
# <a name="best-practices-for-security-in-wcf"></a>Procedure consigliate per la protezione in WCF
Nelle sezioni seguenti vengono elencate le procedure consigliate da prendere in considerazione quando si creano applicazioni protette tramite Windows Communication Foundation (WCF). Per altre informazioni sulla sicurezza, vedere [Considerazioni sulla sicurezza](security-considerations-in-wcf.md), [Considerazioni sulla protezione per i dati](security-considerations-for-data.md) e [Considerazioni sulla sicurezza con metadati](security-considerations-with-metadata.md).  
  
## <a name="identify-services-performing-windows-authentication-with-spns"></a>Identificare i servizi che eseguono l'autenticazione di Windows con SPN  
 I servizi possono essere identificati con i nomi dell'entità utente (UPN) o i nomi dell'entità servizio (SPN). I servizi in esecuzione in account di computer, come un servizio di rete, dispongono di un'identità SPN che corrisponde al computer in cui sono in esecuzione. I servizi in esecuzione in account utente dispongono di un'identità UPN che corrisponde all'utente utilizzato per l'esecuzione, sebbene sia possibile utilizzare lo strumento `setspn` per assegnare un SPN all'account utente. La configurazione di un servizio in modo da poterlo identificare tramite SPN e la configurazione dei client che si connettono al servizio affinché utilizzino tale SPN possono rendere più difficili alcuni attacchi. Questo materiale sussidiario si applica alle associazioni che utilizzano Kerberos o la negoziazione SSPI.  I client devono comunque specificare un SPN nel caso in cui SSPI esegua il fallback a NTLM.  
  
## <a name="verify-service-identities-in-wsdl"></a>Verificare le identità di servizio in WSDL  
 WS-SecurityPolicy consente ai servizi di pubblicare informazioni sulle relative identità nei metadati. In caso di recupero tramite `svcutil` o altri metodi, ad esempio <xref:System.ServiceModel.Description.WsdlImporter>, le informazioni sull'identità vengono traslate nelle proprietà di identità degli indirizzi endpoint del servizio WCF. I client che non verificano la correttezza e la validità di queste identità di servizio ignorano in realtà l'autenticazione del servizio. Un servizio dannoso può sfruttare tali client per eseguire l'inoltro di credenziali e altri attacchi "man in the middle" modificando l'identità attestata in WSDL.  
  
## <a name="use-x509-certificates-instead-of-ntlm"></a>Utilizzare certificati X509 anziché NTLM  
 WCF offre due meccanismi per l'autenticazione peer-to-peer: i certificati X509 (usati dal canale peer) e l'autenticazione di Windows in cui una negoziazione SSPI effettua un downgrade da Kerberos a NTLM.  L'autenticazione basata sui certificati che utilizza dimensioni della chiave pari a 1024 bit o superiori è preferibile a NTLM per diversi motivi:  
  
- disponibilità di autenticazione reciproca  
  
- utilizzo di algoritmi crittografici più avanzati  
  
- maggiore difficoltà nell'utilizzo di credenziali X509 inoltrate.  

## <a name="always-revert-after-impersonation"></a>Eseguire sempre il ripristino dopo la rappresentazione  
 Quando si utilizzano API che consentono la rappresentazione di un client, assicurarsi di ripristinare sempre l'identità originale. Quando si usano, ad esempio, <xref:System.Security.Principal.WindowsIdentity> e <xref:System.Security.Principal.WindowsImpersonationContext>, usare l'istruzione C# `using` o l'istruzione Visual Basic `Using`, come illustrato nel codice seguente. La classe <xref:System.Security.Principal.WindowsImpersonationContext> implementa l'interfaccia <xref:System.IDisposable> e pertanto, il Common Language Runtime (CLR) torna automaticamente alla propria l'identità originale quando il codice lascia il blocco `using`.  
  
 [!code-csharp[c_SecurityBestPractices#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securitybestpractices/cs/source.cs#1)]
 [!code-vb[c_SecurityBestPractices#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securitybestpractices/vb/source.vb#1)]  
  
## <a name="impersonate-only-as-needed"></a>Eseguire la rappresentazione solo quando necessario  
 Utilizzando il metodo <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> della classe <xref:System.Security.Principal.WindowsIdentity> è possibile utilizzare la rappresentazione in un ambito molto controllato. Si tratta di una procedura opposta all'utilizzo della proprietà <xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A> di <xref:System.ServiceModel.OperationBehaviorAttribute> che consente la rappresentazione per l'ambito dell'intera operazione. Quando possibile, controllare sempre l'ambito della rappresentazione utilizzando il metodo <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A> più preciso.  
  
## <a name="obtain-metadata-from-trusted-sources"></a>Ottenere i metadati da fonti attendibili  
 Assicurarsi che l'origine dei metadati sia attendibile e che nessuno abbia manomesso i metadati. I metadati recuperati utilizzando il protocollo HTTP vengono inviati come testo non crittografato e possono essere alterati. Se il servizio utilizza le proprietà <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> e <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetUrl%2A>, utilizzare l'URL fornito dal creatore del servizio per scaricare i dati tramite il protocollo HTTPS.  
  
## <a name="publish-metadata-using-security"></a>Pubblicare i metadati tramite la protezione  
 Per impedire che i metadati pubblicati di un servizio vengano alterati, proteggere l'endpoint dello scambio di metadati con la sicurezza a livello di trasporto o di messaggio. Per altre informazioni, vedere [Pubblicazione di endpoint dei metadati](../publishing-metadata-endpoints.md) e [Procedura: Pubblicare metadati per un servizio usando codice](how-to-publish-metadata-for-a-service-using-code.md).  
  
## <a name="ensure-use-of-local-issuer"></a>Assicurarsi che venga utilizzato l'emittente locale  
 Se per una determinata associazione vengono specificati l'indirizzo dell'emittente e l'associazione, l'emittente locale non verrà utilizzato per gli endpoint che utilizzano tale associazione. Per i client che prevedono di utilizzare sempre l'emittente locale, è necessario accertarsi di non utilizzare tale associazione o di modificare l'associazione in modo che l'indirizzo dell'emittente sia null.  
  
## <a name="saml-token-size-quotas"></a>Quota delle dimensioni del token SAML  
 Quando i token SAML (Security Assertions Markup Language) vengono serializzati nei messaggi, quando sono rilasciati da un servizio token di sicurezza (STS, Security Token Service) o quando sono presentati dai client ai servizi nell'ambito dell'autenticazione, la quota della dimensione massima del messaggio deve essere sufficientemente grande da contenere il token SAML e le altre parti del messaggio. Normalmente la quota della dimensione predefinita del messaggio è sufficiente. Nei casi in cui un token SAML sia di grandi dimensioni perché contiene centinaia di attestazioni, è necessario aumentare le quote per contenere il token serializzato. Per altre informazioni sulle quote, vedere [Considerazioni sulla protezione per i dati](security-considerations-for-data.md).  
  
## <a name="set-securitybindingelementincludetimestamp-to-true-on-custom-bindings"></a>Impostare SecurityBindingElement.IncludeTimestamp su True nelle associazioni personalizzate  
 Quando si crea un'associazione personalizzata, è necessario impostare <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> su `true`. In caso contrario, se <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> viene impostato su `false` e il client utilizza un token basato su chiave asimmetrica quale un certificato X509, il messaggio non sarà firmato.  
  
## <a name="see-also"></a>Vedere anche

- [Security Considerations](security-considerations-in-wcf.md)
- [Considerazioni sulla sicurezza per i dati](security-considerations-for-data.md)
- [Considerazioni sulla sicurezza con metadati](security-considerations-with-metadata.md)
