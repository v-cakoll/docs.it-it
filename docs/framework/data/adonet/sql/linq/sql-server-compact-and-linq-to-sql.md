---
title: SQL Server Compact e LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: b5a1a12018bd85cf313c1841e6b67ab2edf67b4a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792541"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact e LINQ to SQL
SQL Server Compact è il database predefinito installato con Visual Studio. Per ulteriori informazioni, vedere [utilizzo di SQL Server Compact (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2012/aa983321(v=vs.110)).  
  
 In questo argomento vengono descritte le differenze principali relative all'utilizzo, alla configurazione, ai set di funzionalità [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e all'ambito del supporto.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>Caratteristiche di SQL Server Compact in relazione a LINQ to SQL  
 Per impostazione predefinita, SQL Server Compact viene installato per tutte le edizioni di Visual Studio ed è pertanto disponibile nel computer di sviluppo per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]l'uso con. Ma la distribuzione di un'applicazione che usa SQL Server Compact [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e differisce da quella per un'applicazione SQL Server. SQL Server Compact non fa parte di .NET Framework e pertanto deve essere fornito con l'applicazione o scaricato separatamente dal sito Microsoft.  
  
 Tenere presente le seguenti caratteristiche:  
  
- SQL Server Compact viene fornito come una DLL che può essere usata direttamente sui file di database (con estensione sdf).  
  
- SQL Server Compact viene eseguito nello stesso processo dell'applicazione client. L'efficienza della comunicazione con SQL Server Compact può quindi essere significativamente più elevata rispetto alla comunicazione con SQL Server. D'altra parte, SQL Server Compact richiede l'interoperabilità tra codice gestito e non gestito con i costi di supervisore.  
  
- Le dimensioni della DLL SQL Server Compact sono limitate. Questa funzionalità riduce le dimensioni complessive dell'applicazione.  
  
- Il runtime di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] e lo strumento della riga di comando SQLMetal supportano SQL Server Compact.  
  
- Il Object Relational Designer non supporta SQL Server Compact.  
  
## <a name="feature-set"></a>Set di funzionalità  
 Il set di funzionalità SQL Server Compact è molto più semplice rispetto al set di funzionalità di SQL Server nei modi seguenti che possono [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] influire sulle applicazioni:  
  
- SQL Server Compact non supporta stored procedure o visualizzazioni.  
  
- SQL Server Compact supporta solo un subset di tipi di dati e funzioni SQL.  
  
- SQL Server Compact supporta solo un subset di costrutti SQL.  
  
- SQL Server Compact fornisce solo un'utilità di ottimizzazione con funzionalità minime. Potrebbe verificarsi il timeout di alcune query.  
  
- SQL Server Compact non supporta il trust parziale.  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento](reference.md)
