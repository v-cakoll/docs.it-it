---
title: Esecuzione side-by-side in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 377af3c72b0a9a8eb26c8713d98f114803f08356
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583616"
---
# <a name="side-by-side-execution-in-adonet"></a>Esecuzione side-by-side in ADO.NET
Esecuzione side-by-side in .NET Framework è la possibilità di eseguire un'applicazione in un computer che dispone di più versioni di .NET Framework installata, usando esclusivamente la versione per il quale è stata compilata l'applicazione. Per informazioni dettagliate sulla configurazione di esecuzione side-by-side, vedere [esecuzione Side-by-Side](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Un'applicazione compilata usando una singola versione di .NET Framework è possibile eseguire in una versione diversa di .NET Framework. Tuttavia, è consigliabile che si compila una versione dell'applicazione per ogni versione installata di .NET Framework ed eseguire separatamente tali operazioni. Indipendentemente dallo scenario è necessario conoscere le modifiche apportate ad [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] tra una versione e l'altra per valutarne le possibili conseguenze sulla compatibilità dell'applicazione con le versioni successive o precedenti.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Compatibilità con le versioni successive e precedenti  
 Compatibilità con le versioni significa che un'applicazione può essere compilata con una versione precedente di .NET Framework, ma comunque eseguire correttamente anche in una versione successiva di .NET Framework. [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] il codice scritto per .NET Framework versione 1.1 è compatibile con le versioni con le versioni successive.  
  
 Compatibilità con le versioni precedenti si intende che un'applicazione viene compilata per una versione più recente di .NET Framework, ma continua a essere eseguito nelle versioni precedenti di .NET Framework senza alcuna perdita di funzionalità. Naturalmente, ciò non è il caso per le funzionalità introdotte in una nuova versione di .NET Framework.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Provider di dati .NET Framework per ODBC  
 A partire dalla versione 1.1, il Provider di dati .NET Framework per ODBC (<xref:System.Data.Odbc>) è incluso come parte di .NET Framework. Il provider di dati ODBC è disponibile per gli sviluppatori di .NET Framework versione 1.0 come download Web il [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173). Lo spazio dei nomi per il Provider di dati .NET Framework per ODBC scaricato è **ODBC**.  
  
 Se si dispone di un'applicazione sviluppata per .NET Framework versione 1.0 che utilizza il provider di dati ODBC per connettersi all'origine dati e si desidera eseguire tale applicazione su .NET Framework versione 1.1 o versione successiva, è necessario aggiornare lo spazio dei nomi per dat ODBC un provider **System.Data.Odbc**. È quindi necessario ricompilarla per la versione più recente di .NET Framework.  
  
 Se si dispone di un'applicazione sviluppata per .NET Framework versione 2.0 o versione successiva che utilizza il provider di dati ODBC per connettersi all'origine dati e si desidera eseguire tale applicazione su .NET Framework versione 1.0, è necessario scaricare il provider di dati ODBC e installarlo il sistema di .NET Framework versione 1.0. È quindi necessario modificare lo spazio dei nomi per il provider di dati ODBC di **ODBC**e ricompilare l'applicazione .NET Framework versione 1.0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Provider di dati .NET Framework per Oracle  
 A partire dalla versione 1.1, il Provider di dati .NET Framework per Oracle (<xref:System.Data.OracleClient>) è incluso come parte di .NET Framework. Il provider di dati è disponibile per gli sviluppatori di .NET Framework versione 1.0 come download Web il [Data Access and Storage Developer Center](https://go.microsoft.com/fwlink/?linkid=4173).  
  
 Se si dispone di un'applicazione sviluppata per .NET Framework versione 2.0 o versioni successive che usa il provider di dati per la connessione all'origine dati e si desidera eseguire tale applicazione su .NET Framework versione 1.0, è necessario scaricare il provider di dati e installarlo nel .NE Sistema di T Framework versione 1.0.  
  
## <a name="code-access-security"></a>Sicurezza per l'accesso al codice  
 I provider di dati .NET Framework in .NET Framework versione 1.0 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>) devono essere eseguiti con autorizzazioni FullTrust. Provare a usare i provider di dati k di .NET Framework da .NET Framework versione 1.0 in una zona con minore rispetto a FullTrust genera un <xref:System.Security.SecurityException>.  
  
 Tuttavia, a partire da .NET Framework versione 2.0, tutti i provider di dati .NET Framework è utilizzabile in aree parzialmente attendibili. Inoltre, una nuova funzionalità di sicurezza è stato aggiunto per i provider di dati .NET Framework in .NET Framework versione 1.1. che consente di definire quali stringhe di connessione possano essere usate in una determinata area di sicurezza. È anche possibile disabilitare l'uso di password vuote per una particolare area di sicurezza. Per altre informazioni, vedere [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Poiché ogni installazione di .NET Framework dispone di un file Security. config separato, vi sono problemi di compatibilità con le impostazioni di sicurezza. Tuttavia, se l'applicazione dipende dalle capacità aggiuntiva di sicurezza di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] incluso in .NET Framework versione 1.1 e versioni successive, non sarà possibile distribuirla in un sistema della versione 1.0.  
  
## <a name="sqlcommand-execution"></a>Esecuzione di SqlCommand  
 A partire da .NET Framework versione 1.1, di modo che <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> esegue i comandi i dati di origine è stata modificata.  
  
 In .NET Framework versione 1.0 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> eseguiva tutti i comandi nel contesto del **sp_executesql** stored procedure. Di conseguenza, tutti i comandi che incidevano sullo stato della connessione (ad esempio SET NOCOUNT ON) si applicavano solo all'esecuzione del comando corrente. Lo stato della connessione non veniva modificato per i comandi eseguiti successivamente fintanto che la connessione era aperta.  
  
 In .NET Framework 1.1 e versioni successive, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> esegue un comando nel contesto di solo le **sp_executesql** stored procedure se il comando contiene parametri, che offre un miglioramento delle prestazioni. Di conseguenza, se un comando che incide sullo stato della connessione viene incluso in un comando senza parametri, le modifiche apportate allo stato della connessione permarranno anche per tutti i comandi eseguiti successivamente, fino alla chiusura della connessione.  
  
 Si consideri l'esecuzione del gruppo di comandi seguente in una chiamata al metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 In .NET Framework 1.1 e versioni successive NOCOUNT rimarrà via per tutti i comandi eseguiti durante la connessione è aperta. In .NET Framework versione 1.0 NOCOUNT è impostata su ON solo per l'esecuzione del comando corrente.  
  
 Questa modifica può incidere sulla compatibilità avanti e indietro dell'applicazione se dipende dal comportamento di <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> per entrambe le versioni di .NET Framework.  
  
 Per le applicazioni eseguite in versioni sia precedenti sia successive di .NET Framework, è possibile scrivere il codice per assicurarsi che il comportamento è lo stesso indipendentemente dalla versione che si sta usando. Per assicurarsi che un comando modifichi lo stato della connessione per tutti i comandi successivi, si consiglia di eseguire il comando tramite il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Per assicurarsi che un comando non modifichi lo stato della connessione per tutti i comandi successivi, si consiglia di includervi i comandi che ripristinano lo stato della connessione. Ad esempio:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)
- [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](https://go.microsoft.com/fwlink/?LinkId=217917)
