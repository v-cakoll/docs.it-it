---
ms.openlocfilehash: 19ccdb634d4e53ea66c032502f2adb70423ab121
ms.sourcegitcommit: 3492dafceb5d4183b6b0d2f3bdf4a1abc4d5ed8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2020
ms.locfileid: "86416249"
---
### <a name="azure-microsoft-prefixed-azure-integration-packages-removed"></a>Azure: pacchetti di integrazione di Azure con prefisso Microsoft rimossi

I `Microsoft.*` pacchetti seguenti che forniscono l'integrazione tra ASP.NET Core e Azure SDK non sono inclusi nella ASP.NET Core 5,0:

* [Microsoft.Extensions.Configuration. AzureKeyVault](https://www.nuget.org/packages/Microsoft.Extensions.Configuration.AzureKeyVault/), che integra [Azure Key Vault](/azure/key-vault/) nel sistema di [configurazione](/aspnet/core/fundamentals/configuration/).
* [Microsoft. AspNetCore. dataprotection. AzureKeyVault](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureKeyVault/), che integra Azure Key Vault nel sistema di [protezione dei dati ASP.NET Core](/aspnet/core/security/data-protection/introduction).
* [Microsoft. AspNetCore. dataprotection. AzureStorage](https://www.nuget.org/packages/Microsoft.AspNetCore.DataProtection.AzureStorage/), che integra l' [archiviazione BLOB di Azure](/azure/storage/blobs/) nel sistema di protezione dei dati ASP.NET Core.

Per informazioni su questo problema, vedere [DotNet/aspnetcore # 19570](https://github.com/dotnet/aspnetcore/issues/19570).

#### <a name="version-introduced"></a>Versione introdotta

5,0 Anteprima 1

#### <a name="old-behavior"></a>Comportamento precedente

I `Microsoft.*` pacchetti integrano i servizi di Azure con le API di configurazione e protezione dei dati.

#### <a name="new-behavior"></a>Nuovo comportamento

`Azure.*`I nuovi pacchetti integrano i servizi di Azure con le API di configurazione e protezione dei dati.

#### <a name="reason-for-change"></a>Motivo della modifica

La modifica è stata apportata perché i `Microsoft.*` pacchetti sono:

* Uso di versioni obsolete di Azure SDK. Gli aggiornamenti semplici non erano possibili perché le nuove versioni di Azure SDK includevano modifiche di rilievo.
* Associato alla pianificazione delle versioni di .NET Core. Il trasferimento della proprietà dei pacchetti al team di Azure SDK Abilita gli aggiornamenti dei pacchetti durante l'aggiornamento di Azure SDK.

#### <a name="recommended-action"></a>Azione consigliata

Nei progetti ASP.NET Core 2,1 o versioni successive sostituire il vecchio `Microsoft.*` con i nuovi `Azure.*` pacchetti.

| Precedente | Nuovo |
|--|--|
| `Microsoft.AspNetCore.DataProtection.AzureKeyVault` | [Azure. Extensions. AspNetCore. dataprotection. Keys](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Keys) |
| `Microsoft.AspNetCore.DataProtection.AzureStorage` | [Azure. Extensions. AspNetCore. dataprotection. blob](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.DataProtection.Blobs) |
| `Microsoft.Extensions.Configuration.AzureKeyVault` | [Azure.Extensions.AspNetCore.Configuration. Segreti](https://www.nuget.org/packages/Azure.Extensions.AspNetCore.Configuration.Secrets) |

I nuovi pacchetti usano una nuova versione di Azure SDK che include modifiche di rilievo. I modelli di utilizzo generali sono rimasti invariati. Alcuni overload e opzioni possono essere diversi per adattarsi alle modifiche nelle API di Azure SDK sottostanti.

I pacchetti precedenti:

* Essere supportato dal team di ASP.NET Core per la durata di .NET Core 2,1 e 3,1.
* Non essere incluso in .NET 5.

Quando si aggiorna il progetto a .NET 5, passare ai `Azure.*` pacchetti per mantenere il supporto.

#### <a name="category"></a>Categoria

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
