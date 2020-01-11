---
ms.openlocfilehash: db70596552ffd699156e1b7a55cb1e944596f077
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901692"
---
### <a name="data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis"></a>Protezione dei dati: dataprotection. AzureStorage usa le nuove API di archiviazione di Azure

<xref:Microsoft.AspNetCore.DataProtection.AzureStorage?displayProperty=fullName> dipende dalle librerie di [archiviazione di Azure](https://github.com/Azure/azure-storage-net). Queste librerie hanno rinominato gli assembly, i pacchetti e gli spazi dei nomi. A partire da ASP.NET Core 3,0, `Microsoft.AspNetCore.DataProtection.AzureStorage` usa le nuove API e pacchetti con prefisso `Microsoft.Azure.Storage.`.

Per domande sulle API di archiviazione di Azure, usare <https://github.com/Azure/azure-storage-net>. Per informazioni su questo problema, vedere [DotNet/aspnetcore # 8472](https://github.com/dotnet/aspnetcore/issues/8472).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Il pacchetto fa riferimento al pacchetto NuGet `WindowsAzure.Storage`.

#### <a name="new-behavior"></a>Nuovo comportamento

Il pacchetto fa riferimento al pacchetto NuGet `Microsoft.Azure.Storage.Blob`.

#### <a name="reason-for-change"></a>Motivo della modifica

Questa modifica consente la migrazione di `Microsoft.AspNetCore.DataProtection.AzureStorage` ai pacchetti di archiviazione di Azure consigliati.

#### <a name="recommended-action"></a>Azione consigliata

Se è ancora necessario usare le API di archiviazione di Azure meno recenti con ASP.NET Core 3,0, aggiungere una dipendenza diretta al pacchetto [WindowsAzure. storage](https://www.nuget.org/packages/WindowsAzure.Storage/) . Questo pacchetto può essere installato insieme alle nuove API `Microsoft.Azure.Storage`.

In molti casi, l'aggiornamento comporta solo la modifica delle istruzioni `using` per l'uso dei nuovi spazi dei nomi:

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
+ using Microsoft.Azure.Storage;
+ using Microsoft.Azure.Storage.Blob;
```

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

nessuna

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
