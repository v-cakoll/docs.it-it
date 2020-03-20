---
title: Metodo ISymUnmanagedSourceServerModule::GetSourceServerData
ms.date: 03/30/2017
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
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176578"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="227c7-102">Metodo ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="227c7-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="227c7-103">Restituisce i dati del server di origine per il modulo.</span><span class="sxs-lookup"><span data-stu-id="227c7-103">Returns the source server data for the module.</span></span> <span data-ttu-id="227c7-104">Il chiamante deve `CoTaskMemFree`liberare risorse utilizzando .</span><span class="sxs-lookup"><span data-stu-id="227c7-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="227c7-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="227c7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="227c7-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="227c7-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="227c7-107">[fuori] Puntatore a `ULONG32` un che riceve la dimensione, in byte, dei dati del server di origine.</span><span class="sxs-lookup"><span data-stu-id="227c7-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="227c7-108">[fuori] Puntatore al valore `pDataByteCount` restituito.</span><span class="sxs-lookup"><span data-stu-id="227c7-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="227c7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="227c7-109">Return Value</span></span>  
 <span data-ttu-id="227c7-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="227c7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="227c7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="227c7-111">Requirements</span></span>  
 <span data-ttu-id="227c7-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="227c7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="227c7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="227c7-113">See also</span></span>

- [<span data-ttu-id="227c7-114">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="227c7-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
