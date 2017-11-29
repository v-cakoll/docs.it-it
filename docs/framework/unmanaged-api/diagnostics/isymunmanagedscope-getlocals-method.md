---
title: Metodo ISymUnmanagedScope::GetLocals
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetLocals
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76a52d0bd754dde8ded193dee38eaea895223b9d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="6c0bf-102">Metodo ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="6c0bf-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="6c0bf-103">Ottiene le variabili locali definite in questo ambito.</span><span class="sxs-lookup"><span data-stu-id="6c0bf-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c0bf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6c0bf-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c0bf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6c0bf-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="6c0bf-106">[in] Oggetto `ULONG32` che indica le dimensioni del `locals` matrice.</span><span class="sxs-lookup"><span data-stu-id="6c0bf-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="6c0bf-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6c0bf-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="6c0bf-108">[out] Matrice che riceve le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="6c0bf-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c0bf-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6c0bf-109">Return Value</span></span>  
 <span data-ttu-id="6c0bf-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="6c0bf-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c0bf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6c0bf-111">Requirements</span></span>  
 <span data-ttu-id="6c0bf-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6c0bf-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c0bf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6c0bf-113">See Also</span></span>  
 [<span data-ttu-id="6c0bf-114">ISymUnmanagedScope (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="6c0bf-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
