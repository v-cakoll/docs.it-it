---
title: SQL Server Compact e LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 2717a94228dc1be8da0d84179201747d60c896a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact e LINQ to SQL
SQL Server Compact è il database predefinito installato con Visual Studio. Per ulteriori informazioni, vedere [PAVE su utilizzando SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/en-us/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 In questo argomento vengono descritte le differenze principali di utilizzo, configurazione, set di funzionalità e ambito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supportano.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Caratteristiche di SQL Server Compact in relazione a LINQ to SQL  
 Per impostazione predefinita, SQL Server Compact è installato per tutti i [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] edizioni ed è pertanto disponibile nel computer di sviluppo per l'utilizzo con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Distribuzione di un'applicazione che utilizza SQL Server Compact e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è diverso da quello per un [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] dell'applicazione. SQL Server Compact non fa parte di .NET Framework e pertanto deve essere fornito con l'applicazione o scaricato separatamente dal sito Microsoft.  
  
 Tenere presente le seguenti caratteristiche:  
  
-   SQL Server Compact viene fornito come una DLL che può essere usata direttamente sui file di database (con estensione sdf).  
  
-   SQL Server Compact viene eseguito nello stesso processo dell'applicazione client. L'efficienza della comunicazione con SQL Server Compact può pertanto essere significativamente più elevata rispetto alla comunicazione con [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]. D'altra parte, SQL Server Compact richiede l'interoperabilità tra codice gestito e con i relativi costi.  
  
-   La dimensione della DLL di SQL Server Compact è ridotta. Questa funzionalità riduce le dimensioni complessive dell'applicazione.  
  
-   Il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e lo strumento della riga di comando SQLMetal supportano SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] non supporta SQL Server Compact.  
  
## <a name="feature-set"></a>Set di funzionalità  
 Il set di funzionalità di SQL Server Compact è molto più semplice rispetto all'insieme di funzionalità di [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] nei modi seguenti che possono influire sulla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applicazioni:  
  
-   SQL Server Compact non supporta stored procedure o visualizzazioni.  
  
-   SQL Server Compact supporta solo un subset di tipi di dati e funzioni SQL.  
  
-   SQL Server Compact supporta solo un subset di costrutti SQL.  
  
-   SQL Server Compact fornisce solo un'utilità di ottimizzazione con funzionalità minime. È possibile che alcune query potrebbe scadere.  
  
-   SQL Server Compact non supporta il trust parziale.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
