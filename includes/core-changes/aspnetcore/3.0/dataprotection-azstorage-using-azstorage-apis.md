---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901692"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>Protezione dei dati: DataProtection.AzureStorage usa le nuove API di Archiviazione di AzureData Protection: DataProtection.AzureStorage uses new Azure Storage APIs

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName>dipende dalle [librerie di Archiviazione di Azure](https://github.com/Azure/azure-storage-net). Queste librerie hanno rinominato i relativi assembly, pacchetti e spazi dei nomi. A partire da ASP.NET `Microsoft.AspNetCore.DataProtection.AzureStorage` Core 3.0, usa le nuove `Microsoft.Azure.Storage.`API e i pacchetti con prefisso.

Per domande sulle API di Archiviazione <https://github.com/Azure/azure-storage-net>di Azure, usare . Per una discussione su questo problema, vedere [dotnet/aspnetcore-8472](https://github.com/dotnet/aspnetcore/issues/8472).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il pacchetto fa `WindowsAzure.Storage` riferimento al pacchetto NuGet.

#### <a name="new-behavior"></a>Nuovo comportamento

Il pacchetto `Microsoft.Azure.Storage.Blob` fa riferimento al pacchetto NuGet.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica `Microsoft.AspNetCore.DataProtection.AzureStorage` consente di eseguire la migrazione ai pacchetti di Archiviazione di Azure consigliati.

#### <a name="recommended-action"></a>Azione consigliata

Se è ancora necessario usare le API di Archiviazione di Azure precedenti con ASP.NET Core 3.0, aggiungere una dipendenza diretta al pacchetto [WindowsAzure.Storage.If](https://www.nuget.org/packages/WindowsAzure.Storage/) you still need to use the older Azure Storage APIs with ASP.NET Core 3.0, add a direct dependency to the WindowsAzure.Storage package. Questo pacchetto può essere `Microsoft.Azure.Storage` installato insieme alle nuove API.

In molti casi, l'aggiornamento `using` comporta solo la modifica delle istruzioni per utilizzare i nuovi spazi dei nomi:In many cases, the upgrade only involves changing the statements to use the new namespaces:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuno

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
