---
title: Metodo ISymUnmanagedSymbolSearchInfo::GetHRESULT
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetHRESULT
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo::GetHRESULT method [.NET Framework debugging]
- GetHRESULT method [.NET Framework debugging]
ms.assetid: 6999dc3d-65d7-4bf6-bb0a-6efc0fc72588
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b32865e0ac9d8a4a049db5d7ed6179879342c10a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778102"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="ed1ed-102">Metodo ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="ed1ed-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="ed1ed-103">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ed1ed-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed1ed-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ed1ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed1ed-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ed1ed-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="ed1ed-106">[out] Puntatore al valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ed1ed-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed1ed-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ed1ed-107">Return Value</span></span>  
 <span data-ttu-id="ed1ed-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ed1ed-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed1ed-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ed1ed-109">Requirements</span></span>  
 <span data-ttu-id="ed1ed-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ed1ed-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed1ed-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed1ed-111">See also</span></span>

- [<span data-ttu-id="ed1ed-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ed1ed-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
