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
ms.openlocfilehash: 649f44bd7966b9ca89d2d040b7eede662404aa0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638606"
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="c6e55-102">Metodo ISymUnmanagedSymbolSearchInfo::GetSearchPath</span><span class="sxs-lookup"><span data-stu-id="c6e55-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="c6e55-103">Ottiene il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6e55-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6e55-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6e55-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6e55-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6e55-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="c6e55-106">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il percorso di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c6e55-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6e55-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c6e55-107">Return Value</span></span>  
 <span data-ttu-id="c6e55-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c6e55-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6e55-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6e55-109">Requirements</span></span>  
 <span data-ttu-id="c6e55-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6e55-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6e55-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6e55-111">See also</span></span>

- [<span data-ttu-id="c6e55-112">Interfaccia ISymUnmanagedSymbolSearchInfo</span><span class="sxs-lookup"><span data-stu-id="c6e55-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
