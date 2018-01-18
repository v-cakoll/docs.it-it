---
title: Sicurezza dell'integrazione CLR in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4364e35bbce3261c8f6e6c45002d5a603007b85
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="clr-integration-security-in-sql-server"></a>Sicurezza dell'integrazione CLR in SQL Server
Microsoft SQL Server fornisce l'integrazione del componente CLR di .NET Framework. L'integrazione CLR consente di possibile scrivere stored procedure, trigger, tipi definiti dall'utente, funzioni definite dall'utente, aggregati definiti dall'utente e funzioni con valori di tabella di flusso usando qualsiasi linguaggio di .NET Framework, inclusi Microsoft Visual Basic .NET e Microsoft Visual C#.  
  
 CLR supporta un modello di sicurezza per il codice gestito denominato CAS (Code Access Security). In questo modello, le autorizzazioni vengono concesse agli assembly in base all'evidenza fornita dal codice nei metadati. In SQL Server il modello di sicurezza basato su utente di SQL Server si integra con il modello di sicurezza basato su accesso al codice di CLR.  
  
## <a name="external-resources"></a>Risorse esterne  
 Per altre informazioni sull'integrazione di CLR con SQL Server, vedere le risorse seguenti.  
  
|Risorsa|Descrizione|  
|--------------|-----------------|  
|[Sicurezza dall'accesso di codice](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|Contiene argomenti in cui viene descritta la sicurezza dall'accesso di codice in .NET Framework.|  
|[Sicurezza dell'integrazione con CLR](http://go.microsoft.com/fwlink/?LinkId=59998)|Viene descritto il modello di sicurezza per il codice gestito in esecuzione in SQL Server|  
  
## <a name="see-also"></a>Vedere anche  
 [Protezione delle applicazioni ADO.NET](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Scenari di sicurezza delle applicazioni in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Integrazione di Common Language Runtime di SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
