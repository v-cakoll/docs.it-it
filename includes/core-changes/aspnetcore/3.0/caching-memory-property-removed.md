---
ms.openlocfilehash: 2c1362d6982206b14475f77700add0bae61da173
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901960"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Caching: la proprietà CompactOnMemoryPressure è stata rimossa

La versione di ASP.NET Core 3,0 ha rimosso le [API MemoryCacheOptions obsolete](https://github.com/dotnet/extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).

#### <a name="change-description"></a>Descrizione delle modifiche

Questa modifica è un completamento di [ASPNET/Caching # 221](https://github.com/aspnet/Caching/issues/221). Per informazioni, vedere [DotNet/Extensions # 1062](https://github.com/dotnet/extensions/issues/1062).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

Proprietà `MemoryCacheOptions.CompactOnMemoryPressure` disponibile.

#### <a name="new-behavior"></a>Nuovo comportamento

La proprietà `MemoryCacheOptions.CompactOnMemoryPressure` è stata rimossa.

#### <a name="reason-for-change"></a>Motivo della modifica

La compattazione automatica della cache ha causato problemi. Per evitare comportamenti imprevisti, la cache deve essere compattata solo quando è necessario.

#### <a name="recommended-action"></a>Azione consigliata

Per compattare la cache, abbreviata per `MemoryCache` e chiamare `Compact` quando necessario.

#### <a name="category"></a>Categoria

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
