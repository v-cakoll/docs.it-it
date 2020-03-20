---
title: Memorizzazione nella cache di piani di query (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 90b0c685-5ef2-461b-98b4-c3c0a2b253c7
ms.openlocfilehash: a0e84f40aed2cff146e4e203cca73a9110de0e2f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149986"
---
# <a name="query-plan-caching-entity-sql"></a>Memorizzazione nella cache di piani di query (Entity SQL)
Ogni volta che viene fatto un tentativo di eseguire una query, la pipeline di query analizza il proprio piano di query per verificare se la query esatta è già stata compilata ed è disponibile. In caso affermativo, viene riutilizzato il piano memorizzato nella cache anziché compilarne un nuovo. Se non viene individuata una corrispondenza nella cache dei piani di query, la query viene compilata e memorizzata nella cache. Una query è identificata dal testo [!INCLUDE[esql](../../../../../../includes/esql-md.md)] e dalla raccolta di parametri (nomi e tipi). In tutti i confronti di testo viene fatta distinzione tra maiuscole e minuscole.  
  
## <a name="configuration"></a>Configurazione  
 La memorizzazione nella cache del piano di query può essere configurata tramite <xref:System.Data.EntityClient.EntityCommand>.  
  
 Per abilitare o disabilitare la memorizzazione nella cache del piano di query tramite <xref:System.Data.EntityClient.EntityCommand.EnablePlanCaching%2A?displayProperty=nameWithType>, impostare questa proprietà su `true` o su `false`. Disattivando la memorizzazione nella cache del piano di query per singole query dinamiche che non verranno probabilmente usate più di una volta è possibile migliorare le prestazioni.  
  
 È possibile abilitare la memorizzazione nella cache del piano di query tramite <xref:System.Data.Objects.ObjectQuery.EnablePlanCaching%2A>.  
  
## <a name="recommended-practice"></a>Procedure consigliate  
 In genere, è consigliabile evitare le query dinamiche. L'esempio di query dinamica seguente è vulnerabile ad attacchi SQL injection, in quanto usa direttamente l'input dell'utente senza alcuna convalida.  
  
 ```csharp
 var query = "SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp WHERE sp.EmployeeID = " + employeeTextBox.Text;  
 ```

 Se si usano query dinamicamente generate, disabilitare la memorizzazione nella cache del piano di query per evitare un consumo di memoria non necessario per le voci della cache con poche probabilità di riutilizzo.  
  
 La memorizzazione nella cache del piano di query per le query statiche e con parametri può offrire vantaggi a livello di prestazioni. Di seguito è riportato un esempio di query statica:  
  
```csharp
var query = "SELECT sp.SalesYTD FROM AdventureWorksEntities.SalesPerson as sp";  
```  
  
 Per garantire una corretta individuazione della corrispondenza delle query con la cache dei piani di query, è necessario che le query siano conformi ai requisiti seguenti:  
  
- Il testo delle query deve essere un modello costante, preferibilmente una risorsa o una stringa costante.  
  
- È necessario usare <xref:System.Data.EntityClient.EntityParameter> o <xref:System.Data.Objects.ObjectParameter> in ogni situazione in cui deve essere passato un valore fornito dall'utente.  
  
 È necessario evitare i modelli di query seguenti, che usano inutilmente slot nella cache dei piani di query:  
  
- Conversione di caratteri maiuscoli in minuscoli o viceversa nel testo.  
  
- Modifiche degli spazi vuoti.  
  
- Modifiche dei valori letterali.  
  
- Modifiche del testo nei commenti.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su Entity SQL](entity-sql-overview.md)
