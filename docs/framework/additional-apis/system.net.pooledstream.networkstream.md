---
title: Proprietà PooledStream. NetworkStream (System.Net)
ms.date: 10/21/2019
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.PooledStream.NetworkStream
- System.Net.PooledStream.get_NetworkStream
- System.Net.PooledStream.set_NetworkStream
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 541b8c94b30675c1286b48a2291c3bd3e4aeea0b
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2019
ms.locfileid: "72847178"
---
# <a name="pooledstreamnetworkstream-property"></a>Proprietà PooledStream. NetworkStream

Ottiene o imposta il flusso di rete per il socket `PooledStream`.

## <a name="syntax"></a>Sintassi

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a>Valore proprietà

<xref:System.Net.Sockets.NetworkStream>  
Il flusso di rete per il socket `PooledStream`.

## <a name="remarks"></a>Note

> [!WARNING]
> Il `PooledStream.NetworkStream` proprietà è interno e non deve essere usato direttamente nel codice.
>
> Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.

## <a name="requirements"></a>Requisiti

**Spazio dei nomi:** <xref:System.Net>

**Assembly:** System (in System. dll)

**Versioni .NET Framework:** Disponibile a partire da 2,0.
