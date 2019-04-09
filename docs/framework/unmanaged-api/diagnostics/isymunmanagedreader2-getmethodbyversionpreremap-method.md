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
ms.openlocfilehash: bcd200b7fa431f193dd202c3c2a690aa22ec8e32
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135185"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="91b9f-102">Metodo ISymUnmanagedReader2::GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="91b9f-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="91b9f-103">Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="91b9f-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="91b9f-104">I numeri di versione iniziano da 1 e vengano incrementati ogni volta che il metodo viene modificato in seguito a un'operazione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="91b9f-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b9f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="91b9f-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91b9f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="91b9f-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="91b9f-107">[in] Il token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="91b9f-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="91b9f-108">[in] La versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="91b9f-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="91b9f-109">[out] Un puntatore al valore restituito [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="91b9f-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91b9f-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="91b9f-110">Return Value</span></span>  
 <span data-ttu-id="91b9f-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="91b9f-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91b9f-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="91b9f-112">Requirements</span></span>  
 <span data-ttu-id="91b9f-113">**Intestazione:** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="91b9f-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="91b9f-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="91b9f-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b9f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91b9f-115">See also</span></span>

- [<span data-ttu-id="91b9f-116">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="91b9f-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
