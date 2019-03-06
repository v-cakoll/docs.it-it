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
ms.openlocfilehash: dd24289f7e670684effa553f930af9aec92e5730
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469600"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="4b8da-102">Metodo ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="4b8da-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="4b8da-103">Ottiene il valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4b8da-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b8da-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b8da-104">Syntax</span></span>  
  
```  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b8da-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4b8da-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="4b8da-106">[out] Puntatore al valore HRESULT.</span><span class="sxs-lookup"><span data-stu-id="4b8da-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b8da-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4b8da-107">Return Value</span></span>  
 <span data-ttu-id="4b8da-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4b8da-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b8da-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b8da-109">Requirements</span></span>  
 <span data-ttu-id="4b8da-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4b8da-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8da-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b8da-111">See also</span></span>
- [<span data-ttu-id="4b8da-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="4b8da-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
