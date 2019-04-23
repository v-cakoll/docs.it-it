---
title: Metodo ISymUnmanagedReader::GetVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetVariables
helpviewer_keywords:
- ISymUnmanagedReader::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 16dc49cb-2c60-4ac8-9c35-020e9afba3f8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 846ff76fb1073394cc27597c9a2015148581cc70
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165100"
---
# <a name="isymunmanagedreadergetvariables-method"></a><span data-ttu-id="9f182-102">Metodo ISymUnmanagedReader::GetVariables</span><span class="sxs-lookup"><span data-stu-id="9f182-102">ISymUnmanagedReader::GetVariables Method</span></span>
<span data-ttu-id="9f182-103">Restituisce una variabile non locale, padre e al nome.</span><span class="sxs-lookup"><span data-stu-id="9f182-103">Returns a non-local variable, given its parent and name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f182-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9f182-104">Syntax</span></span>  
  
```  
HRESULT GetVariables (  
    [in]  mdToken  parent,  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is (cVars),  
        length_is (*pcVars)] ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f182-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9f182-105">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="9f182-106">[in] L'elemento padre della variabile.</span><span class="sxs-lookup"><span data-stu-id="9f182-106">[in] The parent of the variable.</span></span>  
  
 `cVars`  
 <span data-ttu-id="9f182-107">[in] Dimensione della matrice `pVars`.</span><span class="sxs-lookup"><span data-stu-id="9f182-107">[in] The size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="9f182-108">[out] Un puntatore alla variabile che riceve il numero di variabili restituite in `pVars`.</span><span class="sxs-lookup"><span data-stu-id="9f182-108">[out] A pointer to the variable that receives the number of variables returned in `pVars`.</span></span>  
  
 `pVars`  
 <span data-ttu-id="9f182-109">[out] Puntatore alla variabile che riceve le variabili.</span><span class="sxs-lookup"><span data-stu-id="9f182-109">[out] A pointer to the variable that receives the variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f182-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9f182-110">Return Value</span></span>  
 <span data-ttu-id="9f182-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9f182-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f182-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9f182-112">Requirements</span></span>  
 <span data-ttu-id="9f182-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9f182-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f182-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9f182-114">See also</span></span>

- [<span data-ttu-id="9f182-115">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="9f182-115">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
