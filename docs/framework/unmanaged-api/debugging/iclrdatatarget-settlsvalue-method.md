---
title: Metodo ICLRDataTarget::SetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 6c98fc93fd659ccfc0ccd42eec7d95382cf342f8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860520"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="c9001-102">Metodo ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="c9001-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="c9001-103">Imposta un valore nell'archiviazione locale di thread (TLS) del thread specificato nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9001-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="c9001-104">Questo metodo viene chiamato dai servizi di accesso ai dati di Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="c9001-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9001-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9001-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9001-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9001-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="c9001-107">in Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="c9001-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="c9001-108">in Indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="c9001-108">[in] The index of the location.</span></span> <span data-ttu-id="c9001-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="c9001-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="c9001-110">in `CLRDATA_ADDRESS` Valore che specifica il valore da inserire nella posizione TLS specificata.</span><span class="sxs-lookup"><span data-stu-id="c9001-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9001-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="c9001-111">Remarks</span></span>  
 <span data-ttu-id="c9001-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="c9001-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9001-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9001-113">Requirements</span></span>  
 <span data-ttu-id="c9001-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9001-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9001-115">**Intestazione:** ClrData. idl, ClrData. h</span><span class="sxs-lookup"><span data-stu-id="c9001-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="c9001-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9001-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9001-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9001-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9001-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9001-118">See also</span></span>

- [<span data-ttu-id="c9001-119">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="c9001-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
