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
ms.openlocfilehash: 9a490299c24f44b59da682f714f4b696fde3cba5
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614513"
---
# <a name="isymunmanagedencupdateupdatemethodlines-method"></a><span data-ttu-id="247f6-102">Metodo ISymUnmanagedENCUpdate::UpdateMethodLines</span><span class="sxs-lookup"><span data-stu-id="247f6-102">ISymUnmanagedENCUpdate::UpdateMethodLines Method</span></span>
<span data-ttu-id="247f6-103">Consente di aggiornare le informazioni sulla riga per un metodo che non è stato ricompilato, ma le cui righe sono state spostate in modo indipendente.</span><span class="sxs-lookup"><span data-stu-id="247f6-103">Allows updating the line information for a method that has not been recompiled, but whose lines have moved independently.</span></span> <span data-ttu-id="247f6-104">È consentito un Delta per ogni istruzione.</span><span class="sxs-lookup"><span data-stu-id="247f6-104">A delta for each statement is allowed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="247f6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="247f6-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateMethodLines(  
    [in]  mdMethodDef  mdMethodToken,  
    [in, size_is(cDeltas)] INT32*  pDeltas,  
    [in]  ULONG        cDeltas);  
```  
  
## <a name="parameters"></a><span data-ttu-id="247f6-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="247f6-106">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="247f6-107">in Metadati del token del metodo.</span><span class="sxs-lookup"><span data-stu-id="247f6-107">[in] The metadata of the method token.</span></span>  
  
 `pDeltas`  
 <span data-ttu-id="247f6-108">in Matrice di `INT32` valori che indica i Delta per ogni punto di sequenza nel metodo.</span><span class="sxs-lookup"><span data-stu-id="247f6-108">[in] An array of `INT32` values that indicates deltas for each sequence point in the method.</span></span>  
  
 `cDeltas`  
 <span data-ttu-id="247f6-109">in Oggetto `ULONG` contenente la dimensione del `pDeltas` parametro.</span><span class="sxs-lookup"><span data-stu-id="247f6-109">[in] A `ULONG` containing the size of the `pDeltas` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="247f6-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="247f6-110">Return Value</span></span>  
 <span data-ttu-id="247f6-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="247f6-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="247f6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="247f6-112">Requirements</span></span>  
 <span data-ttu-id="247f6-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="247f6-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="247f6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="247f6-114">See also</span></span>

- [<span data-ttu-id="247f6-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="247f6-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
