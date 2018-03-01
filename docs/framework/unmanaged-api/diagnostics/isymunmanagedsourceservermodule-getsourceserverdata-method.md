---
title: Metodo ISymUnmanagedSourceServerModule::GetSourceServerData
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f75ffbe3980a6c7587912a1cf099ef87888132a3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="fcb3e-102">Metodo ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="fcb3e-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="fcb3e-103">Restituisce i dati del server di origine per il modulo.</span><span class="sxs-lookup"><span data-stu-id="fcb3e-103">Returns the source server data for the module.</span></span> <span data-ttu-id="fcb3e-104">Il chiamante deve liberare risorse mediante `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="fcb3e-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcb3e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fcb3e-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fcb3e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fcb3e-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="fcb3e-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in byte, dei dati di server di origine.</span><span class="sxs-lookup"><span data-stu-id="fcb3e-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="fcb3e-108">[out] Un puntatore all'oggetto restituito `pDataByteCount` valore.</span><span class="sxs-lookup"><span data-stu-id="fcb3e-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fcb3e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fcb3e-109">Return Value</span></span>  
 <span data-ttu-id="fcb3e-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fcb3e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcb3e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fcb3e-111">Requirements</span></span>  
 <span data-ttu-id="fcb3e-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fcb3e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb3e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fcb3e-113">See Also</span></span>  
 [<span data-ttu-id="fcb3e-114">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="fcb3e-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
