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
ms.openlocfilehash: 1534955c1f7cfd37732a08b0b33cda5bff8a8aab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59113022"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="56e13-102">Metodo ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="56e13-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="56e13-103">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="56e13-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56e13-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="56e13-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56e13-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="56e13-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="56e13-106">[out] Puntatore al valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="56e13-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56e13-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="56e13-107">Return Value</span></span>  
 <span data-ttu-id="56e13-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="56e13-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56e13-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="56e13-109">Requirements</span></span>  
 <span data-ttu-id="56e13-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="56e13-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e13-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="56e13-111">See also</span></span>

- [<span data-ttu-id="56e13-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="56e13-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
