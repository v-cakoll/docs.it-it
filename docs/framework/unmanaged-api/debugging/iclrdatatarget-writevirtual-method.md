---
title: Metodo ICLRDataTarget::WriteVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.WriteVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::WriteVirtual
helpviewer_keywords:
- ICLRDataTarget::WriteVirtual method [.NET Framework debugging]
- WriteVirtual method [.NET Framework debugging]
ms.assetid: d627e8b7-a605-40ac-b9bb-da9a3f1b66d9
topic_type:
- apiref
ms.openlocfilehash: bd2f67c2d7230d3873b4dc0df73ac1be778a0828
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179106"
---
# <a name="iclrdatatargetwritevirtual-method"></a><span data-ttu-id="3c711-102">Metodo ICLRDataTarget::WriteVirtual</span><span class="sxs-lookup"><span data-stu-id="3c711-102">ICLRDataTarget::WriteVirtual Method</span></span>
<span data-ttu-id="3c711-103">Scrive i dati dal buffer specificato all'indirizzo di memoria virtuale specificato.</span><span class="sxs-lookup"><span data-stu-id="3c711-103">Writes data from the specified buffer to the specified virtual memory address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c711-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3c711-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [in, size_is(bytesRequested)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesWritten  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c711-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3c711-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="3c711-106">[in] Un CLRDATA_ADDRESS in cui viene archiviato l'indirizzo di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="3c711-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="3c711-107">[in] Puntatore a un buffer in cui sono archiviati i dati da scrivere.</span><span class="sxs-lookup"><span data-stu-id="3c711-107">[in] A pointer to a buffer that stores the data to be written.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="3c711-108">[in] Numero di byte da scrivere.</span><span class="sxs-lookup"><span data-stu-id="3c711-108">[in] The number of bytes to be written.</span></span>  
  
 `bytesWritten`  
 <span data-ttu-id="3c711-109">[fuori] Puntatore al numero effettivo di byte scritti.</span><span class="sxs-lookup"><span data-stu-id="3c711-109">[out] A pointer to the actual number of bytes that were written.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c711-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3c711-110">Requirements</span></span>  
 <span data-ttu-id="3c711-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c711-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c711-112">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3c711-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3c711-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c711-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c711-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c711-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c711-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c711-115">See also</span></span>

- [<span data-ttu-id="3c711-116">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="3c711-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
