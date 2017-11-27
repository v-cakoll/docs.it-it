---
title: Metodo ISymUnmanagedScope::GetMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetMethod
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetMethod
helpviewer_keywords:
- GetMethod method, ISymUnmanagedScope interface [.NET Framework debugging]
- ISymUnmanagedScope::GetMethod method [.NET Framework debugging]
ms.assetid: a61866ee-221a-45b9-a1b7-395825b77872
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bb062ad7ab485a1631a9cbe15f904b21226cb502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscopegetmethod-method"></a><span data-ttu-id="d185c-102">Metodo ISymUnmanagedScope::GetMethod</span><span class="sxs-lookup"><span data-stu-id="d185c-102">ISymUnmanagedScope::GetMethod Method</span></span>
<span data-ttu-id="d185c-103">Ottiene il metodo che contiene questo ambito.</span><span class="sxs-lookup"><span data-stu-id="d185c-103">Gets the method that contains this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d185c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d185c-104">Syntax</span></span>  
  
```  
HRESULT GetMethod(  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d185c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d185c-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="d185c-106">[out] Un puntatore all'oggetto restituito [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d185c-106">[out] A pointer to the returned [ISymUnmanagedMethod](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d185c-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d185c-107">Return Value</span></span>  
 <span data-ttu-id="d185c-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d185c-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d185c-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d185c-109">Requirements</span></span>  
 <span data-ttu-id="d185c-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d185c-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d185c-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d185c-111">See Also</span></span>  
 [<span data-ttu-id="d185c-112">ISymUnmanagedScope (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d185c-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
