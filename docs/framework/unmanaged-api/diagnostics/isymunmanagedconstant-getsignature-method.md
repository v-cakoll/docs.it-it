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
ms.openlocfilehash: ab1282109d7241c2599f8ca029fc79e4a3135209
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939984"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="1cf59-102">Metodo ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="1cf59-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="1cf59-103">Ottiene la firma della costante.</span><span class="sxs-lookup"><span data-stu-id="1cf59-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cf59-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1cf59-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cf59-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1cf59-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="1cf59-106">[in] La lunghezza del buffer che il `pcSig` punta il parametro.</span><span class="sxs-lookup"><span data-stu-id="1cf59-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="1cf59-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="1cf59-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="1cf59-108">[out] Buffer che archivia la firma.</span><span class="sxs-lookup"><span data-stu-id="1cf59-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1cf59-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1cf59-109">Return Value</span></span>  
 <span data-ttu-id="1cf59-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1cf59-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cf59-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1cf59-111">Requirements</span></span>  
 <span data-ttu-id="1cf59-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1cf59-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cf59-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1cf59-113">See also</span></span>

- [<span data-ttu-id="1cf59-114">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="1cf59-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)
- [<span data-ttu-id="1cf59-115">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="1cf59-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="1cf59-116">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="1cf59-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
