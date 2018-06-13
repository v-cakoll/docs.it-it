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
ms.openlocfilehash: f51a41e8f00a0cf88b11078468ba5a8511fd1391
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424739"
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="c7cb2-102">Metodo ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="c7cb2-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="c7cb2-103">Ottiene il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="c7cb2-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7cb2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7cb2-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c7cb2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c7cb2-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="c7cb2-106">[out] Puntatore a una variabile che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="c7cb2-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c7cb2-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c7cb2-107">Return Value</span></span>  
 <span data-ttu-id="c7cb2-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c7cb2-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7cb2-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7cb2-109">Requirements</span></span>  
 <span data-ttu-id="c7cb2-110">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c7cb2-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7cb2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7cb2-111">See Also</span></span>  
 [<span data-ttu-id="c7cb2-112">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="c7cb2-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="c7cb2-113">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="c7cb2-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="c7cb2-114">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="c7cb2-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
