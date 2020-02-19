---
title: Introduzione all'integrazione CLR in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 41dd89af4f45c673cf6b7283fc39aaf91fd9963c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452409"
---
# <a name="introduction-to-sql-server-clr-integration"></a>Introduzione all'integrazione CLR in SQL Server
Common Language Runtime (CLR) rappresenta l'elemento essenziale di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework. Il codice eseguito all'interno di CLR viene definito codice gestito. CLR fornisce diverse funzioni e vari servizi richiesti per l'esecuzione del programma, che includono la compilazione JIT (Just-In-Time), l'allocazione e la gestione della memoria, l'applicazione dell'indipendenza dai tipi, la gestione delle eccezioni e dei thread e la sicurezza.  
  
 Con CLR incluso in Microsoft SQL Server (integrazione di CLR), è possibile creare nuove stored procedure, trigger, funzioni definite dall'utente e aggregati definiti dall'utente nel codice gestito. Poiché il codice gestito viene processato con il codice nativo prima dell'esecuzione, in determinati scenari è possibile ottenere significativi aumenti di prestazioni.  
  
 Il codice gestito usa la sicurezza dall'accesso di codice (CAS, Code Access Security), i collegamenti del codice e i domini dell'applicazione per impedire alle assembly di eseguire determinate operazioni. In SQL Server viene usato CAS per proteggere il codice gestito e per impedire il danneggiamento del sistema operativo o del server di database.  
  
 In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive. Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
- [Panoramica dell'integrazione con CLR (Common Language Runtime)](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a>Abilitazione dell'integrazione con CLR  
 In Microsoft SQL Server la funzionalità di integrazione CLR (Common Language Runtime) è disattivata per impostazione predefinita e deve essere abilitata in modo da usare oggetti implementati mediante l'integrazione CLR. Per abilitare l'integrazione CLR mediante Transact-SQL, usare l'opzione `clr enabled` della stored procedure `sp_configure`, come illustrato di seguito:  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 È possibile disabilitare l'integrazione CLR impostando l'opzione `clr enabled` su 0. Quando si disabilita l'integrazione CLR, SQL Server non esegue più le routine CLR e scarica tutti i domini dell'applicazione.  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
- [Abilitazione dell'integrazione con CLR](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a>Distribuzione di un assembly CLR  
 Dopo che i metodi CLR sono stati testati e verificati nel server di prova, possono essere distribuiti nei server di produzione usando uno script di distribuzione. Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio. Per informazioni più dettagliate, vedere la versione di SQL Server documentazione per la versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
1. [Distribuzione di oggetti di database CLR](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a>Sicurezza dell'integrazione con CLR  
 Il modello di sicurezza dell'integrazione di Microsoft SQL Server con CLR (Common Language Runtime) di Microsoft .NET Framework consente di gestire e di proteggere l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione in SQL Server. Questi oggetti possono essere chiamati da un'istruzione Transact-SQL o da un altro oggetto CLR in esecuzione sul server.  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
- [Sicurezza per l'integrazione con CLR](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a>Debug di un assembly CLR  
 Microsoft SQL Server fornisce il supporto per il debug di oggetti Transact-SQL e CLR (Common Language Runtime) nel database. Il debug può essere eseguito in entrambi i linguaggi, ovvero gli utenti possono passare agevolmente da oggetti Transact-SQL a oggetti CLR e viceversa.  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
- [Debug di oggetti di database CLR](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a>Vedere anche

- [Sicurezza dell'accesso di codice e ADO.NET](../code-access-security.md)
- [Panoramica di ADO.NET](../ado-net-overview.md)
