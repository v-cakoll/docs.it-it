---
title: Utilizzo della rappresentazione con la sicurezza del trasporto
ms.date: 03/30/2017
ms.assetid: 426df8cb-6337-4262-b2c0-b96c2edf21a9
ms.openlocfilehash: 1d33bfbbb74266aefa538166b4e1aca7d7e315ef
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594972"
---
# <a name="using-impersonation-with-transport-security"></a>Utilizzo della rappresentazione con la sicurezza del trasporto
La *rappresentazione* è la capacità di un'applicazione server di assumere l'identità del client. In genere i servizi utilizzano la rappresentazione al momento della convalida dell'accesso alle risorse. L'applicazione server è in esecuzione tramite un account del servizio ma quando il server accetta una connessione client, rappresenta il client. In questo modo i controlli di accesso vengono eseguiti utilizzando le credenziali client. La protezione del trasporto è un meccanismo utilizzato sia per il passaggio delle credenziali che per la protezione della comunicazione tramite quelle credenziali. In questo argomento viene descritto l'utilizzo della sicurezza del trasporto in Windows Communication Foundation (WCF) con la funzionalità di rappresentazione. Per ulteriori informazioni sulla rappresentazione tramite la sicurezza dei messaggi, vedere [delega e rappresentazione](delegation-and-impersonation-with-wcf.md).  
  
## <a name="five-impersonation-levels"></a>Cinque livelli di rappresentazione  
 La protezione del trasporto si avvale di cinque livelli di rappresentazione, come descritto nella tabella seguente.  
  
|Livello di rappresentazione|Descrizione|  
|-------------------------|-----------------|  
|nessuno|L'applicazione server non tenta di rappresentare il client.|  
|Anonima|L'applicazione server è in grado di eseguire controlli di accesso a fronte delle credenziali client, ma non riceve alcuna informazione sull'identità del client. Questo livello di rappresentazione è significativo solo per comunicazioni su computer, ad esempio le named pipe. L'utilizzo di `Anonymous` con una connessione remota innalza il livello di rappresentazione a Identify.|  
|Identify|L'applicazione conosce l'identità del client ed è in grado di eseguire la convalida dell'accesso a fronte delle credenziali client, ma non è in grado di rappresentare il client. Identificare è il livello di rappresentazione predefinito utilizzato con le credenziali SSPI in WCF, a meno che il provider di token non fornisca un livello di rappresentazione diverso.|  
|Impersonate|Oltre a eseguire controlli di accesso, l'applicazione server è in grado di accedere alle risorse nel server come client. L'applicazione server non è in grado di accedere alle risorse su computer remoti tramite l'identità del client poiché il token rappresentato non dispone di credenziali di rete.|  
|Delegato|Oltre ad avere le stesse funzionalità di `Impersonate`, il livello di rappresentazione Delegate consente all'applicazione server l'accesso a risorse in computer remoti utilizzando l'identità del client e il passaggio dell'identità ad altre applicazioni.<br /><br /> **Importante** Per utilizzare queste funzionalità aggiuntive, è necessario che l'account di dominio del server sia contrassegnato come trusted per la delega del controller di dominio. È impossibile utilizzare questo livello di rappresentazione con account di dominio client contrassegnati come riservati.|  
  
 I livelli utilizzati più di frequente con la sicurezza del trasporto sono `Identify` e `Impersonate` . I livelli `None` e `Anonymous` non sono consigliati per un utilizzo tipico. Molti trasporti inoltre non supportano l'utilizzo di tali livelli con l'autenticazione. Il livello `Delegate` è una funzionalità potente che deve essere utilizzata con cautela. Solo ad applicazioni server attendibili deve essere fornita l'autorizzazione per delegare credenziali.  
  
 L'utilizzo della rappresentazione ai livelli `Impersonate` o `Delegate` richiede che l'applicazione server disponga del privilegio `SeImpersonatePrivilege`. Un'applicazione dispone di questo privilegio per impostazione predefinita se è in esecuzione in un account nel gruppo Administrators o in un account con un SID del servizio (Servizio di rete, Servizio locale o Sistema locale). La rappresentazione non richiede autenticazione reciproca tra client e server. È impossibile utilizzare alcuni schemi di autenticazione che supportano la rappresentazione, ad esempio NTLM, con l'autenticazione reciproca.  
  
## <a name="transport-specific-issues-with-impersonation"></a>Problemi specifici del trasporto con la rappresentazione  
 La scelta di un trasporto in WCF influiscono sulle possibili scelte per la rappresentazione. In questa sezione vengono descritti i problemi che interessano i trasporti standard HTTP e named pipe in WCF. I trasporti personalizzati presentano restrizioni relative al supporto per la rappresentazione.  
  
### <a name="named-pipe-transport"></a>Trasporto di named pipe  
 Gli elementi seguenti vengono utilizzati con il trasporto di named pipe:  
  
- Il trasporto di named pipe è concepito per l'utilizzo solo nel computer locale. Il trasporto named pipe in WCF non consente in modo esplicito connessioni tra computer.  
  
- Non è possibile utilizzare le named pipe con livelli di rappresentazione `Impersonate` o `Delegate`. La named pipe non è in grado di imporre la garanzia su computer con questi livelli di rappresentazione.  
  
 Per ulteriori informazioni sulle named pipe, vedere [scelta di un trasporto](choosing-a-transport.md).  
  
### <a name="http-transport"></a>Trasporto HTTP  
 Le associazioni che utilizzano il trasporto HTTP ( <xref:System.ServiceModel.WSHttpBinding> e <xref:System.ServiceModel.BasicHttpBinding> ) supportano diversi schemi di autenticazione, come illustrato in [informazioni sull'autenticazione HTTP](understanding-http-authentication.md). Il livello di rappresentazione supportato dipende dallo schema di autenticazione. Gli elementi seguenti vengono utilizzati con il trasporto HTTP:  
  
- Lo schema di autenticazione `Anonymous` ignora la rappresentazione.  
  
- Lo `Basic` schema di autenticazione supporta solo il `Delegate` livello. Tutti i livelli di rappresentazione inferiori vengono aggiornati.  
  
- Lo schema di autenticazione `Digest` supporta solo i livelli `Impersonate` e `Delegate`.  
  
- Lo schema di autenticazione `NTLM`, selezionabile direttamente o tramite negoziazione, supporta solo il livello `Delegate` nel computer locale.  
  
- Lo schema di autenticazione Kerberos, selezionabile solo tramite negoziazione, può essere utilizzato con qualsiasi livello di rappresentazione supportato.  
  
 Per ulteriori informazioni sul trasporto HTTP, vedere [scelta di un trasporto](choosing-a-transport.md).  
  
## <a name="see-also"></a>Vedere anche

- [Delega e rappresentazione](delegation-and-impersonation-with-wcf.md)
- [Autorizzazione](authorization-in-wcf.md)
- [Procedura: Rappresentare un client in un servizio](../how-to-impersonate-a-client-on-a-service.md)
- [Informazioni sull'autenticazione HTTP](understanding-http-authentication.md)
