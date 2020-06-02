---
title: Recupero di un valore singolo da un database
description: Informazioni su come restituire un singolo valore in ADO.NET. Questo codice di esempio restituisce il valore della colonna Identity per un record inserito.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: a6f268f72f8b8a09ae48ba3cad6254323cb95a20
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286702"
---
# <a name="obtaining-a-single-value-from-a-database"></a>Recupero di un valore singolo da un database
Può essere necessario restituire informazioni del database costituite semplicemente da un singolo valore anziché da una tabella o da un flusso di dati. È ad esempio possibile che si desideri restituire il risultato di una funzione di aggregazione, ad esempio COUNT ( \* ), Sum (price) o AVG (Quantity). L'oggetto **Command** fornisce la possibilità di restituire valori singoli usando il metodo **ExecuteScalar** . Il metodo **ExecuteScalar** restituisce, come valore scalare, il valore della prima colonna della prima riga del set di risultati.  
  
 Nell'esempio di codice seguente viene inserito un nuovo valore nel database usando un <xref:System.Data.SqlClient.SqlCommand>. Per restituire il valore della colonna Identity per il record inserito, viene usato il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Comandi e parametri](commands-and-parameters.md)
- [Esecuzione di un comando](executing-a-command.md)
- [DbConnection, DbCommand e DbException](dbconnection-dbcommand-and-dbexception.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
