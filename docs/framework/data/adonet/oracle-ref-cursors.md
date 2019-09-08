---
title: Oggetti REF CURSOR Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 7cd29a6a20015c7ce4475b0211cb07f7ee78b530
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794880"
---
# <a name="oracle-ref-cursors"></a>Oggetti REF CURSOR Oracle
Il .NET Framework provider di dati per Oracle supporta il tipo di dati **ref CURSOR** di Oracle. Quando si usa il provider di dati per usare il tipo di dati REF CURSOR Oracle, considerare i seguenti comportamenti.  
  
> [!NOTE]
> Alcuni comportamenti si differenziano da quelli del provider Microsoft OLE DB per Oracle (MSDAORA).  
  
- Per motivi di prestazioni, il provider di dati per Oracle non associa automaticamente i tipi di dati **ref CURSOR** , come avviene in MSDAORA, a meno che non vengano specificati in modo esplicito.  
  
- Il provider di dati non supporta alcuna sequenza di escape ODBC, incluso il carattere di escape {resultset} usato per specificare i parametri REF CURSOR.  
  
- Per eseguire un stored procedure che restituisce Ref cursors, è <xref:System.Data.OracleClient.OracleParameterCollection> necessario definire i parametri in con un oggetto <xref:System.Data.OracleClient.OracleType> di **Cursor** e un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> oggetto di **output**. Il provider di dati supporta l'associazione dei REF CURSOR solo come parametri di output. I REF CURSOR come parametri di input non sono supportati.  
  
- Il recupero di un tipo <xref:System.Data.OracleClient.OracleDataReader> dal valore del parametro non è supportato. I valori sono di tipo <xref:System.DBNull> dopo l'esecuzione del comando.  
  
- L'unico valore di enumerazione **CommandBehavior** che funziona con i REF CURSOR, ad esempio quando si <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>chiama, è **CloseConnection**. tutti gli altri vengono ignorati.  
  
- L'ordine dei CURSORi REF in **OracleDataReader** dipende dall'ordine dei parametri in **OracleParameterCollection**. La proprietà <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> viene ignorata.  
  
- Il tipo di dati della **tabella** PL/SQL non è supportato. I REF CURSOR, tuttavia, sono più efficaci. Se è necessario utilizzare un tipo di dati **Table** , utilizzare il OLE DB .NET provider di dati con MSDAORA.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Esempi di REF CURSOR](ref-cursor-examples.md)  
 Vengono presentati tre esempi che illustrano l'uso del tipo di dati REF CURSOR.  
  
 [Parametri REF CURSOR in un oggetto OracleDataReader](ref-cursor-parameters-in-an-oracledatareader.md)  
 Viene illustrato come eseguire un stored procedure PL/SQL che restituisce un parametro REF CURSOR e legge il valore come **OracleDataReader**.  
  
 [Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader](retrieving-data-from-multiple-ref-cursors.md)  
 Viene illustrato come eseguire un stored procedure PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando **OracleDataReader**.  
  
 [Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR](filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Viene illustrato come eseguire una stored procedure PL/SQL che restituisce due parametri REF CURSOR e la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](oracle-and-adonet.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
