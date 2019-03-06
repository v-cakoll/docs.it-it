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
ms.openlocfilehash: 00078d1d405eb2abc0d34f7b455fa045ac17c261
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485835"
---
# <a name="isymunmanagedreadergetglobalvariables-method"></a><span data-ttu-id="648e3-102">Metodo ISymUnmanagedReader::GetGlobalVariables</span><span class="sxs-lookup"><span data-stu-id="648e3-102">ISymUnmanagedReader::GetGlobalVariables Method</span></span>
<span data-ttu-id="648e3-103">Restituisce tutte le variabili globali.</span><span class="sxs-lookup"><span data-stu-id="648e3-103">Returns all global variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="648e3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="648e3-104">Syntax</span></span>  
  
```  
HRESULT GetGlobalVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars),  
        length_is(*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="648e3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="648e3-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="648e3-106">[in] La lunghezza del buffer a cui punta `pcVars`.</span><span class="sxs-lookup"><span data-stu-id="648e3-106">[in] The length of the buffer pointed to by `pcVars`.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="648e3-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le variabili.</span><span class="sxs-lookup"><span data-stu-id="648e3-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the variables.</span></span>  
  
 `pVars`  
 <span data-ttu-id="648e3-108">[out] Un buffer che contiene le variabili.</span><span class="sxs-lookup"><span data-stu-id="648e3-108">[out] A buffer that contains the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="648e3-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="648e3-109">Return Value</span></span>  
 <span data-ttu-id="648e3-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="648e3-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="648e3-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="648e3-111">Requirements</span></span>  
 <span data-ttu-id="648e3-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="648e3-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="648e3-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="648e3-113">See also</span></span>
- [<span data-ttu-id="648e3-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="648e3-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
