---
title: Metodo ICLRDataTarget::GetTLSValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a820ec7c0a00306266be432a8aceacb3d30d1b4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="09083-102">Metodo ICLRDataTarget::GetTLSValue</span><span class="sxs-lookup"><span data-stu-id="09083-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="09083-103">Ottiene un valore dall'archiviazione locale di thread (TLS) del thread nel processo di destinazione specificato.</span><span class="sxs-lookup"><span data-stu-id="09083-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="09083-104">Questo metodo viene chiamato da servizi di accesso dati di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="09083-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09083-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="09083-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09083-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="09083-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="09083-107">[in] Identificatore del sistema operativo di un thread nel processo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="09083-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="09083-108">[in] Indice della posizione.</span><span class="sxs-lookup"><span data-stu-id="09083-108">[in] The index of the location.</span></span> <span data-ttu-id="09083-109">Questo valore deve essere un indice valido nell'archivio locale del thread specificato.</span><span class="sxs-lookup"><span data-stu-id="09083-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="09083-110">[out] Un puntatore a un `CLRDATA_ADDRESS` valore che specifica il valore restituito dalla posizione TLS specificata.</span><span class="sxs-lookup"><span data-stu-id="09083-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09083-111">Note</span><span class="sxs-lookup"><span data-stu-id="09083-111">Remarks</span></span>  
 <span data-ttu-id="09083-112">Questo metodo è implementato dal writer dell'applicazione di debug.</span><span class="sxs-lookup"><span data-stu-id="09083-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09083-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="09083-113">Requirements</span></span>  
 <span data-ttu-id="09083-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09083-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09083-115">**Intestazione:** ClrData.idl, Clrdata. H</span><span class="sxs-lookup"><span data-stu-id="09083-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="09083-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09083-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09083-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09083-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09083-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="09083-118">See Also</span></span>  
 [<span data-ttu-id="09083-119">ICLRDataTarget (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="09083-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
