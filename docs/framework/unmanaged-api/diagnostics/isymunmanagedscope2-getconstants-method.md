---
title: Metodo ISymUnmanagedScope2::GetConstants
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedScope2.GetConstants
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope2::GetConstants
helpviewer_keywords:
- ISymUnmanagedScope2::GetConstants method [.NET Framework debugging]
- GetConstants method [.NET Framework debugging]
ms.assetid: f241b620-9ec5-42fd-92ef-3b22329db72a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: da0d2d39fcc1de8435c7af49a912764c79eb6583
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscope2getconstants-method"></a><span data-ttu-id="1e471-102">Metodo ISymUnmanagedScope2::GetConstants</span><span class="sxs-lookup"><span data-stu-id="1e471-102">ISymUnmanagedScope2::GetConstants Method</span></span>
<span data-ttu-id="1e471-103">Ottiene le costanti locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="1e471-103">Gets the local constants defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e471-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1e471-104">Syntax</span></span>  
  
```  
HRESULT GetConstants(  
     [in]  ULONG32  cConstants,  
     [out] ULONG32  *pcConstants,  
     [out, size_is(cConstants),  
         length_is(*pcConstants)] ISymUnmanagedConstant*   
             constants[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1e471-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1e471-105">Parameters</span></span>  
 `cConstants`  
 <span data-ttu-id="1e471-106">[in] La lunghezza del buffer che il `pcConstants` punta al parametro.</span><span class="sxs-lookup"><span data-stu-id="1e471-106">[in] The length of the buffer that the `pcConstants` parameter points to.</span></span>  
  
 `pcConstants`  
 <span data-ttu-id="1e471-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere le costanti.</span><span class="sxs-lookup"><span data-stu-id="1e471-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the constants.</span></span>  
  
 `constants`  
 <span data-ttu-id="1e471-108">[out] Buffer che archivia le costanti.</span><span class="sxs-lookup"><span data-stu-id="1e471-108">[out] The buffer that stores the constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e471-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1e471-109">Return Value</span></span>  
 <span data-ttu-id="1e471-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1e471-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e471-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1e471-111">Requirements</span></span>  
 <span data-ttu-id="1e471-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1e471-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e471-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1e471-113">See Also</span></span>  
 [<span data-ttu-id="1e471-114">Interfaccia ISymUnmanagedScope2</span><span class="sxs-lookup"><span data-stu-id="1e471-114">ISymUnmanagedScope2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)
