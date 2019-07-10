---
title: Metodo ISymUnmanagedConstant::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73ece48a21ac40320379f5bf4ea309a3ec36b40f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736774"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="964f2-102">Metodo ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="964f2-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="964f2-103">Ottiene il nome della costante.</span><span class="sxs-lookup"><span data-stu-id="964f2-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="964f2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="964f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="964f2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="964f2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="964f2-106">[in] La lunghezza del buffer che il `szName` punta il parametro.</span><span class="sxs-lookup"><span data-stu-id="964f2-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="964f2-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="964f2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="964f2-108">[out] Buffer che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="964f2-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="964f2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="964f2-109">Return Value</span></span>  
 <span data-ttu-id="964f2-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="964f2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="964f2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="964f2-111">Requirements</span></span>  
 <span data-ttu-id="964f2-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="964f2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="964f2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="964f2-113">See also</span></span>

- [<span data-ttu-id="964f2-114">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="964f2-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="964f2-115">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="964f2-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="964f2-116">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="964f2-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
