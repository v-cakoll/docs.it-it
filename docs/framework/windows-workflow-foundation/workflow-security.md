---
title: Sicurezza del flusso di lavoro
ms.date: 03/30/2017
helpviewer_keywords:
- programming [WF], workflow security
ms.assetid: d712a566-f435-44c0-b8c0-49298e84b114
ms.openlocfilehash: 2a9b26f8da7616480f69a6c4580b8d351833c9ee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646311"
---
# <a name="workflow-security"></a>Sicurezza del flusso di lavoro
Windows Workflow Foundation (WF) è integrato con diverse tecnologie, ad esempio Microsoft SQL Server e Windows Communication Foundation (WCF). L'interazione con queste tecnologie può introdurre problemi di sicurezza nel flusso di lavoro, se eseguito in modo errato.

## <a name="persistence-security-concerns"></a>Problemi di sicurezza della persistenza

1. I flussi di lavoro che usano un'attività <xref:System.Activities.Statements.Delay> e la persistenza devono essere riattivati da un servizio. In Windows AppFabric viene usato il Servizio di gestione flussi di lavoro (WMS) per riattivare i flussi di lavoro con timer scaduti. WMS consente di creare un oggetto <xref:System.ServiceModel.WorkflowServiceHost> per ospitare il flusso di lavoro riattivato. Se il servizio WMS viene arrestato, i flussi di lavoro persistenti non verranno riattivati quando i timer scadono.

2. L'accesso alle istanze durevoli dovrebbe essere protetto da entità dannose esterne al dominio applicazione. Inoltre, gli sviluppatori devono assicurarsi che il codice dannoso non possa essere eseguito nello stesso dominio applicazione del codice dell'istanza durevole.

3. L'istanza durevole non deve essere eseguita con autorizzazioni (di amministratore) elevate.

4. I dati che vengono elaborati all'esterno del dominio applicazione devono essere protetti.

5. Le applicazioni che richiedono una isolamento di sicurezza non devono condividere la stessa istanza dell'astrazione dello schema. Tali applicazioni devono usare provider di archiviazione differenti o provider di archiviazione configurati per l'uso di istanze di archiviazione.

## <a name="sql-server-security-concerns"></a>Problemi di sicurezza relativi a SQL Server

- Quando si usano numerose attività figlio, percorsi, segnalibri, estensioni host o ambiti o quando si usano segnalibri con payload di notevoli dimensioni, la memoria può esaurirsi o si può allocare eccessivo spazio del database durante la persistenza. Questa situazione può essere attenuata con la sicurezza a livello di oggetto e a livello di database.

- Quando si usa l'oggetto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>, l'archivio di istanze deve essere protetto.

- I dati sensibili nell'archivio di istanze devono essere crittografati. Per altre informazioni, vedere [Crittografia di SQL Server](/sql/relational-databases/security/encryption/sql-server-encryption).

- Poiché la stringa di connessione del database è spesso inclusa in un file di configurazione, è necessario usare la sicurezza a livello di Windows (ACL) per assicurarsi che il file di configurazione (in genere Web.Config) sia protetto e che le informazioni sull'accesso e sulla password non siano incluse nella stringa di connessione. Tra il database e il server Web dovrebbe invece essere usata l'autenticazione di Windows.

## <a name="considerations-for-workflowservicehost"></a>Considerazioni su WorkflowServiceHost

- Gli endpoint di Windows Communication Foundation (WCF) usati nei flussi di lavoro devono essere protetti. Per altre informazioni, vedere [Cenni preliminari](../wcf/feature-details/security-overview.md)sulla sicurezza WCF.

- È possibile implementare l'autorizzazione a livello host usando <xref:System.ServiceModel.ServiceAuthorizationManager>. Per informazioni dettagliate, vedere [Procedura: creare un gestore autorizzazioni personalizzato per un servizio.](../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)

- L'oggetto ServiceSecurityContext per il messaggio in arrivo è disponibile anche dall'interno del flusso di lavoro tramite l'accesso a OperationContext.

## <a name="wf-security-pack-ctp"></a>WF Security Pack CTP
 Microsoft WF Security Pack Community Technology Preview (CTP) 1 è un insieme di attività e la relativa implementazione basata su [Windows Workflow Foundation](index.md) in [.NET Framework 4](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w0x726c2(v=vs.100)) (WF 4) e Windows Identity Foundation [(WIF).](https://docs.microsoft.com/previous-versions/dotnet/framework/security/index) Microsoft WF Security Pack CTP 1 contiene sia le attività e che le finestre di progettazione che illustrano come attivare facilmente i diversi scenari relativi alla sicurezza mediante il flusso di lavoro, tra cui:

1. Rappresentazione di un'identità client nel flusso di lavoro

2. Autorizzazione nel flusso di lavoro, come PrincipalPermission e la convalida delle attestazioni

3. La messaggistica autenticata usando ClientCredentials specificato nel flusso di lavoro, ad esempio il nome utente/password o un token recuperato da un servizio token di sicurezza (STS)

4. Propagazione di un token di sicurezza client a un servizio back-end (delega basata su richieste) usando ActAs di WS-Trust

Per ulteriori informazioni e per scaricare il CTP di WF Security Pack, vedere: [WF Security Pack CTP](https://archive.codeplex.com/?p=wf)
