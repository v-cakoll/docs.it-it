---
title: Metodo ISymUnmanagedScope::GetLocals
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e45f5411d48032b86403e35358d7ce83d5f97c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777917"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="e8868-102">Metodo ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="e8868-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="e8868-103">Ottiene le variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="e8868-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8868-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e8868-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8868-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e8868-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="e8868-106">[in] Oggetto `ULONG32` che indica le dimensioni del `locals` matrice.</span><span class="sxs-lookup"><span data-stu-id="e8868-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="e8868-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="e8868-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="e8868-108">[out] Matrice che riceve le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="e8868-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8868-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e8868-109">Return Value</span></span>  
 <span data-ttu-id="e8868-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e8868-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8868-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e8868-111">Requirements</span></span>  
 <span data-ttu-id="e8868-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8868-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8868-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8868-113">See also</span></span>

- [<span data-ttu-id="e8868-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="e8868-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
