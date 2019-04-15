---
ms.openlocfilehash: 33ad1c044001e0a8d09708cc7a1f06e05cb307de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235477"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Diversa gestione delle eccezioni per i metodi ObjectContext.CreateDatabase e DbProviderServices.CreateDatabase

|   |   |
|---|---|
|Dettagli|A partire da .NET Framework 4.5, se la creazione del database non riesce, i metodi <code>CreateDatabase</code> tentano di eliminare il database vuoto. Se tale operazione ha esito positivo, verrà propagata l'eccezione <xref:System.Data.SqlClient.SqlException?displayProperty=name> originale, al posto dell'eccezione <xref:System.InvalidOperationException?displayProperty=name> che viene sempre generata in .NET Framework 4.0.|
|Suggerimento|Quando si rileva un oggetto <xref:System.InvalidOperationException?displayProperty=name> durante l'esecuzione di <xref:System.Data.Objects.ObjectContext.CreateDatabase> o <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, ora deve essere rilevato anche SQLExceptions.|
|Ambito|Secondario|
|Versione|4.5|
|Tipo|Runtime|
|API interessate|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
