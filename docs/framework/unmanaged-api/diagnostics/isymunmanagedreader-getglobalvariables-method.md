---
title: Metodo ISymUnmanagedReader::GetGlobalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetGlobalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetGlobalVariables
helpviewer_keywords:
- GetGlobalVariables method [.NET Framework debugging]
- ISymUnmanagedReader::GetGlobalVariables method [.NET Framework debugging]
ms.assetid: a2dd5098-3e58-4be5-b7a2-e4160b3b505a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e778a5a7baed52941a7f4b990b34d31f8ca84c24
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092643"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="6ee06-102">Metodo ISymUnmanagedReader::GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="6ee06-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="6ee06-103">Restituisce tutte le variabili globali.</span><span class="sxs-lookup"><span data-stu-id="6ee06-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ee06-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6ee06-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ee06-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6ee06-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="6ee06-106">[in] La lunghezza del buffer a cui punta `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="6ee06-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="6ee06-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le variabili.</span><span class="sxs-lookup"><span data-stu-id="6ee06-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="6ee06-108">[out] Un buffer che contiene le variabili.</span><span class="sxs-lookup"><span data-stu-id="6ee06-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ee06-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6ee06-109">Return Value</span></span>  
 <span data-ttu-id="6ee06-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6ee06-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ee06-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6ee06-111">Requirements</span></span>  
 <span data-ttu-id="6ee06-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6ee06-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ee06-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ee06-113">See also</span></span>

- [<span data-ttu-id="6ee06-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="6ee06-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
