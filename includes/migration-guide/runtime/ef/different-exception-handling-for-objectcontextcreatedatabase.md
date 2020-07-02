---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620304"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Diversa gestione delle eccezioni per i metodi ObjectContext.CreateDatabase e DbProviderServices.CreateDatabase

#### <a name="details"></a>Dettagli

A partire da .NET Framework 4.5, se la creazione del database non riesce, i metodi <code>CreateDatabase</code> tentano di eliminare il database vuoto. Se tale operazione ha esito positivo, verrà propagata l'eccezione <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> originale, al posto dell'eccezione <xref:System.InvalidOperationException?displayProperty=fullName> che viene sempre generata in .NET Framework 4.0.

#### <a name="suggestion"></a>Suggerimento

Quando si rileva un oggetto <xref:System.InvalidOperationException?displayProperty=fullName> durante l'esecuzione di <xref:System.Data.Objects.ObjectContext.CreateDatabase> o <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, ora deve essere rilevato anche SQLExceptions.

| Nome    | Valore       |
|:--------|:------------|
| Scope   |Minorenne|
|Version|4.5|
|Type|Runtime

#### <a name="affected-apis"></a>API interessate

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
