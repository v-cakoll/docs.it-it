---
title: Recupero di un valore singolo da un database
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 09231a360408efe3a167a9e613fdf85631c0be52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="obtaining-a-single-value-from-a-database"></a>Recupero di un valore singolo da un database
Può essere necessario restituire informazioni del database costituite semplicemente da un singolo valore anziché da una tabella o da un flusso di dati. Ad esempio, si desidera restituire il risultato di una funzione di aggregazione, ad esempio conteggio (\*), SUM (price) o AVG (Quantity). Il **comando** oggetto offre la possibilità di restituire singoli valori usando il **ExecuteScalar** metodo. Il **ExecuteScalar** restituisce come un valore scalare, il valore della prima colonna della prima riga del set di risultati.  
  
 Nell'esempio di codice seguente viene inserito un nuovo valore nel database usando un <xref:System.Data.SqlClient.SqlCommand>. Per restituire il valore della colonna Identity per il record inserito, viene usato il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Comandi e parametri](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [Esecuzione di un comando](../../../../docs/framework/data/adonet/executing-a-command.md)  
 [DbConnection, DbCommand e DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
