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
ms.openlocfilehash: 2cc712e6560fc58af7526428ba40c424be388eee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746661"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="48709-102">Metodo IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="48709-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="48709-103">Richieste per popolare il buffer specificato con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="48709-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="48709-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48709-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a><span data-ttu-id="48709-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="48709-105">Parameters</span></span>

<span data-ttu-id="48709-106">`reqCode` [in] Tipo per l'invio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="48709-106">`reqCode` [in] Request type to be sent.</span></span>

<span data-ttu-id="48709-107">`inBufferSize` [in] dimensione del buffer di input che deve essere passato.</span><span class="sxs-lookup"><span data-stu-id="48709-107">`inBufferSize` [in] size of the input buffer to be passed in.</span></span>

<span data-ttu-id="48709-108">`inBuffer` [in, size_is(inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="48709-108">`inBuffer` [in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

<span data-ttu-id="48709-109">`outBufferSize` [in] Dimensioni del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="48709-109">`outBufferSize` [in] Size of the output buffer.</span></span>

<span data-ttu-id="48709-110">`outBuffer` [out, size_is(outBufferSize)] Puntatore del buffer usato per archiviare la risposta alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="48709-110">`outBuffer` [out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="48709-111">Note</span><span class="sxs-lookup"><span data-stu-id="48709-111">Remarks</span></span>

<span data-ttu-id="48709-112">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 36o slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="48709-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="48709-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48709-113">Requirements</span></span>

<span data-ttu-id="48709-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48709-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="48709-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="48709-115">**Header:** None</span></span>   
<span data-ttu-id="48709-116">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="48709-116">**Library:** None</span></span>  
<span data-ttu-id="48709-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="48709-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="48709-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48709-118">See also</span></span>
- [<span data-ttu-id="48709-119">Debug</span><span class="sxs-lookup"><span data-stu-id="48709-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="48709-120">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="48709-120">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)
