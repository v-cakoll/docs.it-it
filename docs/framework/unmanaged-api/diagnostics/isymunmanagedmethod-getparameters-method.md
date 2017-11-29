---
title: Metodo ISymUnmanagedMethod::GetParameters
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetParameters
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetParameters
helpviewer_keywords:
- ISymUnmanagedMethod::GetParameters method [.NET Framework debugging]
- GetParameters method [.NET Framework debugging]
ms.assetid: 3a8074f1-facc-4a3f-bb9b-d6574fc2fc74
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 057cafc5270eeb82b4c9b9becac59ea45ea21371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetparameters-method"></a><span data-ttu-id="9a11a-102">Metodo ISymUnmanagedMethod::GetParameters</span><span class="sxs-lookup"><span data-stu-id="9a11a-102">ISymUnmanagedMethod::GetParameters Method</span></span>
<span data-ttu-id="9a11a-103">Ottiene i parametri per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="9a11a-103">Gets the parameters for this method.</span></span> <span data-ttu-id="9a11a-104">I parametri vengono restituiti nell'ordine in cui sono definiti all'interno della firma del metodo.</span><span class="sxs-lookup"><span data-stu-id="9a11a-104">The parameters are returned in the order in which they are defined within the method's signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a11a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a11a-105">Syntax</span></span>  
  
```  
HRESULT GetParameters(  
    [in]  ULONG32  cParams,  
    [out] ULONG32  *pcParams,  
    [out, size_is(cParams),  
        length_is(*pcParams)] ISymUnmanagedVariable*  params[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a11a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a11a-106">Parameters</span></span>  
 `cParams`  
 <span data-ttu-id="9a11a-107">[in] Dimensione della matrice `params`.</span><span class="sxs-lookup"><span data-stu-id="9a11a-107">[in] The size of the `params` array.</span></span>  
  
 `pcParams`  
 <span data-ttu-id="9a11a-108">[in] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer che è necessario per contenere i parametri.</span><span class="sxs-lookup"><span data-stu-id="9a11a-108">[in] A pointer to a `ULONG32` that receives the size of the buffer that is required to contain the parameters.</span></span>  
  
 `params`  
 <span data-ttu-id="9a11a-109">[out] Puntatore al buffer che riceve i parametri.</span><span class="sxs-lookup"><span data-stu-id="9a11a-109">[out] A pointer to the buffer that receives the parameters.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a11a-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a11a-110">Return Value</span></span>  
 <span data-ttu-id="9a11a-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9a11a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a11a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a11a-112">Requirements</span></span>  
 <span data-ttu-id="9a11a-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a11a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a11a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a11a-114">See Also</span></span>  
 [<span data-ttu-id="9a11a-115">ISymUnmanagedMethod (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="9a11a-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
