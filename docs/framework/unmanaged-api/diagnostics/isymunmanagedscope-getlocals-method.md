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
ms.openlocfilehash: 625609d8632f1f73ee2ec01e3b2e0e1af7e4a134
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986245"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="108d4-102">Metodo ISymUnmanagedScope::GetLocals</span><span class="sxs-lookup"><span data-stu-id="108d4-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="108d4-103">Ottiene le variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="108d4-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108d4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="108d4-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="108d4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="108d4-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="108d4-106">[in] Oggetto `ULONG32` che indica le dimensioni del `locals` matrice.</span><span class="sxs-lookup"><span data-stu-id="108d4-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="108d4-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="108d4-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="108d4-108">[out] Matrice che riceve le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="108d4-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="108d4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="108d4-109">Return Value</span></span>  
 <span data-ttu-id="108d4-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="108d4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108d4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="108d4-111">Requirements</span></span>  
 <span data-ttu-id="108d4-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="108d4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="108d4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="108d4-113">See also</span></span>

- [<span data-ttu-id="108d4-114">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="108d4-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
