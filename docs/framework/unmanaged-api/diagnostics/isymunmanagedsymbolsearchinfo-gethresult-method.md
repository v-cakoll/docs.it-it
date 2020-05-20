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
ms.openlocfilehash: 9dcd8282adf200932e86c950bee0b073780ce02d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615306"
---
# <a name="isymunmanagedsymbolsearchinfogethresult-method"></a><span data-ttu-id="546c6-102">Metodo ISymUnmanagedSymbolSearchInfo::GetHRESULT</span><span class="sxs-lookup"><span data-stu-id="546c6-102">ISymUnmanagedSymbolSearchInfo::GetHRESULT Method</span></span>
<span data-ttu-id="546c6-103">Ottiene HRESULT.</span><span class="sxs-lookup"><span data-stu-id="546c6-103">Gets the HRESULT.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="546c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="546c6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHRESULT(  
    [out] HRESULT *phr);  
```  
  
## <a name="parameters"></a><span data-ttu-id="546c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="546c6-105">Parameters</span></span>  
 `phr`  
 <span data-ttu-id="546c6-106">out Puntatore a HRESULT.</span><span class="sxs-lookup"><span data-stu-id="546c6-106">[out] A pointer to the HRESULT.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="546c6-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="546c6-107">Return Value</span></span>  
 <span data-ttu-id="546c6-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="546c6-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="546c6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="546c6-109">Requirements</span></span>  
 <span data-ttu-id="546c6-110">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="546c6-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="546c6-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="546c6-111">See also</span></span>

- [<span data-ttu-id="546c6-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="546c6-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](isymunmanagedsymbolsearchinfo-interface.md)
