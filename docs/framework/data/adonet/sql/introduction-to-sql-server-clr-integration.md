---
title: Introduzione all'integrazione CLR in SQL Server
description: L'integrazione di CLR con SQL Server supporta stored procedure, trigger, funzioni definite dall'utente, tipi definiti dall'utente e funzioni di aggregazione definite dall'utente nel codice gestito.
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: fa2ef68792d09cf94b3e0680a14bd79f9b593999
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286430"
---
# <a name="introduction-to-sql-server-clr-integration"></a>Introduzione all'integrazione CLR in SQL Server
Common Language Runtime (CLR) rappresenta il fulcro di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework. Il codice eseguito in CLR viene chiamato codice gestito. CLR fornisce varie funzioni e servizi necessari per l'esecuzione del programma, incluse le funzioni di compilazione JIT (Just-In-Time), di allocazione e gestione della memoria, di imposizione dell'indipendenza dai tipi, di gestione delle eccezioni, di gestione dei thread e di sicurezza.  
  
 Grazie all'integrazione di CLR in Microsoft SQL Server, è possibile creare stored procedure, trigger, funzioni definite dall'utente, tipi definiti dall'utente e aggregazioni definite dall'utente nel codice gestito. Poiché il codice gestito viene compilato nel codice nativo prima dell'esecuzione, è possibile ottenere notevoli miglioramenti delle prestazioni in alcuni scenari.  
  
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
 Dopo aver testato e verificato i metodi CLR sul server di prova, sarà possibile distribuirli a server di produzione utilizzando uno script di distribuzione Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio. Per informazioni più dettagliate, vedere la versione di SQL Server documentazione per la versione di SQL Server in uso.  
  
 **Documentazione di SQL Server**  
  
1. [Distribuzione di oggetti di database CLR](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a>Sicurezza per l'integrazione con CLR  
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
