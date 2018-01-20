---
title: "Applicazioni a più livelli e remote con LINQ to SQL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 272c125096e08819a7f70b830e1f359a760f687f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>Applicazioni a più livelli e remote con LINQ to SQL
È possibile creare applicazioni a più livelli che usano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. In genere, il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] contesto dei dati, le classi di entità e logica di costruzione delle query si trovano nel livello intermedio come livello di accesso ai dati (DAL). La regola business e i dati non persistenti possono essere implementati completamente in classi e metodi parziali di entità e nel contesto dati oppure possono essere implementati in classi separate.  
  
 Il livello client o di presentazione chiama i metodi nell'interfaccia remota del livello intermedio e il DAL di tale livello eseguirà le query o le stored procedure di cui è stato eseguito il mapping ai metodi <xref:System.Data.Linq.DataContext>. Il livello intermedio in genere restituisce i dati ai client come rappresentazioni XML di entità o oggetti proxy.  
  
 Nel livello intermedio, le entità vengono create dal contesto dati che tiene traccia dello stato e gestisce il caricamento posticipato e l'invio delle modifiche al database. Queste entità sono "collegate" all'oggetto `DataContext`. Tuttavia, le entità vengono disconnesse dopo l'invio a un altro livello mediante la serializzazione, ovvero `DataContext` non tiene più traccia del relativo stato. Le entità inviate dal client per gli aggiornamenti devono essere ricollegate al contesto dati prima che [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sia in grado di inviare le modifiche al database. Il client ha lo scopo di fornire al livello intermedio i valori originali e/o i timestamp se richiesti per i controlli di concorrenza ottimistica.  
  
 Nelle applicazioni ASP.NET, <xref:System.Web.UI.WebControls.LinqDataSource> gestisce gran parte di questa complessità. Per ulteriori informazioni, vedere [NIB: Panoramica del controllo Server Web LinqDataSource](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="additional-resources"></a>Risorse aggiuntive  
 Per altre informazioni sull'implementazione delle applicazioni a più livelli che usano [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], vedere gli argomenti seguenti:  
  
-   [Più livelli di LINQ to SQL con ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [Più livelli di LINQ to SQL con Servizi Web](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [LINQ to SQL con applicazioni client/server strettamente accoppiate](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [Implementazione della logica di business a più livelli](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [Recupero di dati e operazioni CUD in applicazioni a più livelli (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 Per ulteriori informazioni sulle applicazioni a più livelli che utilizzano i dataset ADO.NET, vedere [utilizzano set di dati nelle applicazioni a più livelli](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).  
  
## <a name="see-also"></a>Vedere anche  
 [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
