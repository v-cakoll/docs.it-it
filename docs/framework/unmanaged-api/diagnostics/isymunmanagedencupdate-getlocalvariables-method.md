---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 48e359f8ed4d52de1cff7ca46a523f4eb80ec4c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776899"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="01563-102">Metodo ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="01563-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="01563-103">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="01563-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01563-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="01563-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01563-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="01563-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="01563-106">[in] Il token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="01563-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="01563-107">[in] Oggetto `ULONG` che indica le dimensioni del `rgLocals` parametro.</span><span class="sxs-lookup"><span data-stu-id="01563-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="01563-108">[out] La matrice restituita di [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) istanze.</span><span class="sxs-lookup"><span data-stu-id="01563-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="01563-109">[out] Un puntatore a un `ULONG` che riceve le dimensioni del `rgLocals` buffer necessario per contenere variabili locali.</span><span class="sxs-lookup"><span data-stu-id="01563-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01563-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="01563-110">Return Value</span></span>  
 <span data-ttu-id="01563-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="01563-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01563-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="01563-112">Requirements</span></span>  
 <span data-ttu-id="01563-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="01563-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01563-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="01563-114">See also</span></span>

- [<span data-ttu-id="01563-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="01563-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
