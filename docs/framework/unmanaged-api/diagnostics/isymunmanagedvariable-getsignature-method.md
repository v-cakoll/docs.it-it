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
ms.openlocfilehash: 4b089540f23659d4f7811d921364adc73fd62803
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427743"
---
# <a name="isymunmanagedvariablegetsignature-method"></a><span data-ttu-id="69902-102">Metodo ISymUnmanagedVariable::GetSignature</span><span class="sxs-lookup"><span data-stu-id="69902-102">ISymUnmanagedVariable::GetSignature Method</span></span>
<span data-ttu-id="69902-103">Ottiene la firma di questa variabile.</span><span class="sxs-lookup"><span data-stu-id="69902-103">Gets the signature of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69902-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="69902-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="69902-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="69902-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="69902-106">[in] La lunghezza del buffer a cui punta il `sig` parametro.</span><span class="sxs-lookup"><span data-stu-id="69902-106">[in] The length of the buffer pointed to by the `sig` parameter.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="69902-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="69902-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="69902-108">[out] Buffer che archivia la firma.</span><span class="sxs-lookup"><span data-stu-id="69902-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="69902-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="69902-109">Return Value</span></span>  
 <span data-ttu-id="69902-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="69902-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69902-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="69902-111">Requirements</span></span>  
 <span data-ttu-id="69902-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69902-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69902-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69902-113">See Also</span></span>  
 [<span data-ttu-id="69902-114">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="69902-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
