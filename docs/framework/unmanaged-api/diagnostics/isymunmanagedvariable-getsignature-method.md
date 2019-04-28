---
title: Metodo ISymUnmanagedVariable::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetSignature method [.NET Framework debugging]
ms.assetid: 78c1ba28-a410-4360-805c-23a95408964a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3cc616246812bb9643388d8ad57cf84bc387b55e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61797501"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="3a716-102">Metodo ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="3a716-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="3a716-103">Ottiene la firma della variabile.</span><span class="sxs-lookup"><span data-stu-id="3a716-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a716-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3a716-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a716-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3a716-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="3a716-106">[in] La lunghezza del buffer a cui punta il `sig` parametro.</span><span class="sxs-lookup"><span data-stu-id="3a716-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="3a716-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="3a716-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="3a716-108">[out] Buffer che archivia la firma.</span><span class="sxs-lookup"><span data-stu-id="3a716-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a716-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3a716-109">Return Value</span></span>  
 <span data-ttu-id="3a716-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3a716-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a716-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3a716-111">Requirements</span></span>  
 <span data-ttu-id="3a716-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3a716-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a716-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3a716-113">See also</span></span>

- [<span data-ttu-id="3a716-114">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="3a716-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
