---
title: Metodo ISymUnmanagedSymbolSearchInfo::GetSearchPath
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04bf526b4868fc683eac92a84828ae36b02bb3ff
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479528"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="ee619-102">Metodo ISymUnmanagedSymbolSearchInfo::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="ee619-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="ee619-103">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee619-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee619-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ee619-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee619-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ee619-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="ee619-106">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="ee619-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ee619-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ee619-107">Return Value</span></span>  
 <span data-ttu-id="ee619-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ee619-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee619-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ee619-109">Requirements</span></span>  
 <span data-ttu-id="ee619-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ee619-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee619-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee619-111">See also</span></span>
- [<span data-ttu-id="ee619-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="ee619-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
