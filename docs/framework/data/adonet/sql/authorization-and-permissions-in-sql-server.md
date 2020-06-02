---
title: Autorizzazioni in SQL Server
description: Informazioni su come concedere in modo esplicito le autorizzazioni per rendere gli oggetti di database creati accessibili agli utenti in SQL Server con ADO.NET.
ms.date: 03/30/2017
ms.assetid: d340405c-91f4-4837-a3cc-a238ee89888a
ms.openlocfilehash: eb01e29b36da5e1793b9176301a968a42115d19c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286533"
---
# <a name="authorization-and-permissions-in-sql-server"></a>Autorizzazioni in SQL Server
Quando si creano oggetti di database, è necessario concedere in modo esplicito le autorizzazioni per renderli accessibili agli utenti. Ogni oggetto a protezione diretta dispone di autorizzazioni che possono essere concesse a un'entità di sicurezza usando istruzioni di autorizzazione.  
  
## <a name="the-principle-of-least-privilege"></a>Principio dei privilegi minimi  
 Lo sviluppo di un'applicazione usando un approccio basato su un account utente con privilegi minimi rappresenta una parte importante di una strategia difensiva dettagliata per fronteggiare i rischi per la sicurezza. Tale approccio assicura infatti che gli utenti seguano il principio dei privilegi minimi ed effettuino sempre l'accesso con account utente limitati. Le attività amministrative vengono suddivise usando i ruoli predefiniti del server, tuttavia l'uso del ruolo predefinito del server `sysadmin` presenta particolari restrizioni.  
  
 Attenersi sempre al principio dei privilegi minimi quando si concedono autorizzazioni agli utenti del database. Concedere le autorizzazioni minime necessarie per consentire a un utente o a un ruolo di eseguire una determinata attività.  
  
> [!IMPORTANT]
> Lo sviluppo e il test di un'applicazione per la quale è stato usato l'approccio basato su un account utente con privilegi minimi implica maggiori difficoltà durante il processo di sviluppo. È infatti più agevole creare oggetti e scrivere codice quando si è connessi come amministratore di sistema o proprietario del database rispetto a quando si usa un account con privilegi minimi. Tuttavia, lo sviluppo di applicazioni con un account dotato di privilegi maggiori può offuscare l'impatto di funzionalità ridotte quando utenti con privilegi minimi tentano di eseguire un'applicazione per il cui corretto funzionamento sono richieste autorizzazioni elevate. D'altro canto, concedere agli utenti autorizzazioni eccessive per consentire loro di disporre nuovamente delle funzionalità perse può esporre l'applicazione a potenziali attacchi. La progettazione, lo sviluppo e il test dell'applicazione per il cui accesso viene usato un account con privilegi minimi consentono invece di applicare un approccio disciplinato alla pianificazione della sicurezza, eliminando sorprese sgradite ed impedendo di cedere alla tentazione di concedere privilegi elevati per risolvere rapidamente il problema. Per il test è possibile usare un account di accesso SQL Server anche se per la distribuzione dell'applicazione si intende usare l'autenticazione di Windows.  
  
## <a name="role-based-permissions"></a>Autorizzazioni basate sui ruoli  
 La concessione delle autorizzazioni ai ruoli anziché agli utenti consente di semplificare l'amministrazione della sicurezza. I set di autorizzazioni assegnati ai ruoli vengono ereditati da tutti i membri del ruolo. È più semplice aggiungere o rimuovere utenti da un ruolo anziché ricreare set di autorizzazioni distinti per i singoli utenti. I ruoli possono essere annidati, tuttavia un numero eccessivo di livelli di annidamento può comportare problemi di prestazioni. Per semplificare l'assegnazione delle autorizzazioni, è inoltre possibile aggiungere utenti a ruoli predefiniti del database.  
  
 È possibile concedere autorizzazioni a livello di schema. Gli utenti ereditano automaticamente autorizzazioni su tutti i nuovi oggetti creati nello schema, pertanto non è necessario concedere autorizzazioni quando vengono creati nuovi oggetti.  
  
## <a name="permissions-through-procedural-code"></a>Autorizzazioni tramite codice procedurale  
 L'incapsulamento dell'accesso ai dati tramite moduli, ad esempio stored procedure e funzioni definite dall'utente, consente di definire un ulteriore livello di protezione per l'applicazione. È possibile impedire agli utenti di interagire direttamente con oggetti di database concedendo autorizzazioni solo a stored procedure o funzioni e negandole agli oggetti sottostanti, ad esempio le tabelle. In SQL Server è possibile eseguire questa operazione tramite il concatenamento della proprietà.  
  
