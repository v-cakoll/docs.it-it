---
title: Metodo ISymUnmanagedConstant::GetValue
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetValue
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 75cc16f44ddf29b161c758718b697cc2aaba8e08
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204666"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="b38b9-102">Metodo ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="b38b9-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="b38b9-103">Ottiene il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="b38b9-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b38b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b38b9-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b38b9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b38b9-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="b38b9-106">[out] Un puntatore a una variabile che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="b38b9-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b38b9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b38b9-107">Return Value</span></span>  
 <span data-ttu-id="b38b9-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="b38b9-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b38b9-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b38b9-109">Requirements</span></span>  
 <span data-ttu-id="b38b9-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b38b9-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b38b9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b38b9-111">See also</span></span>

- [<span data-ttu-id="b38b9-112">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="b38b9-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="b38b9-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="b38b9-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="b38b9-114">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="b38b9-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
