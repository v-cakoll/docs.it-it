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
ms.openlocfilehash: a02a60668ae6caaad1940395822758331b93f550
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119795"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="8d7c4-102">Metodo IXCLRDataModule::Request</span><span class="sxs-lookup"><span data-stu-id="8d7c4-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="8d7c4-103">Richieste per popolare il buffer specificato con i dati del modulo.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="8d7c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8d7c4-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="8d7c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8d7c4-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="8d7c4-106">[in] Tipo per l'invio di richiesta.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="8d7c4-107">[in] dimensione del buffer di input che deve essere passato.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="8d7c4-108">[in, size_is(inBufferSize)] Puntatore del buffer per i dati non elaborati da inviare nella richiesta.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="8d7c4-109">[in] Dimensioni del buffer di output.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="8d7c4-110">[out, size_is(outBufferSize)] Puntatore del buffer usato per archiviare la risposta alla richiesta.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="8d7c4-111">Note</span><span class="sxs-lookup"><span data-stu-id="8d7c4-111">Remarks</span></span>

<span data-ttu-id="8d7c4-112">Il metodo specificato fa parte di `IXCLRDataModule` interfaccia e corrisponde al 36o slot della tabella di metodo virtuale.</span><span class="sxs-lookup"><span data-stu-id="8d7c4-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="8d7c4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8d7c4-113">Requirements</span></span>

<span data-ttu-id="8d7c4-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d7c4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="8d7c4-115">**Intestazione:** nessuno</span><span class="sxs-lookup"><span data-stu-id="8d7c4-115">**Header:** None</span></span>   
<span data-ttu-id="8d7c4-116">**Libreria:** nessuno</span><span class="sxs-lookup"><span data-stu-id="8d7c4-116">**Library:** None</span></span>  
**<span data-ttu-id="8d7c4-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8d7c4-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a><span data-ttu-id="8d7c4-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8d7c4-118">See also</span></span>

- [<span data-ttu-id="8d7c4-119">Debug</span><span class="sxs-lookup"><span data-stu-id="8d7c4-119">Debugging</span></span>](index.md)
- [<span data-ttu-id="8d7c4-120">Interfaccia IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="8d7c4-120">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)