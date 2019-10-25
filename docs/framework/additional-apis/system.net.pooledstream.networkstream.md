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
# <a name="pooledstreamnetworkstream-property"></a><span data-ttu-id="6e2c6-102">Proprietà PooledStream. NetworkStream</span><span class="sxs-lookup"><span data-stu-id="6e2c6-102">PooledStream.NetworkStream Property</span></span>

<span data-ttu-id="6e2c6-103">Ottiene o imposta il flusso di rete per il socket `PooledStream`.</span><span class="sxs-lookup"><span data-stu-id="6e2c6-103">Gets or sets the network stream for the `PooledStream` socket.</span></span>

## <a name="syntax"></a><span data-ttu-id="6e2c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6e2c6-104">Syntax</span></span>

```csharp
internal NetworkStream NetworkStream { get; set; }
```

## <a name="property-value"></a><span data-ttu-id="6e2c6-105">Valore proprietà</span><span class="sxs-lookup"><span data-stu-id="6e2c6-105">Property value</span></span>

<xref:System.Net.Sockets.NetworkStream>  
<span data-ttu-id="6e2c6-106">Il flusso di rete per il socket `PooledStream`.</span><span class="sxs-lookup"><span data-stu-id="6e2c6-106">The network stream for the `PooledStream` socket.</span></span>

## <a name="remarks"></a><span data-ttu-id="6e2c6-107">Note</span><span class="sxs-lookup"><span data-stu-id="6e2c6-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="6e2c6-108">Il `PooledStream.NetworkStream` proprietà è interno e non deve essere usato direttamente nel codice.</span><span class="sxs-lookup"><span data-stu-id="6e2c6-108">The `PooledStream.NetworkStream` property is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="6e2c6-109">Microsoft non supporta l'utilizzo di questa proprietà in un'applicazione di produzione in qualsiasi circostanza.</span><span class="sxs-lookup"><span data-stu-id="6e2c6-109">Microsoft does not support the use of this property in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e2c6-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6e2c6-110">Requirements</span></span>

<span data-ttu-id="6e2c6-111">**Spazio dei nomi:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="6e2c6-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="6e2c6-112">**Assembly:** System (in System. dll)</span><span class="sxs-lookup"><span data-stu-id="6e2c6-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="6e2c6-113">**Versioni .NET Framework:** Disponibile a partire da 2,0.</span><span class="sxs-lookup"><span data-stu-id="6e2c6-113">**.NET Framework versions:** Available since 2.0.</span></span>
