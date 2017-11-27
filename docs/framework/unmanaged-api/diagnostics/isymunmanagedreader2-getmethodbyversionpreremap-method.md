---
title: Metodo ISymUnmanagedReader2::GetMethodByVersionPreRemap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 69a203424320a176cd285c23d98111e71709042a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a><span data-ttu-id="568cf-102">Metodo ISymUnmanagedReader2::GetMethodByVersionPreRemap</span><span class="sxs-lookup"><span data-stu-id="568cf-102">ISymUnmanagedReader2::GetMethodByVersionPreRemap Method</span></span>
<span data-ttu-id="568cf-103">Ottiene un metodo del lettore di simboli, dato un token di metodo e un numero di versione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="568cf-103">Gets a symbol reader method, given a method token and an edit-and-continue version number.</span></span> <span data-ttu-id="568cf-104">Numeri di versione iniziano da 1 e vengono incrementati ogni volta che il metodo viene modificato in seguito a un'operazione di modifica e continuazione.</span><span class="sxs-lookup"><span data-stu-id="568cf-104">Version numbers start at 1 and are incremented each time the method is changed as a result of an edit-and-continue operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="568cf-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="568cf-105">Syntax</span></span>  
  
```  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="568cf-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="568cf-106">Parameters</span></span>  
 `token`  
 <span data-ttu-id="568cf-107">[in] Il token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="568cf-107">[in] The method metadata token.</span></span>  
  
 `version`  
 <span data-ttu-id="568cf-108">[in] La versione del metodo.</span><span class="sxs-lookup"><span data-stu-id="568cf-108">[in] The method version.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="568cf-109">[out] Un puntatore all'oggetto restituito [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="568cf-109">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="568cf-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="568cf-110">Return Value</span></span>  
 <span data-ttu-id="568cf-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="568cf-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="568cf-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="568cf-112">Requirements</span></span>  
 <span data-ttu-id="568cf-113">**Intestazione:** CorSym.idl.</span><span class="sxs-lookup"><span data-stu-id="568cf-113">**Header:** CorSym.idl.</span></span> <span data-ttu-id="568cf-114">CorSym.h</span><span class="sxs-lookup"><span data-stu-id="568cf-114">CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="568cf-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="568cf-115">See Also</span></span>  
 [<span data-ttu-id="568cf-116">ISymUnmanagedReader2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="568cf-116">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
