---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901960"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Memorizzazione nella cache: proprietà CompactOnMemoryPressure rimossaCaching: CompactOnMemoryPressure property removed

La versione ASP.NET Core 3.0 ha rimosso le [API MemoryCacheOptions obsolete.](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18)

#### <a name="change-description"></a>Descrizione modifica:

Questa modifica è un follow-up di [aspnet/Caching-221](https://github.com/aspnet/Caching/issues/221). Per una discussione, vedere [dotnet/extensions.](https://github.com/dotnet/extensions/issues/1062)

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

`MemoryCacheOptions.CompactOnMemoryPressure`proprietà era disponibile.

#### <a name="new-behavior"></a>Nuovo comportamento

La `MemoryCacheOptions.CompactOnMemoryPressure` proprietà è stata rimossa.

#### <a name="reason-for-change"></a>Motivo della modifica

La compattazione automatica della cache ha causato problemi. Per evitare comportamenti imprevisti, la cache deve essere compattata solo quando necessario.

#### <a name="recommended-action"></a>Azione consigliata

Per compattare la cache, eseguire il downcast `MemoryCache` e chiamare `Compact` quando necessario.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
