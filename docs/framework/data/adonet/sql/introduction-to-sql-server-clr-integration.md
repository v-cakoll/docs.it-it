---
title: Introduzione all'integrazione CLR in SQL Server
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: dd0ef041db13aa842554c70533770bf99c369941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33365579"
---
# <a name="introduction-to-sql-server-clr-integration"></a>Introduzione all'integrazione CLR in SQL Server
Common Language Runtime (CLR) rappresenta l'elemento essenziale di Microsoft .NET Framework e fornisce l'ambiente di esecuzione per tutto il codice .NET Framework. Il codice eseguito all'interno di CLR viene definito codice gestito. CLR fornisce diverse funzioni e vari servizi richiesti per l'esecuzione del programma, che includono la compilazione JIT (Just-In-Time), l'allocazione e la gestione della memoria, l'applicazione dell'indipendenza dai tipi, la gestione delle eccezioni e dei thread e la sicurezza.  
  
 Con CLR incluso in Microsoft SQL Server (integrazione di CLR), è possibile creare nuove stored procedure, trigger, funzioni definite dall'utente e aggregati definiti dall'utente nel codice gestito. Poiché il codice gestito viene processato con il codice nativo prima dell'esecuzione, in determinati scenari è possibile ottenere significativi aumenti di prestazioni.  
  
 Il codice gestito usa la sicurezza dall'accesso di codice (CAS, Code Access Security), i collegamenti del codice e i domini dell'applicazione per impedire alle assembly di eseguire determinate operazioni. In SQL Server viene usato CAS per proteggere il codice gestito e per impedire il danneggiamento del sistema operativo o del server di database.  
  
 In questa sezione vengono fornite solo le informazioni di base per iniziare a programmare con l'integrazione CLR di SQL Server. Tali informazioni non sono da considerarsi esaustive. Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
-   [Panoramica dell'integrazione con Common Language Runtime (CLR)](http://go.microsoft.com/fwlink/?LinkId=115242)  
  
## <a name="enabling-clr-integration"></a>Abilitazione dell'integrazione con CLR  
 In Microsoft SQL Server la funzione di integrazione CLR (Common Language Runtime) è disattivata per impostazione predefinita e deve essere abilitata in modo da usare oggetti implementati mediante l'integrazione CLR. Per abilitare l'integrazione CLR mediante Transact-SQL, usare l'opzione `clr enabled` della stored procedure `sp_configure`, come illustrato di seguito:  
  
```  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 È possibile disabilitare l'integrazione CLR impostando l'opzione `clr enabled` su 0. Quando si disabilita l'integrazione CLR, SQL Server non esegue più le routine CLR e scarica tutti i domini dell'applicazione.  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
-   [Abilitazione dell'integrazione CLR](http://go.microsoft.com/fwlink/?LinkId=115230)  
  
## <a name="deploying-a-clr-assembly"></a>Distribuzione di un assembly CLR  
 Dopo che i metodi CLR sono stati testati e verificati nel server di prova, possono essere distribuiti nei server di produzione usando uno script di distribuzione. Lo script di distribuzione può essere generato manualmente o tramite SQL Server Management Studio. Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
1.  [Distribuzione di oggetti di Database CLR](http://go.microsoft.com/fwlink/?LinkId=115232)  
  
## <a name="clr-integration-security"></a>Sicurezza dell'integrazione con CLR  
 Il modello di sicurezza dell'integrazione di Microsoft SQL Server con CLR (Common Language Runtime) di Microsoft .NET Framework consente di gestire e di proteggere l'accesso tra diversi tipi di oggetti CLR e non CLR in esecuzione in SQL Server. Questi oggetti possono essere chiamati da un'istruzione Transact-SQL o da un altro oggetto CLR in esecuzione sul server.  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
-   [Sicurezza dell'integrazione con CLR](http://go.microsoft.com/fwlink/?LinkId=115234)  
  
## <a name="debugging-a-clr-assembly"></a>Debug di un assembly CLR  
 Microsoft SQL Server fornisce il supporto per il debug di oggetti Transact-SQL e CLR (Common Language Runtime) nel database. Il debug può essere eseguito in entrambi i linguaggi, ovvero gli utenti possono passare agevolmente da oggetti Transact-SQL a oggetti CLR e viceversa.  
  
 Per informazioni più dettagliate, vedere la versione della documentazione online di SQL Server corrispondente alla versione di SQL Server in uso.  
  
 **Documentazione online di SQL Server**  
  
-   [Debug di oggetti di Database CLR](http://go.microsoft.com/fwlink/?LinkId=115236)  
  
## <a name="see-also"></a>Vedere anche  
 [Creazione di oggetti di SQL Server 2005 nel codice gestito](http://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [Sicurezza dell'accesso di codice e ADO.NET](../../../../../docs/framework/data/adonet/code-access-security.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
