---
title: Metodo ISymUnmanagedENCUpdate::UpdateMethodLines
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateMethodLines
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateMethodLines
helpviewer_keywords:
- UpdateMethodLines method [.NET Framework debugging]
- ISymUnmanagedENCUpdate::UpdateMethodLines method [.NET Framework debugging]
ms.assetid: 275ef87b-0b53-49f9-af6b-58506335dc06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bd1f101e2e9cf9baeb28290c7607ccab3d8d7440
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178919"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="5b0e3-102">Metodo ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="5b0e3-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="5b0e3-103">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono spostati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="5b0e3-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="5b0e3-104">Valore delta di ogni istruzione è consentito.</span><span class="sxs-lookup"><span data-stu-id="5b0e3-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0e3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5b0e3-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0e3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5b0e3-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="5b0e3-107">[in] I metadati del token del metodo.</span><span class="sxs-lookup"><span data-stu-id="5b0e3-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="5b0e3-108">[in] Matrice di `INT32` valori che indica i valori differenziali per ogni punto di sequenza nel metodo.</span><span class="sxs-lookup"><span data-stu-id="5b0e3-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="5b0e3-109">[in] Oggetto `ULONG` che contiene la dimensione del `pDeltas` parametro.</span><span class="sxs-lookup"><span data-stu-id="5b0e3-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b0e3-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5b0e3-110">Return Value</span></span>  
 <span data-ttu-id="5b0e3-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5b0e3-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0e3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5b0e3-112">Requirements</span></span>  
 <span data-ttu-id="5b0e3-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5b0e3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0e3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b0e3-114">See also</span></span>

- [<span data-ttu-id="5b0e3-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="5b0e3-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