## <a name="permission-statements"></a>Istruzioni di autorizzazione  
 La tabella seguente descrive le tre istruzioni di autorizzazione Transact-SQL.  
  
|Istruzione di autorizzazione|Descrizione|  
|--------------------------|-----------------|  
|GRANT|Consente di concedere un'autorizzazione.|  
|REVOKE|Consente di revocare un'autorizzazione. Corrisponde allo stato predefinito di un nuovo oggetto. Un'autorizzazione revocata a un utente o a un ruolo può tuttavia ancora essere ereditata da altri gruppi o ruoli a cui è assegnata l'entità di sicurezza.|  
|NEGA|Consente di revocare un'autorizzazione in modo che non possa essere ereditata. Ha la precedenza su tutte le autorizzazioni, ma non si applica a proprietari di oggetti o a membri di `sysadmin`. Se si usa DENY per negare le autorizzazioni su un oggetto al ruolo `public`, le autorizzazioni verranno negate a tutti gli utenti e ruoli, ad eccezione dei parte proprietari dell'oggetto e dei membri di `sysadmin`.|  
  
- L'istruzione GRANT consente di assegnare a un gruppo o un ruolo autorizzazioni che possono essere ereditate dagli utenti del database. Tuttavia, poiché l'istruzione DENY ha la precedenza su tutte le altre istruzioni di autorizzazione, un utente al quale è stata negata un'autorizzazione non può ereditarla da un altro ruolo.  
  
> [!NOTE]
> Non è possibile negare autorizzazioni ai membri del ruolo predefinito del server `sysadmin` e ai proprietari dell'oggetto.  
  
## <a name="ownership-chains"></a>Catene di proprietà  
 SQL Server assicura che l'accesso agli oggetti sia consentito solo alle entità di sicurezza cui è stata concessa l'autorizzazione. Se più oggetti di database accedono ad altri oggetti di database, la sequenza viene denominata catena. Quando SQL Server attraversa i collegamenti della catena, valuta le autorizzazioni in modo diverso rispetto a quanto avviene durante l'accesso a singoli elementi. Quando l'accesso a un oggetto avviene tramite una catena, SQL Server confronta dapprima il proprietario dell'oggetto con il proprietario dell'oggetto chiamante, ovvero il collegamento precedente nella catena. Se il proprietario di entrambi oggetti è lo stesso, le autorizzazioni sull'oggetto a cui viene fatto riferimento non vengono controllate. Ogni volta che un oggetto accede a un altro oggetto il cui proprietario è diverso, la catena di proprietà viene interrotta e SQL Server deve controllare il contesto di sicurezza del chiamante.  
  
## <a name="procedural-code-and-ownership-chaining"></a>Codice procedurale e concatenamento delle proprietà  
 Si supponga che un utente siano concesse autorizzazioni di esecuzione su una stored procedure che seleziona dati da una tabella. Se il proprietario della stored procedure e della tabella è lo stesso, non è necessario che all'utente vengano concesse autorizzazioni sulla tabella ed è persino possibile negarle. Tuttavia, se i proprietari della stored procedure e della tabella sono diversi, SQL Server deve controllare le autorizzazioni dell'utente sulla tabella prima di consentire l'accesso ai dati.  
  
> [!NOTE]
> Il concatenamento delle proprietà non si applica nel caso di istruzioni SQL dinamiche. Per chiamare una procedura che esegue un'istruzione SQL, è necessario che al chiamante siano concesse autorizzazioni sulle tabelle sottostanti, esponendo in tal l'applicazione ad attacchi SQL injection. In SQL Server vengono forniti nuovi meccanismi, ad esempio la rappresentazione e la firma di moduli con i certificati, per i quali non è richiesta la concessione di autorizzazioni sulle tabelle sottostanti e che possono essere usati anche con stored procedure CLR.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per ulteriori informazioni, vedere le risorse seguenti.  
  
|Resource|Descrizione|  
|--------------|-----------------|  
|[Autorizzazioni](/sql/relational-databases/security/permissions-database-engine)|Contiene argomenti che illustrano la gerarchia delle autorizzazioni, le viste del catalogo e le autorizzazioni dei ruoli predefiniti del server e del database.|
  
## <a name="see-also"></a>Vedere anche

- [Protezione delle applicazioni ADO.NET](../securing-ado-net-applications.md)
- [Scenari di sicurezza delle applicazioni in SQL Server](application-security-scenarios-in-sql-server.md)
- [Autenticazione in SQL Server](authentication-in-sql-server.md)
- [Ruoli server e database in SQL Server](server-and-database-roles-in-sql-server.md)
- [Proprietà e separazione tra schemi e utenti in SQL Server](ownership-and-user-schema-separation-in-sql-server.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
