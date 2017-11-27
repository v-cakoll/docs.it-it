---
title: Metodo ISymUnmanagedConstant::GetValue
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetValue
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetValue
helpviewer_keywords:
- GetValue method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetValue method [.NET Framework debugging]
ms.assetid: 0036fc10-e768-47a8-b9cf-bf47faf8d194
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: df55345b34340349c4c20213f75591e9586153cc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedconstantgetvalue-method"></a><span data-ttu-id="bbbbe-102">Metodo ISymUnmanagedConstant::GetValue</span><span class="sxs-lookup"><span data-stu-id="bbbbe-102">ISymUnmanagedConstant::GetValue Method</span></span>
<span data-ttu-id="bbbbe-103">Ottiene il valore della costante.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-103">Gets the value of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbbbe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbbbe-104">Syntax</span></span>  
  
```  
HRESULT GetValue(  
    [out]  VARIANT* pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbbbe-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bbbbe-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="bbbbe-106">[out] Puntatore a una variabile che riceve il valore.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-106">[out] A pointer to a variable that receives the value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbbbe-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bbbbe-107">Return Value</span></span>  
 <span data-ttu-id="bbbbe-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="bbbbe-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbbbe-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bbbbe-109">Requirements</span></span>  
 <span data-ttu-id="bbbbe-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bbbbe-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbbe-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbbbe-111">See Also</span></span>  
 [<span data-ttu-id="bbbbe-112">ISymUnmanagedConstant (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="bbbbe-112">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="bbbbe-113">GetName (metodo)</span><span class="sxs-lookup"><span data-stu-id="bbbbe-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="bbbbe-114">GetSignature (metodo)</span><span class="sxs-lookup"><span data-stu-id="bbbbe-114">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
