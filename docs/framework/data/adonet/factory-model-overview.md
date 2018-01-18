---
title: Cenni preliminari sul modello di factory
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5dc81c4-7554-44b9-b513-769bd61e2e7b
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 0194cd6789ae6ddebeeee65abf1a4fca4a2bc0d6
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="factory-model-overview"></a>Cenni preliminari sul modello di factory
In ADO.NET 2.0 sono state introdotte nuove classi di base nello spazio dei nomi <xref:System.Data.Common>. Le classi di base sono astratte, ovvero non è possibile creare un'istanza di tali classi in modo diretto. Includono <xref:System.Data.Common.DbConnection>, <xref:System.Data.Common.DbCommand>e <xref:System.Data.Common.DbDataAdapter> e sono condivise tra i provider di dati .NET Framework, ad esempio <xref:System.Data.SqlClient> e <xref:System.Data.OleDb>. L'aggiunta di classi di base consente di aggiungere più facilmente funzionalità ai provider di dati .NET Framework senza dover creare nuove interfacce.  
  
 In ADO.NET 2.0 sono state inoltre introdotte classi di base astratte che consentono agli sviluppatori di scrivere codice per l'accesso ai dati generico e non dipendente da un provider di dati specifico.  
  
## <a name="the-factory-design-pattern"></a>Modello di progettazione a livello di factory  
 Il modello di programmazione per la scrittura di codice indipendente dal provider è basato sul modello di progettazione a livello di factory, che usa una singola API per accedere ai database di più provider. Il nome di questo modello è appropriato in quanto richiede l'uso di un oggetto specializzato soltanto per creare altri oggetti, non molto diversamente da una fabbrica reale. Per una descrizione più dettagliata del modello di progettazione di factory, vedere "[la scrittura di codice di accesso ai dati generico in ASP.NET 2.0 e ADO.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=55915)" e "Generico di codifica con di ADO.NET 2.0 Base le classi factory e" [http:// MSDN.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp](http://msdn.microsoft.com/library/default.asp?url=/library/dnvs05/html/vsgenerics.asp) su MSDN.  
  
 A partire da ADO.NET 2.0 la classe <xref:System.Data.Common.DbProviderFactories> fornisce metodi `static` (o `Shared` in Visual Basic) per la creazione di un'istanza di <xref:System.Data.Common.DbProviderFactory>. L'istanza restituisce quindi un oggetto fortemente tipizzato corretto basato sulle informazioni fornite dal provider e dalla stringa di connessione in fase di esecuzione.  
  
## <a name="see-also"></a>Vedere anche  
 [Recupero di una classe DbProviderFactory](../../../../docs/framework/data/adonet/obtaining-a-dbproviderfactory.md)  
 [DbConnection, DbCommand e DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [Modifica di dati con un oggetto DbDataAdapter](../../../../docs/framework/data/adonet/modifying-data-with-a-dbdataadapter.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
