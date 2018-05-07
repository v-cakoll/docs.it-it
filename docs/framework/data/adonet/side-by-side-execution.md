---
title: Esecuzione side-by-side in ADO.NET
ms.date: 03/30/2017
ms.assetid: 9f9ba96d-9f89-4f65-bb2f-6860879f4393
ms.openlocfilehash: 793a48966192326e2a1273c6ea4b9c9eddda76fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="side-by-side-execution-in-adonet"></a>Esecuzione side-by-side in ADO.NET
In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] il supporto dell'esecuzione side-by-side indica la possibilità di eseguire un'applicazione in un computer in cui sono installate più versioni di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] usando esclusivamente la versione per la quale è stata compilata l'applicazione stessa. Per informazioni dettagliate sulla configurazione di esecuzione side-by-side, vedere [esecuzione Side-by-Side](../../../../docs/framework/deployment/side-by-side-execution.md).  
  
 Un'applicazione compilata usando una singola versione di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] può essere eseguita in una versione diversa di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Si consiglia tuttavia di compilare versioni dell'applicazione diverse per ciascuna versione di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] installata e di eseguirle separatamente. Indipendentemente dallo scenario è necessario conoscere le modifiche apportate ad [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] tra una versione e l'altra per valutarne le possibili conseguenze sulla compatibilità dell'applicazione con le versioni successive o precedenti.  
  
