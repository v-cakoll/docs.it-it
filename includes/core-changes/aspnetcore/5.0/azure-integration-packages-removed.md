---
ms.openlocfilehash: d8506893f5b3eefa6f46dc9f773e43b125ee5210
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291652"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a>Azure: rimossi i pacchetti di integrazione di Azure con prefisso MicrosoftAzure: Microsoft-prefixed Azure integration packages removed

I `Microsoft.*` pacchetti seguenti che forniscono l'integrazione tra ASP.NET Core e gli SDK di Azure non sono inclusi in ASP.NET Core 5.0:The following packages that provide integration between ASP.NET Core and Azure SDKs aren't included in ASP.NET Core 5.0:

* [Microsoft.Extensions.Configuration.AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), che integra [l'insieme](/azure/key-vault/) di credenziali delle chiavi di Azure nel sistema di [configurazione.](/aspnet/core/fundamentals/configuration/)
* [Microsoft.AspNetCore.DataProtection.AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), che integra l'insieme di credenziali delle chiavi di Azure nel [sistema di protezione dei dati di ASP.NET core](/aspnet/core/security/data-protection/introduction).
* [Microsoft.AspNetCore.DataProtection.AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), che integra [Archiviazione BLOB](/azure/storage/blobs/) di Azure nel sistema di protezione dei dati di ASP.NET core.

Per una discussione su questo problema, vedere [dotnet/aspnetcore-19570](https://github.com/dotnet/aspnetcore/issues/19570).

#### <a name="version-introduced"></a>Versione introdotta

5.0 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

I `Microsoft.*` pacchetti sono stati integrati con le API di configurazione e protezione dei dati.

#### <a name="new-behavior"></a>Nuovo comportamento

I `Azure.*` nuovi pacchetti integrano i servizi di Azure con le API di configurazione e protezione dei dati.

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica è `Microsoft.*` stata apportata perché i pacchetti erano:

* Utilizzo di versioni obsolete di Azure SDK. Semplici aggiornamenti non erano possibili perché le nuove versioni di Azure SDK includevano modifiche di rilievo.
* Legato alla pianificazione del rilascio di .NET Core. Il trasferimento della proprietà dei pacchetti al team di Azure SDK abilita gli aggiornamenti dei pacchetti durante l'aggiornamento di Azure SDK.

#### <a name="recommended-action"></a>Azione consigliata

In ASP.NET Core 2.1 o progetti `Microsoft.*` successivi, `Azure.*` sostituire il vecchio con i nuovi pacchetti.

| Vecchio | Nuovo |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [Azure.AspNetCore.DataProtection.Keys](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [Azure.AspNetCore.DataProtection.Blobs](https://www.nuget.org/packages/Azure.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [Azure.Extensions.Configuration.Secrets](https://www.nuget.org/packages/Azure.Extensions.Configuration.Secrets) |

I nuovi pacchetti usano una nuova versione di Azure SDK che include modifiche di rilievo. I modelli di utilizzo generale sono invariati. Alcuni overload e opzioni possono differire per adattarsi alle modifiche nelle API di Azure SDK sottostanti.

I vecchi pacchetti:

* Essere supportato dal team di ASP.NET Core per la durata di .NET Core 2.1 e 3.1.
* Non essere incluso in .NET 5.

Quando si aggiorna il progetto a `Azure.*` .NET 5, eseguire la transizione ai pacchetti per mantenere il supporto.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

- <xref:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.Extensions.Configuration.AzureKeyVaultConfigurationExtensions.AddAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.ProtectKeysWithAzureKeyVault`
- `Overload:Microsoft.AspNetCore.DataProtection.AzureDataProtectionBuilderExtensions.PersistKeysToAzureBlobStorage`

-->
