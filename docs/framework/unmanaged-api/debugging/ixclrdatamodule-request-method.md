---
title: 'Metodo IXCLRDataModule:: Request'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 44ee4fc7fc2368b65f6f2fffe6ac239beddc6293
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395274"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="df59f-102">Metodo IXCLRDataModule:: Request</span><span class="sxs-lookup"><span data-stu-id="df59f-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="df59f-103">Richieste per popolare il buffer fornito con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="df59f-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="df59f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df59f-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="df59f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="df59f-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="df59f-106">in Tipo di richiesta da inviare.</span><span class="sxs-lookup"><span data-stu-id="df59f-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="df59f-107">[in] dimensione del buffer di input da passare.</span><span class="sxs-lookup"><span data-stu-id="df59f-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="df59f-108">[in, size_is (inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="df59f-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="df59f-109">in Dimensioni del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="df59f-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="df59f-110">[out, size_is (outBufferSize)] Puntatore del buffer a usato per archiviare la risposta della richiesta.</span><span class="sxs-lookup"><span data-stu-id="df59f-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="df59f-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="df59f-111">Remarks</span></span>

<span data-ttu-id="df59f-112">Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 37a della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="df59f-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="df59f-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="df59f-113">Requirements</span></span>

<span data-ttu-id="df59f-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df59f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="df59f-115">**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="df59f-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="df59f-116">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="df59f-116">See also</span></span>

- [<span data-ttu-id="df59f-117">Debug</span><span class="sxs-lookup"><span data-stu-id="df59f-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="df59f-118">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="df59f-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
