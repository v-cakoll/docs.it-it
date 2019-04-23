---
title: Metodo ISymUnmanagedMethod::GetParameters
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetParameters
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a757e3b28a94c96e28a5bab736a6820a83617a3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59101230"
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="7a627-102">Metodo ISymUnmanagedMethod::GetParameters</span><span class="sxs-lookup"><span data-stu-id="7a627-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="7a627-103">Ottiene i parametri per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="7a627-103">Gets the parameters for this method.</span></span> <span data-ttu-id="7a627-104">I parametri vengono restituiti nell'ordine in cui vengono definiti all'interno di firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="7a627-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a627-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a627-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a627-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="7a627-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="7a627-107">[in] Dimensione della matrice `params`.</span><span class="sxs-lookup"><span data-stu-id="7a627-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="7a627-108">[in] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer che è necessario per contenere i parametri.</span><span class="sxs-lookup"><span data-stu-id="7a627-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="7a627-109">[out] Puntatore al buffer che riceve i parametri.</span><span class="sxs-lookup"><span data-stu-id="7a627-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a627-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7a627-110">Return Value</span></span>  
 <span data-ttu-id="7a627-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="7a627-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a627-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a627-112">Requirements</span></span>  
 <span data-ttu-id="7a627-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="7a627-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a627-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a627-114">See also</span></span>

- [<span data-ttu-id="7a627-115">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="7a627-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
