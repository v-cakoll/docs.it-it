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
ms.openlocfilehash: f25150d037a2f6fabb700f2c4bf2191e8e402a8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446216"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="2e8f0-102">Metodo ISymUnmanagedSourceServerModule::GetSourceServerData</span><span class="sxs-lookup"><span data-stu-id="2e8f0-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="2e8f0-103">Restituisce i dati del server di origine per il modulo.</span><span class="sxs-lookup"><span data-stu-id="2e8f0-103">Returns the source server data for the module.</span></span> <span data-ttu-id="2e8f0-104">Il chiamante deve liberare risorse usando `CoTaskMemFree`.</span><span class="sxs-lookup"><span data-stu-id="2e8f0-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e8f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e8f0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e8f0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e8f0-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="2e8f0-107">out Puntatore a un `ULONG32` che riceve le dimensioni, in byte, dei dati del server di origine.</span><span class="sxs-lookup"><span data-stu-id="2e8f0-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="2e8f0-108">out Puntatore al valore restituito `pDataByteCount`.</span><span class="sxs-lookup"><span data-stu-id="2e8f0-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e8f0-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2e8f0-109">Return Value</span></span>  
 <span data-ttu-id="2e8f0-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2e8f0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e8f0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e8f0-111">Requirements</span></span>  
 <span data-ttu-id="2e8f0-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2e8f0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e8f0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e8f0-113">See also</span></span>

- [<span data-ttu-id="2e8f0-114">Interfaccia ISymUnmanagedSourceServerModule</span><span class="sxs-lookup"><span data-stu-id="2e8f0-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)
