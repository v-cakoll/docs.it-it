---
title: Metodo ICLRDataTarget::ReadVirtual
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.ReadVirtual
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::ReadVirtual
helpviewer_keywords:
- ReadVirtual method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::ReadVirtual method [.NET Framework debugging]
ms.assetid: da3769eb-1828-4aa1-b9ed-db4842136a43
topic_type:
- apiref
ms.openlocfilehash: e285df37d83ff73fe29fe293380a4053cb5a9eea
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860561"
---
# <a name="iclrdatatargetreadvirtual-method"></a><span data-ttu-id="e2e49-102">Metodo ICLRDataTarget::ReadVirtual</span><span class="sxs-lookup"><span data-stu-id="e2e49-102">ICLRDataTarget::ReadVirtual Method</span></span>
<span data-ttu-id="e2e49-103">Legge i dati dall'indirizzo di memoria virtuale specificato nel buffer specificato.</span><span class="sxs-lookup"><span data-stu-id="e2e49-103">Reads data from the specified virtual memory address into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2e49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2e49-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadVirtual (  
    [in] CLRDATA_ADDRESS    address,  
    [out, size_is(bytesRequested), length_is(*bytesRead)]
        BYTE                *buffer,  
    [in] ULONG32            bytesRequested,  
    [out] ULONG32           *bytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2e49-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2e49-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="e2e49-106">in CLRDATA_ADDRESS che archivia l'indirizzo di memoria virtuale.</span><span class="sxs-lookup"><span data-stu-id="e2e49-106">[in] A CLRDATA_ADDRESS that stores the virtual memory address.</span></span>  
  
 `buffer`  
 <span data-ttu-id="e2e49-107">out Puntatore a un buffer che riceve i dati.</span><span class="sxs-lookup"><span data-stu-id="e2e49-107">[out] A pointer to a buffer that receives the data.</span></span>  
  
 `bytesRequested`  
 <span data-ttu-id="e2e49-108">in Lunghezza del buffer.</span><span class="sxs-lookup"><span data-stu-id="e2e49-108">[in] The length of the buffer.</span></span>  
  
 `bytesRead`  
 <span data-ttu-id="e2e49-109">out Puntatore al numero di byte restituiti.</span><span class="sxs-lookup"><span data-stu-id="e2e49-109">[out] A pointer to the number of bytes returned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2e49-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2e49-110">Requirements</span></span>  
 <span data-ttu-id="e2e49-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2e49-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2e49-112">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="e2e49-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e2e49-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2e49-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2e49-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2e49-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2e49-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2e49-115">See also</span></span>

- [<span data-ttu-id="e2e49-116">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="e2e49-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
