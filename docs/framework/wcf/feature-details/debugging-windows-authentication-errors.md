---
title: Debug degli errori di autenticazione di Windows
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
- WCF, authentication
- WCF, Windows authentication
ms.assetid: 181be4bd-79b1-4a66-aee2-931887a6d7cc
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8c153fc3fa44b6f84d5aa11a7f20dcce3df533c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="debugging-windows-authentication-errors"></a>Debug degli errori di autenticazione di Windows
Quando si utilizza l'autenticazione di Windows come meccanismo di sicurezza, i processi di sicurezza vengono gestiti dall'interfaccia SSPI (Security Support Provider Interface). Se si verificano errori di sicurezza a livello SSPI, questi vengono riportati da [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. In questo argomento viene fornito un framework e un insieme di domande per facilitare la diagnosi degli errori.  
  
 Per una panoramica del protocollo Kerberos, vedere [Kerberos illustrati](http://go.microsoft.com/fwlink/?LinkID=86946); per una panoramica dell'interfaccia SSPI, vedere [SSPI](http://go.microsoft.com/fwlink/?LinkId=88941).  
  
 Per l'autenticazione di Windows, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza in genere il *Negotiate* Security Support Provider (SSP), che esegue l'autenticazione reciproca Kerberos tra il client e servizio. Se il protocollo Kerberos non è disponibile, per impostazione predefinita [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] esegue il fallback al protocollo NTLM (NT LAN Manager). È tuttavia possibile configurare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per utilizzare solo il protocollo Kerberos e viene generata un'eccezione se Kerberos non è disponibile. È inoltre possibile configurare [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] per utilizzare formati con restrizioni del protocollo Kerberos.  
  
## <a name="debugging-methodology"></a>Metodologia di debug  
 Il metodo di base è il seguente:  
  
1.  Determinare se si sta utilizzando l'autenticazione di Windows. Se si sta utilizzando qualsiasi altro schema, questo argomento non è applicabile.  
  
2.  Se si sta utilizzando con certezza l'autenticazione di Windows, determinare se la configurazione [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizza Kerberos direttamente o Negotiate.  
  
3.  Una volta determinato se la configurazione utilizza il protocollo Kerberos o NTLM, è possibile comprendere i messaggi di errore nel contesto giusto.  
  
### <a name="availability-of-the-kerberos-protocol-and-ntlm"></a>Disponibilità del protocollo Kerberos e NTLM  
 Per l'SSP Kerberos è necessario un controller di dominio che agisca da Centro di distribuzione chiave Kerberos (KDC, Kerberos Key Distribution Center). Il protocollo Kerberos è disponibile solo quando sia il client che il servizio utilizzano identità di dominio. In altre combinazioni di account, viene utilizzato il protocollo NTLM, come riepilogato nella tabella seguente.  
  
 Nelle intestazioni della tabella vengono riportati i possibili tipi di account utilizzati dal server, mentre nella colonna sinistra vengono indicati i possibili tipi di account utilizzati dal client.  
  
||Utente locale|Sistema locale|Utente del dominio|Computer del dominio|  
|-|----------------|------------------|-----------------|--------------------|  
|Utente locale|NTLM|NTLM|NTLM|NTLM|  
|Sistema locale|NTLM anonimo|NTLM anonimo|NTLM anonimo|NTLM anonimo|  
|Utente del dominio|NTLM|NTLM|Kerberos|Kerberos|  
|Computer del dominio|NTLM|NTLM|Kerberos|Kerberos|  
  
 In particolare, i quattro tipi di account includono:  
  
-   Utente locale: profilo utente del computer. Ad esempio: `MachineName\Administrator` o `MachineName\ProfileName`.  
  
-   Sistema locale: account predefinito SYSTEM in un computer non associato a un dominio.  
  
-   Utente del dominio: account utente in un dominio Windows. Ad esempio: `DomainName\ProfileName`.  
  
-   Computer del dominio: processo con identità di computer in esecuzione in un computer associato a un dominio Windows. Ad esempio: `MachineName\Network Service`.  
  
> [!NOTE]
>  La credenziale del servizio viene acquisita quando viene chiamato il metodo <xref:System.ServiceModel.ICommunicationObject.Open%2A> della classe <xref:System.ServiceModel.ServiceHost>. La credenziale del client viene letta ogni volta che il client invia un messaggio.  
  
## <a name="common-windows-authentication-problems"></a>Problemi di autenticazione di Windows comuni  
 Contenuto della sezione vengono illustrati alcuni problemi di autenticazione di Windows comuni e le possibili soluzioni.  
  
### <a name="kerberos-protocol"></a>Protocollo Kerberos  
  
#### <a name="spnupn-problems-with-the-kerberos-protocol"></a>Problemi SPN/UPN con il protocollo Kerberos  
 Quando si utilizza l'autenticazione di Windows unitamente al protocollo Kerberos diretto o negoziato mediante SSPI, l'URL utilizzato dall'endpoint client deve includere il nome di dominio completo dell'host del servizio presente nell'URL del servizio. Si presuppone che l'account con cui viene eseguito il servizio disponga dell'accesso alla chiave del computer (impostazione predefinita) servizio il nome dell'entità (SPN) che viene creata quando il computer viene aggiunto al dominio Active Directory, che viene eseguito più di frequente dall'esecuzione del servizio tramite il Account del servizio di rete. Se il servizio non ha accesso alla chiave dell'SPN del computer, è necessario fornire l'SPN corretto o il nome dell'entità utente (UPN) dell'account utilizzato per l'esecuzione del servizio nell'identità dell'endpoint del client. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]come [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SPN e UPN, vedere [autenticazione e identità del servizio](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 In scenari di bilanciamento del carico, ad esempio Web farm o Web garden, viene comunemente definito un account univoco per ogni applicazione, viene assegnato un SPN a tale account e viene verificato che tutti i servizi dell'applicazione siano eseguiti in tale account.  
  
 Per ottenere un SPN per l'account del servizio, è necessario essere amministratore di dominio di Active Directory. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Supplemento tecnico Kerberos per Windows](http://go.microsoft.com/fwlink/?LinkID=88330).  
  
#### <a name="kerberos-protocol-direct-requires-the-service-to-run-under-a-domain-machine-account"></a>Per il protocollo Kerberos diretto è necessario che il servizio venga eseguito utilizzando un account di tipo computer del dominio  
 Questo si verifica quando la proprietà `ClientCredentialType` è impostata su `Windows` e la proprietà <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> è impostata su `false`, come illustrato nel codice seguente.  
  
 [!code-csharp[C_DebuggingWindowsAuth#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#1)]
 [!code-vb[C_DebuggingWindowsAuth#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#1)]  
  
 Per risolvere questo problema, eseguire il servizio utilizzando un account di tipo computer del dominio, ad esempio Servizio di rete, in un computer associato al dominio.  
  
### <a name="delegation-requires-credential-negotiation"></a>Requisito di negoziazione della credenziale in caso di delega  
 Per poter essere utilizzato con la funzionalità di delega, il protocollo di autenticazione Kerberos deve essere implementato con la negoziazione della credenziale. Questa versione di Kerberos è nota come Kerberos multifase o multipassaggio. Se si implementa l'autenticazione Kerberos senza negoziazione della credenziale (ovvero una versione di Kerberos anche nota come "monofase" o "monopassaggio), verrà generata un'eccezione.  
  
 Per implementare Kerberos con negoziazione della credenziale, eseguire le operazioni seguenti:  
  
1.  Implementare la delega impostando <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> su <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>.  
  
2.  Richiedere la negoziazione SSPI:  
  
    1.  Se si utilizzano associazioni standard, impostare la proprietà `NegotiateServiceCredential` su `true`.  
  
    2.  Se si utilizzano associazioni personalizzate, impostare l'attributo `AuthenticationMode` dell'elemento `Security` su `SspiNegotiated`.  
  
3.  Richiedere che la negoziazione SSPI utilizzi Kerberos impedendo l'utilizzo di NTLM:  
  
    1.  È possibile eseguire questa operazione nel codice utilizzando l'istruzione seguente: `ChannelFactory.Credentials.Windows.AllowNtlm = false`  
  
    2.  In alternativa, è possibile operare nel file di configurazione impostando l'attributo `allowNtlm` su `false`. Questo attributo è contenuto nella [ \<windows >](../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md).  
  
### <a name="ntlm-protocol"></a>Protocollo NTLM  
  
#### <a name="negotiate-ssp-falls-back-to-ntlm-but-ntlm-is-disabled"></a>Il provider SSP Negotiate esegue il fallback a NTLM, ma NTLM è disabilitato  
 Poiché la proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowNtlm%2A> è impostata su `false`, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] tenta di generare un'eccezione se viene utilizzato NTLM. Si noti che l'impostazione di questa proprietà su `false` potrebbe non impedire l'invio di credenziali NTLM nella rete.  
  
 Nel codice seguente viene illustrato come disabilitare il fallback a NTLM.  
  
 [!code-csharp[C_DebuggingWindowsAuth#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#4)]
 [!code-vb[C_DebuggingWindowsAuth#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#4)]  
  
#### <a name="ntlm-logon-fails"></a>Impossibile accedere a NTLM  
 Le credenziali client non sono valide per il servizio. Verificare che il nome utente e la password siano impostati correttamente e che corrispondano a un account noto al computer in cui viene eseguito il servizio. Per accedere al computer del servizio, NTLM utilizza le credenziali specificate. Anche se le credenziali possono essere valide nel computer in cui il client è in esecuzione, l'accesso non riuscirà se le credenziali non sono valide nel computer del servizio.  
  
#### <a name="anonymous-ntlm-logon-occurs-but-anonymous-logons-are-disabled-by-default"></a>Si verifica un accesso NTLM anonimo, ma gli accessi anonimi sono disabilitati per impostazione predefinita  
 Quando si crea un client, la proprietà <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> viene impostata su <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, come illustrato nell'esempio seguente, ma per impostazione predefinita il server impedisce gli accessi anonimi. Tale situazione si verifica perché il valore predefinito della proprietà <xref:System.ServiceModel.Security.WindowsServiceCredential.AllowAnonymousLogons%2A> della classe <xref:System.ServiceModel.Security.WindowsServiceCredential> è `false`.  
  
 Nel codice client seguente viene tentata l'abilitazione degli accessi anonimi (si noti che la proprietà predefinita è `Identification`).  
  
 [!code-csharp[C_DebuggingWindowsAuth#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#5)]
 [!code-vb[C_DebuggingWindowsAuth#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#5)]  
  
 Nel codice del servizio seguente viene modificata l'impostazione predefinita per consentire gli accessi anonimi.  
  
 [!code-csharp[C_DebuggingWindowsAuth#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#6)]
 [!code-vb[C_DebuggingWindowsAuth#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#6)]  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]la rappresentazione, vedere [delega e rappresentazione](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md).  
  
 In alternativa, il client viene eseguito come un servizio Windows, utilizzando l'account predefinito System.  
  
### <a name="other-problems"></a>Altri problemi  
  
#### <a name="client-credentials-are-not-set-correctly"></a>Le credenziali client non sono impostate correttamente  
 L'autenticazione di Windows utilizza l'istanza <xref:System.ServiceModel.Security.WindowsClientCredential> restituita dalla proprietà <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> della classe <xref:System.ServiceModel.ClientBase%601>, non l'istanza <xref:System.ServiceModel.Security.UserNamePasswordClientCredential>. Nel codice seguente viene illustrato un esempio non corretto.  
  
 [!code-csharp[C_DebuggingWindowsAuth#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#2)]
 [!code-vb[C_DebuggingWindowsAuth#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#2)]  
  
 Nel codice seguente viene illustrato l'esempio corretto.  
  
 [!code-csharp[C_DebuggingWindowsAuth#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_debuggingwindowsauth/cs/source.cs#3)]
 [!code-vb[C_DebuggingWindowsAuth#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_debuggingwindowsauth/vb/source.vb#3)]  
  
#### <a name="sspi-is-not-available"></a>L'interfaccia SSPI non è disponibile  
 I sistemi operativi seguenti non supportano l'autenticazione di Windows quando viene utilizzato come un server: [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Home Edition, [!INCLUDE[wxp](../../../../includes/wxp-md.md)] Media Center Edition e [!INCLUDE[wv](../../../../includes/wv-md.md)]Home Edition.  
  
#### <a name="developing-and-deploying-with-different-identities"></a>Sviluppo e distribuzione con identità diverse  
 Se l'applicazione viene sviluppata in un computer e distribuita in un altro e si utilizzano diversi tipi di account per l'autenticazione in ogni computer, potrebbe verificarsi un comportamento diverso. Si supponga, ad esempio, di sviluppare l'applicazione in un computer Windows XP Pro utilizzando la modalità di autenticazione `SSPI Negotiated`. Se si utilizza un account utente locale per l'autenticazione, verrà utilizzato il protocollo NTLM. Una volta sviluppata l'applicazione, il servizio viene distribuito in un computer Windows Server 2003 in cui è in esecuzione un account di dominio. A questo punto il client non è in grado di autenticare il servizio poiché utilizza Kerberos e un controller di dominio.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>  
 <xref:System.ServiceModel.Security.WindowsClientCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 [Delega e rappresentazione](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 [Scenari non supportati](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)
