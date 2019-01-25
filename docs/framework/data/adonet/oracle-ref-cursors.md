---
title: Oggetti REF CURSOR Oracle
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: 4dd0a78fafe63197987938021195723e3eed0885
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740996"
---
# <a name="oracle-ref-cursors"></a>Oggetti REF CURSOR Oracle
Il Provider di dati .NET Framework per Oracle supporta Oracle **REF CURSOR** tipo di dati. Quando si usa il provider di dati per usare il tipo di dati REF CURSOR Oracle, considerare i seguenti comportamenti.  
  
> [!NOTE]
>  Alcuni comportamenti si differenziano da quelli del provider Microsoft OLE DB per Oracle (MSDAORA).  
  
-   Per motivi di prestazioni, il Provider di dati per Oracle non associa automaticamente **REF CURSOR** i tipi di dati, come MSDAORA, a meno che non specificati in modo esplicito.  
  
-   Il provider di dati non supporta alcuna sequenza di escape ODBC, incluso il carattere di escape {resultset} usato per specificare i parametri REF CURSOR.  
  
-   Per eseguire una stored procedure che restituisce i REF CURSOR, è necessario definire i parametri in di <xref:System.Data.OracleClient.OracleParameterCollection> con un <xref:System.Data.OracleClient.OracleType> dei **cursore** e un <xref:System.Data.OracleClient.OracleParameter.Direction%2A> di **Output**. Il provider di dati supporta l'associazione dei REF CURSOR solo come parametri di output. I REF CURSOR come parametri di input non sono supportati.  
  
-   Il recupero di un tipo <xref:System.Data.OracleClient.OracleDataReader> dal valore del parametro non è supportato. I valori sono di tipo <xref:System.DBNull> dopo l'esecuzione del comando.  
  
-   Gli unici **CommandBehavior** valore dell'enumerazione che funziona con oggetti REF CURSOR (ad esempio, quando si chiama <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) viene **CloseConnection**; tutti gli altri vengono ignorati.  
  
-   L'ordine dei REF CURSOR nel **OracleDataReader** dipende dall'ordine i parametri nel **OracleParameterCollection**. La proprietà <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A> viene ignorata.  
  
-   Il codice PL/SQL **tabella** tipo di dati non è supportato. I REF CURSOR, tuttavia, sono più efficaci. Se è necessario usare una **tabella** tipo di dati, usare il Provider di dati OLE DB .NET con MSDAORA.  
  
## <a name="in-this-section"></a>In questa sezione  
 [Esempi di REF CURSOR](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Vengono presentati tre esempi che illustrano l'uso del tipo di dati REF CURSOR.  
  
 [Parametri REF CURSOR in un oggetto OracleDataReader](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Viene illustrato come eseguire una procedura stored PL/SQL che restituisce un parametro REF CURSOR e legge il valore come un **OracleDataReader**.  
  
 [Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Viene illustrato come eseguire una procedura stored PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando un **OracleDataReader**.  
  
 [Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Viene illustrato come eseguire una stored procedure PL/SQL che restituisce due parametri REF CURSOR e la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.  
  
## <a name="see-also"></a>Vedere anche
- [Oracle e ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
