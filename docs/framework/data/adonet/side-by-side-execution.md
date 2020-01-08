---
title: Esecuzione side-by-side in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 0355f375de678b2a74f8fdf58e2c58cc0bdf10ee
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348000"
---
# <a name="side-by-side-execution-in-adonet"></a>Esecuzione side-by-side in ADO.NET
L'esecuzione affiancata nel .NET Framework è la possibilità di eseguire un'applicazione in un computer in cui sono installate più versioni del .NET Framework, usando esclusivamente la versione per la quale è stata compilata l'applicazione. Per informazioni dettagliate sulla configurazione dell'esecuzione side-by-Side, vedere [esecuzione side-by-side](../../deployment/side-by-side-execution.md).  
  
 Un'applicazione compilata utilizzando una versione del .NET Framework può essere eseguita in una versione diversa del .NET Framework. È tuttavia consigliabile compilare una versione dell'applicazione per ogni versione installata del .NET Framework ed eseguirle separatamente. In entrambi gli scenari è necessario tenere presenti le modifiche apportate in ADO.NET tra le versioni che possono influire sulla compatibilità con le versioni precedenti o sulla compatibilità con le versioni precedenti dell'applicazione.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Compatibilità con le versioni successive e precedenti  
 Per compatibilità con le versioni successive si intende che un'applicazione può essere compilata con una versione precedente del .NET Framework, ma verrà comunque eseguita correttamente in una versione successiva del .NET Framework. Il codice ADO.NET scritto per la versione di .NET Framework 1,1 è compatibile con le versioni successive.  
  
 Per compatibilità con le versioni precedenti si intende che un'applicazione viene compilata per una versione più recente del .NET Framework, ma continua a essere eseguita in versioni precedenti del .NET Framework senza alcuna perdita di funzionalità. Naturalmente, ciò non avviene per le funzionalità introdotte in una nuova versione del .NET Framework.  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Provider di dati .NET Framework per ODBC  
 A partire dalla versione 1,1, il .NET Framework provider di dati per ODBC (<xref:System.Data.Odbc>) è incluso nell'.NET Framework.
  
 Se si dispone di un'applicazione sviluppata per la versione .NET Framework 1,0 che utilizza il provider di dati ODBC per connettersi all'origine dati e si desidera eseguire tale applicazione nella .NET Framework versione 1,1 o successiva, è necessario aggiornare lo spazio dei nomi per il provider di dati ODBC a **System. Data. ODBC**. Sarà quindi necessario ricompilarlo per la versione più recente del .NET Framework.  
  
 Se si dispone di un'applicazione sviluppata per il .NET Framework versione 2,0 o successiva che utilizza il provider di dati ODBC per connettersi all'origine dati e si desidera eseguire tale applicazione nella .NET Framework versione 1,0, è necessario scaricare il provider di dati ODBC e installarlo. nel sistema .NET Framework versione 1,0. È quindi necessario modificare lo spazio dei nomi per il provider di dati ODBC in **Microsoft. Data. ODBC**e ricompilare l'applicazione per la versione di .NET Framework 1,0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Provider di dati .NET Framework per Oracle  
 A partire dalla versione 1,1, il .NET Framework provider di dati per Oracle (<xref:System.Data.OracleClient>) è incluso nell'.NET Framework.
  
 Se si dispone di un'applicazione sviluppata per il .NET Framework versione 2,0 o successiva che utilizza il provider di dati per connettersi all'origine dati e si desidera eseguire tale applicazione nella .NET Framework versione 1,0, è necessario scaricare il provider di dati e installarlo nel. NE T Framework versione 1,0.  
  
## <a name="code-access-security"></a>Sicurezza per l'accesso al codice  
 Per l'esecuzione con autorizzazione FullTrust sono necessari i provider di dati .NET Framework nella .NET Framework versione 1,0 (<xref:System.Data.SqlClient>, <xref:System.Data.OleDb>). Qualsiasi tentativo di usare i provider di dati .NET Framework k dalla versione .NET Framework 1,0 in una zona con autorizzazioni minori di FullTrust causa un <xref:System.Security.SecurityException>.  
  
 Tuttavia, a partire da .NET Framework versione 2,0, tutti i provider di dati .NET Framework possono essere utilizzati in zone parzialmente attendibili. Inoltre, è stata aggiunta una nuova funzionalità di sicurezza ai provider di dati .NET Framework nella .NET Framework versione 1,1. che consente di definire quali stringhe di connessione possano essere usate in una determinata area di sicurezza. È anche possibile disabilitare l'uso di password vuote per una particolare area di sicurezza. Per altre informazioni, vedere [Code Access Security and ADO.NET](code-access-security.md).  
  
 Poiché ogni installazione del .NET Framework dispone di un file Security. config separato, non ci sono problemi di compatibilità con le impostazioni di sicurezza. Tuttavia, se l'applicazione dipende dalle funzionalità di sicurezza aggiuntive di ADO.NET incluse in .NET Framework versione 1,1 e successive, non sarà possibile distribuirla a un sistema di versione 1,0.  
  
## <a name="sqlcommand-execution"></a>Esecuzione di SqlCommand  
 A partire dalla versione .NET Framework 1,1, il modo in cui <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> esegue i comandi nell'origine dati è stato modificato.  
  
 Nel .NET Framework versione 1,0 <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> eseguito tutti i comandi nel contesto del stored procedure **sp_executesql** . Di conseguenza, tutti i comandi che incidevano sullo stato della connessione (ad esempio SET NOCOUNT ON) si applicavano solo all'esecuzione del comando corrente. Lo stato della connessione non veniva modificato per i comandi eseguiti successivamente fintanto che la connessione era aperta.  
  
 Nella versione .NET Framework 1,1 e versioni successive <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> esegue un comando solo nel contesto del **sp_executesql** stored procedure se il comando contiene parametri, che offre un vantaggio in relazione alle prestazioni. Di conseguenza, se un comando che incide sullo stato della connessione viene incluso in un comando senza parametri, le modifiche apportate allo stato della connessione permarranno anche per tutti i comandi eseguiti successivamente, fino alla chiusura della connessione.  
  
 Si consideri l'esecuzione del gruppo di comandi seguente in una chiamata al metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 In .NET Framework versione 1,1 e successive, NOCOUNT rimarrà attivo per tutti i comandi successivi eseguiti mentre la connessione è aperta. Nella versione .NET Framework 1,0, NOCOUNT è solo ON per l'esecuzione del comando corrente.  
  
 Questa modifica può influire sia sulla compatibilità diretta che sulla compatibilità con le versioni precedenti dell'applicazione se si dipende dal comportamento di <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> per entrambe le versioni del .NET Framework.  
  
 Per le applicazioni eseguite in versioni precedenti e successive del .NET Framework, è possibile scrivere il codice per assicurarsi che il comportamento sia lo stesso indipendentemente dalla versione in esecuzione. Per assicurarsi che un comando modifichi lo stato della connessione per tutti i comandi successivi, si consiglia di eseguire il comando tramite il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Per assicurarsi che un comando non modifichi lo stato della connessione per tutti i comandi successivi, si consiglia di includervi i comandi che ripristinano lo stato della connessione. Ad esempio:  
  
```sql
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di ADO.NET](ado-net-overview.md)
- [Recupero e modifica di dati in ADO.NET](retrieving-and-modifying-data.md)
