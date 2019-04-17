---
title: Metodo IXCLRDataModule::Request
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
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610600"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="bdb44-102">Metodo IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="bdb44-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="bdb44-103">Richieste per popolare il buffer specificato con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="bdb44-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="bdb44-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdb44-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="bdb44-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bdb44-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="bdb44-106">[in] Tipo per l'invio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="bdb44-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="bdb44-107">[in] dimensione del buffer di input che deve essere passato.</span><span class="sxs-lookup"><span data-stu-id="bdb44-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="bdb44-108">[in, size_is(inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="bdb44-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="bdb44-109">[in] Dimensioni del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="bdb44-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="bdb44-110">[out, size_is(outBufferSize)] Puntatore del buffer usato per archiviare la risposta alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="bdb44-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="bdb44-111">Note</span><span class="sxs-lookup"><span data-stu-id="bdb44-111">Remarks</span></span>

<span data-ttu-id="bdb44-112">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 36o slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="bdb44-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="bdb44-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdb44-113">Requirements</span></span>

<span data-ttu-id="bdb44-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdb44-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="bdb44-115">**Intestazione:** Nessuno **libreria:** Nessuno **versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="bdb44-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bdb44-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdb44-116">See also</span></span>

- [<span data-ttu-id="bdb44-117">Debug</span><span class="sxs-lookup"><span data-stu-id="bdb44-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="bdb44-118">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="bdb44-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)