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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea8052152b08732906c707648f361bba4d83a276
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173576"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="e1374-102">Metodo ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="e1374-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="e1374-103">Restituisce i dati del server di origine per il modulo.</span><span class="sxs-lookup"><span data-stu-id="e1374-103">Returns the source server data for the module.</span></span> <span data-ttu-id="e1374-104">Il chiamante deve liberare risorse mediante `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="e1374-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1374-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e1374-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1374-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="e1374-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="e1374-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in byte, dei dati del server di origine.</span><span class="sxs-lookup"><span data-stu-id="e1374-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="e1374-108">[out] Un puntatore all'oggetto restituito `pDataByteCount` valore.</span><span class="sxs-lookup"><span data-stu-id="e1374-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e1374-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e1374-109">Return Value</span></span>  
 <span data-ttu-id="e1374-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e1374-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1374-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e1374-111">Requirements</span></span>  
 <span data-ttu-id="e1374-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e1374-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1374-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e1374-113">See also</span></span>

- [<span data-ttu-id="e1374-114">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="e1374-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
