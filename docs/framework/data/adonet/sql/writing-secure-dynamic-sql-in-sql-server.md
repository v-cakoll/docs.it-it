---
title: Scrittura dinamica sicura in SQL Server
ms.date: 03/30/2017
ms.assetid: df5512b0-c249-40d2-82f9-f9a2ce6665bc
ms.openlocfilehash: 0dc372b4e5554623d51a4add9a43f33d4a320f18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="writing-secure-dynamic-sql-in-sql-server"></a>Scrittura dinamica sicura in SQL Server
Per SQL injection si intende il processo mediante il quale un utente malintenzionato immette istruzioni Transact-SQL anziché input valido. Se l'input viene passato direttamente al server senza essere convalidato e se l'applicazione esegue inavvertitamente il codice inserito, è possibile che l'attacco danneggi o elimini permanentemente i dati.  
  
 Per la prevenzione degli attacchi di questo tipo è necessario esaminare tutte le procedure che creano istruzioni SQL, poiché in SQL Server vengono eseguite tutte le query sintatticamente valide ricevute. Anche i dati con parametri possono essere modificati da un utente malintenzionato abile e determinato. Se si usano istruzioni SQL dinamiche, aggiungere parametri ai comandi e non includere mai i valori dei parametri direttamente nella stringa di query.  
  
## <a name="anatomy-of-a-sql-injection-attack"></a>Anatomia di un attacco SQL injection  
 Il processo di injection termina prematuramente una stringa di testo e aggiunge un nuovo comando. Poiché prima che venga eseguito è possibile che al comando inserito vengano aggiunte ulteriori stringhe, l'utente malintenzionato termina la stringa inserita con un contrassegno di commento "--". In fase di esecuzione il testo che segue il contrassegno di commento viene ignorato. È possibile inserire più comandi usando il punto e virgola (;) come delimitatore.  
  
 Se il codice SQL inserito tramite injection è corretto dal punto di vista sintattico, le manomissioni non possono essere rilevate a livello di codice. È pertanto necessario convalidare tutto l'input utente ed esaminare attentamente il codice per l'esecuzione dei comandi SQL generati nel server in uso. Non eseguire mai la concatenazione di input utente non convalidato. La concatenazione delle stringhe costituisce il punto di ingresso principale per un attacco script injection.  
  
 Di seguito sono riportate alcune linee guida utili.  
  
-   Non compilare mai istruzioni Transact-SQL direttamente dall'input utente. Usare stored procedure per la convalida dell'input utente.  
  
-   Convalidare l'input utente testando tipo, lunghezza, formato e intervallo. Usare la funzione QUOTENAME() Transact-SQL per usare caratteri di escape per i nomi di sistema oppure la funzione REPLACE() per usare caratteri di escape per qualsiasi carattere di una stringa.  
  
-   Implementare più livelli di convalida per ciascun livello dell'applicazione.  
  
-   Testare le dimensioni e il tipo di dati dell'input e imporre limiti appropriati. In questo modo è possibile impedire intenzionali sovraccarichi del buffer.  
  
-   Testare il contenuto delle variabili stringa e accettare solo i valori previsti. Rifiutare voci contenenti dati binari, sequenze di escape e caratteri di commento.  
  
-   Quando si usano documenti XML, convalidare tutti i dati in base al relativo schema man mano che vengono immessi.  
  
-   In ambienti multilivello è necessario convalidare tutti i dati prima di consentirne l'inserimento nell'area attendibile.  
  
-   Non accettare le stringhe seguenti in campi da cui è possibile creare nomi di file: AUX, CLOCK$, da COM1 a COM8, CON, CONFIG$, da LPT1 a LPT8, NUL e PRN.  
  
-   Usare oggetti <xref:System.Data.SqlClient.SqlParameter> con stored procedure e comandi per fornire la verifica dei tipi e la convalida della lunghezza.  
  
-   Usare espressioni <xref:System.Text.RegularExpressions.Regex> nel codice client per filtrare i caratteri non validi.  
  
## <a name="dynamic-sql-strategies"></a>Strategie per le istruzioni SQL dinamiche  
 L'esecuzione di istruzioni SQL create in modo dinamico nel codice procedurale interrompe la catena di proprietà, facendo in modo che SQL Server controlli le autorizzazioni del chiamante sugli oggetti cui hanno accesso le istruzioni SQL dinamiche.  
  
 In SQL Server sono disponibili nuove tecniche per concedere agli utenti l'accesso ai dati usando stored procedure e funzioni definite dall'utente che eseguono istruzioni SQL dinamiche.  
  
-   Utilizzo della rappresentazione con di Transact-SQL EXECUTE AS clausola, come descritto in [personalizzazione delle autorizzazioni con rappresentazione in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).  
  
-   Firma di stored procedure con certificati, come descritto in [firma di Stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).  
  
### <a name="execute-as"></a>EXECUTE AS  
 La clausola EXECUTE AS sostituisce le autorizzazioni del chiamante con quelle dell'utente specificato nella clausola stessa. Le stored procedure o i trigger annidati vengono eseguiti nel contesto di sicurezza dell'utente proxy. Tale comportamento può causare l'interruzione di applicazioni che si basano sulla sicurezza a livello di riga o che richiedono controlli. Alcune funzioni che restituiscono l'identità dell'utente restituiscono in realtà l'utente associato alla clausola EXECUTE AS e non il chiamante originale. Viene ripristinato il contesto di esecuzione del chiamante originale solo dopo l'esecuzione della stored procedure o quando viene eseguita un'istruzione REVERT.  
  
### <a name="certificate-signing"></a>Firma dei certificati  
 Quando viene eseguita una stored procedure firmata con un certificato, le autorizzazioni concesse all'utente del certificato vengono unite con quelle del chiamante. Il contesto di esecuzione rimane lo stesso. L'utente del certificato non rappresenta il chiamante. L'implementazione della firma delle stored procedure richiede l'esecuzione di numerosi passaggi. Una stored procedure deve essere firmata nuovamente a ogni modifica.  
  
### <a name="cross-database-access"></a>Accesso tra database  
 Il concatenamento della proprietà tra database non funziona nei casi in cui vengono eseguite istruzioni SQL create in modo dinamico. È possibile risolvere il problema in SQL Server creando una stored procedure che accede ai dati in un altro database e firmare la procedura con un certificato esistente in entrambi i database. In questo modo si fornisce agli utenti l'accesso alle risorse del database usate dalla procedura senza concedere loro l'accesso o le autorizzazioni per il database.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Stored procedure](http://go.microsoft.com/fwlink/?LinkId=98233) e [attacchi SQL Injection](http://go.microsoft.com/fwlink/?LinkId=98234) nella documentazione Online di SQL Server|Viene descritto come creare stored procedure e come funziona SQL Injection.|  
|[Nuovi attacchi di troncamento SQL e su come evitarli](http://msdn.microsoft.com/msdnmag/issues/06/11/SQLSecurity/) in MSDN Magazine.|Viene descritto come delimitare caratteri e stringhe, SQL injection e modifiche da attacchi di troncamento.|  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Cenni preliminari sulla sicurezza in SQL Server](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Gestione delle autorizzazioni con stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/managing-permissions-with-stored-procedures-in-sql-server.md)  
 [Firma di stored procedure in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [Personalizzazione delle autorizzazioni con rappresentazione in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
