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
ms.openlocfilehash: 3c18fc5c947cbb89fc4e9aed60d3cedcbe22d749
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420812"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="636f9-102">Metodo IXCLRDataModule:: Request</span><span class="sxs-lookup"><span data-stu-id="636f9-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="636f9-103">Richieste per popolare il buffer fornito con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="636f9-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="636f9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="636f9-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="636f9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="636f9-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="636f9-106">in Tipo di richiesta da inviare.</span><span class="sxs-lookup"><span data-stu-id="636f9-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="636f9-107">[in] dimensione del buffer di input da passare.</span><span class="sxs-lookup"><span data-stu-id="636f9-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="636f9-108">[in, size_is (inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="636f9-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="636f9-109">in Dimensioni del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="636f9-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="636f9-110">[out, size_is (outBufferSize)] Puntatore del buffer a usato per archiviare la risposta della richiesta.</span><span class="sxs-lookup"><span data-stu-id="636f9-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="636f9-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="636f9-111">Remarks</span></span>

<span data-ttu-id="636f9-112">Il metodo fornito fa parte dell' `IXCLRDataModule` interfaccia e corrisponde allo slot 37a della tabella del metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="636f9-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 37th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="636f9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="636f9-113">Requirements</span></span>

<span data-ttu-id="636f9-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="636f9-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>
<span data-ttu-id="636f9-115">**Intestazione:** Nessuna **libreria:** nessuna **.NET Framework versioni:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="636f9-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="636f9-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="636f9-116">See also</span></span>

- [<span data-ttu-id="636f9-117">Debug</span><span class="sxs-lookup"><span data-stu-id="636f9-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="636f9-118">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="636f9-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