## <a name="forward-compatibility-and-backward-compatibility"></a>Compatibilità con le versioni successive e precedenti  
 Per compatibilità con le versioni successive si intende la possibilità di compilare un'applicazione per una versione precedente di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], potendola comunque eseguire correttamente anche in versioni più recenti di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]. Il codice [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] scritto per la versione 1.1 di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] è ad esempio compatibile con le versioni successive.  
  
 Per compatibilità con le versioni precedenti si intende la possibilità di compilare un'applicazione per una versione successiva di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], ma di poterla eseguire correttamente anche in versioni precedenti di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] senza alcuna perdita di funzionalità. Tuttavia, ciò non vale per le funzionalità introdotte nella nuove versioni di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="the-net-framework-data-provider-for-odbc"></a>Provider di dati .NET Framework per ODBC  
 Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per ODBC (<xref:System.Data.Odbc>) viene fornito con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] a partire dalla versione 1.1. È disponibile per il provider di dati ODBC [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] sviluppatori versione 1.0 scaricare dal [Data Access and Storage Developer Center](http://go.microsoft.com/fwlink/?linkid=4173). Lo spazio dei nomi per il download [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Provider di dati per ODBC è **ODBC**.  
  
 Se si dispone di un'applicazione sviluppata per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0 che utilizza il provider di dati ODBC per connettersi all'origine dati e si desidera eseguire tale applicazione sul [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.1 o versione successiva, è necessario aggiornare lo spazio dei nomi per ODBC provider di dati di **ODBC**. Ricompilare quindi l'applicazione per la versione successiva di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Se si dispone di un'applicazione sviluppata per [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 2.0 o successiva che effettua la connessione a un'origine dati usando il provider di dati ODBC e si desidera eseguire tale applicazione in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0, è necessario scaricare il provider di dati ODBC e installarlo nel computer che esegue [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0. È quindi necessario modificare lo spazio dei nomi per il provider di dati ODBC in **ODBC**e ricompilare l'applicazione per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0.  
  
## <a name="the-net-framework-data-provider-for-oracle"></a>Provider di dati .NET Framework per Oracle  
 Il provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] per Oracle (<xref:System.Data.OracleClient>) viene fornito con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] a partire dalla versione 1.1. Il provider di dati è disponibile per [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] sviluppatori versione 1.0 scaricare dal [Data Access and Storage Developer Center](http://go.microsoft.com/fwlink/?linkid=4173).  
  
 Se si dispone di un'applicazione sviluppata per il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 2.0 o versione successiva e che utilizza il provider di dati per connettersi all'origine dati e si desidera eseguire tale applicazione nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0, è necessario scaricare il provider di dati e installarlo nel < C4 > [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]  versione 1.0.  
  
## <a name="code-access-security"></a>Sicurezza per l'accesso al codice  
 I provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] usati con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0 (<xref:System.Data.SqlClient> e <xref:System.Data.OleDb>) devono essere eseguiti con autorizzazioni FullTrust. Qualsiasi tentativo di usare il [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provider di dati di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0 in un'area con meno di autorizzazione FullTrust determina un <xref:System.Security.SecurityException>.  
  
 A partire da [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 2.0, tutti i provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] possono tuttavia essere usati in aree parzialmente attendibili. Inoltre, con [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.1 ai provider di dati [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] è stata aggiunta una nuova funzionalità di sicurezza, che consente di definire quali stringhe di connessione possano essere usate in una determinata area di sicurezza. È anche possibile disabilitare l'uso di password vuote per una particolare area di sicurezza. Per altre informazioni, vedere [Code Access Security and ADO.NET](../../../../docs/framework/data/adonet/code-access-security.md).  
  
 Poiché ogni installazione di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dispone di un file Security.config separato, le impostazioni di sicurezza non generano problemi di compatibilità. Tuttavia, se l'applicazione dipende dalle funzionalità di sicurezza aggiuntive di [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] incluse in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 e versioni successive, non sarà possibile distribuirla in un computer che usa la versione 1.0.  
  
## <a name="sqlcommand-execution"></a>Esecuzione di SqlCommand  
 A partire da [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.1 è cambiata la modalità di esecuzione di comandi sull'origine dati con il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
 Nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> eseguiva tutti i comandi nel contesto del **sp_executesql** stored procedure. Di conseguenza, tutti i comandi che incidevano sullo stato della connessione (ad esempio SET NOCOUNT ON) si applicavano solo all'esecuzione del comando corrente. Lo stato della connessione non veniva modificato per i comandi eseguiti successivamente fintanto che la connessione era aperta.  
  
 Nel [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 e versioni successive, <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> esegue un comando solo nel contesto del **sp_executesql** stored procedure, se il comando contiene parametri, che fornisce un miglioramento delle prestazioni. Di conseguenza, se un comando che incide sullo stato della connessione viene incluso in un comando senza parametri, le modifiche apportate allo stato della connessione permarranno anche per tutti i comandi eseguiti successivamente, fino alla chiusura della connessione.  
  
 Si consideri l'esecuzione del gruppo di comandi seguente in una chiamata al metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A>.  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
```  
  
 In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 1.1 e versioni successive NOCOUNT rimane impostato su ON per tutti i comandi eseguiti successivamente finché la connessione è aperta. In [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] versione 1.0 NOCOUNT è impostato su ON solo durante l'esecuzione del comando corrente.  
  
 Tale modifica può incidere sulla compatibilità di un'applicazione con le versioni successive e precedenti, se l'applicazione dipende dal comportamento del metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteReader%2A> di una delle versioni di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
 Per le applicazioni che possono essere eseguite sia sulle versioni successive che sulle versioni precedenti di [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], è possibile scrivere il codice in modo tale che il comportamento resti invariato indipendentemente dalla versione in cui viene eseguita l'applicazione. Per assicurarsi che un comando modifichi lo stato della connessione per tutti i comandi successivi, si consiglia di eseguire il comando tramite il metodo <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A>. Per assicurarsi che un comando non modifichi lo stato della connessione per tutti i comandi successivi, si consiglia di includervi i comandi che ripristinano lo stato della connessione. Ad esempio:  
  
```  
SET NOCOUNT ON;  
SELECT * FROM dbo.Customers;  
SET NOCOUNT OFF;  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di ADO.NET](../../../../docs/framework/data/adonet/ado-net-overview.md)  
 [Recupero e modifica di dati in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Provider gestiti ADO.NET e Centro per sviluppatori di set di dati](http://go.microsoft.com/fwlink/?LinkId=217917)
