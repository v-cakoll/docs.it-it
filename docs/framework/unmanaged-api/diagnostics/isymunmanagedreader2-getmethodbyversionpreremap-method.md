---
title: Metodo ISymUnmanagedReader2::GetMethodByVersionPreRemap
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efa34d262157faed2e05cd6e7517c259cd279146
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428576"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="23be8-102">Metodo ISymUnmanagedReader2::GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="23be8-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="23be8-103">Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="23be8-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="23be8-104">Numeri di versione iniziano da 1 e vengono incrementati ogni volta che il metodo viene modificato in seguito a un'operazione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="23be8-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23be8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23be8-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23be8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="23be8-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="23be8-107">[in] Il token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="23be8-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="23be8-108">[in] La versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="23be8-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="23be8-109">[out] Un puntatore all'oggetto restituito [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="23be8-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23be8-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="23be8-110">Return Value</span></span>  
 <span data-ttu-id="23be8-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="23be8-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23be8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23be8-112">Requirements</span></span>  
 <span data-ttu-id="23be8-113">**Intestazione:** CorSym. idl.</span><span class="sxs-lookup"><span data-stu-id="23be8-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="23be8-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="23be8-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23be8-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23be8-115">See Also</span></span>  
 [<span data-ttu-id="23be8-116">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="23be8-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
