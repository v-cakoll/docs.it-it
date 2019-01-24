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
ms.openlocfilehash: f7905b3ee83378ed1a27501b082dbfca01d6436c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688064"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="b72b4-102">Metodo ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="b72b4-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="b72b4-103">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono spostati in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="b72b4-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="b72b4-104">Valore delta di ogni istruzione è consentito.</span><span class="sxs-lookup"><span data-stu-id="b72b4-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b72b4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b72b4-105">Syntax</span></span>  
  
```  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b72b4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="b72b4-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="b72b4-107">[in] I metadati del token del metodo.</span><span class="sxs-lookup"><span data-stu-id="b72b4-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="b72b4-108">[in] Matrice di `INT32` valori che indica i valori differenziali per ogni punto di sequenza nel metodo.</span><span class="sxs-lookup"><span data-stu-id="b72b4-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="b72b4-109">[in] Oggetto `ULONG` che contiene la dimensione del `pDeltas` parametro.</span><span class="sxs-lookup"><span data-stu-id="b72b4-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b72b4-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b72b4-110">Return Value</span></span>  
 <span data-ttu-id="b72b4-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b72b4-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b72b4-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b72b4-112">Requirements</span></span>  
 <span data-ttu-id="b72b4-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b72b4-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b72b4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b72b4-114">See also</span></span>
- [<span data-ttu-id="b72b4-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="b72b4-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
