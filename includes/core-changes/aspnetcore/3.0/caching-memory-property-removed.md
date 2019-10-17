---
ms.openlocfilehash: 7d40324e6b0bc4afab9dd39b236f0909f360cc9b
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394137"
---
### <a name="caching-compactonmemorypressure-property-removed"></a>Caching: la proprietà CompactOnMemoryPressure è stata rimossa

La versione di ASP.NET Core 3,0 ha rimosso le [API MemoryCacheOptions obsolete](https://github.com/aspnet/Extensions/blob/dc5c593da7b72c82e6fe85abb91d03818f9b700c/src/Caching/Memory/src/MemoryCacheOptions.cs#L17-L18).

#### <a name="change-description"></a>Descrizione della modifica

Questa modifica è un completamento di [ASPNET/Caching # 221](https://github.com/aspnet/Caching/issues/221). Per informazioni, vedere [ASPNET/Extensions # 1062](https://github.com/aspnet/Extensions/issues/1062).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="old-behavior"></a>Comportamento precedente

la proprietà `MemoryCacheOptions.CompactOnMemoryPressure` era disponibile.

#### <a name="new-behavior"></a>Nuovo comportamento

La proprietà `MemoryCacheOptions.CompactOnMemoryPressure` è stata rimossa.

#### <a name="reason-for-change"></a>Motivo della modifica

La compattazione automatica della cache ha causato problemi. Per evitare comportamenti imprevisti, la cache deve essere compattata solo quando è necessario.

#### <a name="recommended-action"></a>Azione consigliata

Per compattare la cache, abbreviata in `MemoryCache` e chiamare `Compact` quando necessario.

#### <a name="category"></a>Category

ASP.NET Core

#### <a name="affected-apis"></a>API interessate

<xref:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.Extensions.Caching.Memory.MemoryCacheOptions.CompactOnMemoryPressure`

-->
