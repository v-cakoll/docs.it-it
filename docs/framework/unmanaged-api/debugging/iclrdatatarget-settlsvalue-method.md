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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c0be35772b10d89f90da5b33f47aa781034b13a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152932"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="0f680-102">Metodo ICLRDataTarget::SetTLSValue</span><span class="sxs-lookup"><span data-stu-id="0f680-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="0f680-103">Imposta un valore nell'archiviazione thread-local (TLS) del thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="0f680-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="0f680-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0f680-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f680-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0f680-105">Syntax</span></span>  
  
```  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f680-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0f680-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="0f680-107">[in] L'identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0f680-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="0f680-108">[in] L'indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="0f680-108">[in] The index of the location.</span></span> <span data-ttu-id="0f680-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="0f680-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="0f680-110">[in] Oggetto `CLRDATA_ADDRESS` valore che specifica il valore da inserire nella località specificata TLS.</span><span class="sxs-lookup"><span data-stu-id="0f680-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f680-111">Note</span><span class="sxs-lookup"><span data-stu-id="0f680-111">Remarks</span></span>  
 <span data-ttu-id="0f680-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="0f680-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f680-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0f680-113">Requirements</span></span>  
 <span data-ttu-id="0f680-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f680-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f680-115">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="0f680-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0f680-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f680-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f680-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f680-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f680-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0f680-118">See also</span></span>

- [<span data-ttu-id="0f680-119">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="0f680-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
