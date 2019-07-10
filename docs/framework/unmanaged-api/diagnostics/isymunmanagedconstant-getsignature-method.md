---
title: Metodo ISymUnmanagedConstant::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5d479e9f55cf7d7a13fef99f302bfd8d9d89d47f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776949"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="5a6e6-102">Metodo ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="5a6e6-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="5a6e6-103">Ottiene la firma della costante.</span><span class="sxs-lookup"><span data-stu-id="5a6e6-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a6e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a6e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a6e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5a6e6-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="5a6e6-106">[in] La lunghezza del buffer che il `pcSig` punta il parametro.</span><span class="sxs-lookup"><span data-stu-id="5a6e6-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="5a6e6-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="5a6e6-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="5a6e6-108">[out] Buffer che archivia la firma.</span><span class="sxs-lookup"><span data-stu-id="5a6e6-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a6e6-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5a6e6-109">Return Value</span></span>  
 <span data-ttu-id="5a6e6-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5a6e6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a6e6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a6e6-111">Requirements</span></span>  
 <span data-ttu-id="5a6e6-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5a6e6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a6e6-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a6e6-113">See also</span></span>

- [<span data-ttu-id="5a6e6-114">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="5a6e6-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="5a6e6-115">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="5a6e6-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="5a6e6-116">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="5a6e6-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
