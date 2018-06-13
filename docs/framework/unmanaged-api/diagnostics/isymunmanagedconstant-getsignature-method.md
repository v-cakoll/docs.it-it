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
ms.openlocfilehash: ce9ce768e32434e0a1acd2fad67a0cdc99f49e18
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430146"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="65667-102">Metodo ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="65667-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="65667-103">Ottiene la firma della costante.</span><span class="sxs-lookup"><span data-stu-id="65667-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65667-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65667-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65667-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65667-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="65667-106">[in] La lunghezza del buffer che il `pcSig` punta al parametro.</span><span class="sxs-lookup"><span data-stu-id="65667-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="65667-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="65667-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="65667-108">[out] Buffer che archivia la firma.</span><span class="sxs-lookup"><span data-stu-id="65667-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65667-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="65667-109">Return Value</span></span>  
 <span data-ttu-id="65667-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="65667-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65667-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65667-111">Requirements</span></span>  
 <span data-ttu-id="65667-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="65667-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65667-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65667-113">See Also</span></span>  
 [<span data-ttu-id="65667-114">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="65667-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="65667-115">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="65667-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="65667-116">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="65667-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
