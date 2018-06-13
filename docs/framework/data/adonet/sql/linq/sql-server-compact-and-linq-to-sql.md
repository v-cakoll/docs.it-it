---
title: SQL Server Compact e LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 74b8a7a6dfc9a4050dbba9a8c2f6969dba42656c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355786"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact e LINQ to SQL
SQL Server Compact è il database predefinito installato con Visual Studio. Per ulteriori informazioni, vedere [PAVE su utilizzando SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 In questo argomento vengono descritte le differenze principali di utilizzo, configurazione, set di funzionalità e ambito di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supportano.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Caratteristiche di SQL Server Compact in relazione a LINQ to SQL  
 Per impostazione predefinita, SQL Server Compact è installato per tutte le edizioni di Visual Studio e pertanto è disponibile nel computer di sviluppo per l'utilizzo con [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Ma la distribuzione di un'applicazione che utilizza SQL Server Compact e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] differisce da quella per un'applicazione SQL Server. SQL Server Compact non fa parte di .NET Framework e pertanto deve essere fornito con l'applicazione o scaricato separatamente dal sito Microsoft.  
  
 Tenere presente le seguenti caratteristiche:  
  
-   SQL Server Compact viene fornito come una DLL che può essere usata direttamente sui file di database (con estensione sdf).  
  
-   SQL Server Compact viene eseguito nello stesso processo dell'applicazione client. L'efficienza della comunicazione con SQL Server Compact può pertanto essere notevolmente maggiore rispetto alla comunicazione con SQL Server. D'altra parte, SQL Server Compact richiede l'interoperabilità tra codice gestito e con i relativi costi.  
  
-   La dimensione della DLL di SQL Server Compact è ridotta. Questa funzionalità riduce le dimensioni complessive dell'applicazione.  
  
-   Il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e lo strumento della riga di comando SQLMetal supportano SQL Server Compact.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] non supporta SQL Server Compact.  
  
## <a name="feature-set"></a>Set di funzionalità  
 Il set di funzionalità di SQL Server Compact è molto più semplice rispetto a quello di SQL Server nei modi seguenti che possono influire sulla [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applicazioni:  
  
-   SQL Server Compact non supporta stored procedure o visualizzazioni.  
  
-   SQL Server Compact supporta solo un subset di tipi di dati e funzioni SQL.  
  
-   SQL Server Compact supporta solo un subset di costrutti SQL.  
  
-   SQL Server Compact fornisce solo un'utilità di ottimizzazione con funzionalità minime. È possibile che alcune query potrebbe scadere.  
  
-   SQL Server Compact non supporta il trust parziale.  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
