---
title: Oggetti REF CURSOR Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 7c6b326b15a2af58da9206adf28070e57fec600c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963505"
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
 [Esempi di REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Vengono presentati tre esempi che illustrano l'uso del tipo di dati REF CURSOR.  
  
 [Parametri REF CURSOR in un oggetto OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Viene illustrato come eseguire un stored procedure PL/SQL che restituisce un parametro REF CURSOR e legge il valore come **OracleDataReader**.  
  
 [Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Viene illustrato come eseguire un stored procedure PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando **OracleDataReader**.  
  
 [Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Viene illustrato come eseguire una stored procedure PL/SQL che restituisce due parametri REF CURSOR e la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.  
  
## <a name="see-also"></a>Vedere anche

- [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
