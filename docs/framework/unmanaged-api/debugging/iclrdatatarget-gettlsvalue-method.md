---
title: Metodo ICLRDataTarget::GetTLSValue
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21fa9a17067f754fe9b13c4d32193856a57750ca
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227366"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="8bc58-102">Metodo ICLRDataTarget::GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="8bc58-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="8bc58-103">Ottiene un valore dall'archiviazione thread-local (TLS) del thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="8bc58-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="8bc58-104">Questo metodo viene chiamato dai servizi di accesso dati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="8bc58-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc58-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8bc58-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bc58-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8bc58-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8bc58-107">[in] L'identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8bc58-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="8bc58-108">[in] L'indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="8bc58-108">[in] The index of the location.</span></span> <span data-ttu-id="8bc58-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="8bc58-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="8bc58-110">[out] Un puntatore a un `CLRDATA_ADDRESS` valore che specifica il valore restituito dalla posizione specificata TLS.</span><span class="sxs-lookup"><span data-stu-id="8bc58-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc58-111">Note</span><span class="sxs-lookup"><span data-stu-id="8bc58-111">Remarks</span></span>  
 <span data-ttu-id="8bc58-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="8bc58-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bc58-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8bc58-113">Requirements</span></span>  
 <span data-ttu-id="8bc58-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bc58-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bc58-115">**Intestazione:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8bc58-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8bc58-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bc58-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="8bc58-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="8bc58-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8bc58-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8bc58-118">See also</span></span>

- [<span data-ttu-id="8bc58-119">Interfaccia ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="8bc58-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
