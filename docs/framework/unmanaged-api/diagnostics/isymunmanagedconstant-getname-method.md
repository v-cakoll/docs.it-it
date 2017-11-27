---
title: Metodo ISymUnmanagedConstant::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedConstant.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e4b6dc3eb79f351041687586327e4e095225acf4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="5dcc0-102">Metodo ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="5dcc0-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="5dcc0-103">Ottiene il nome della costante.</span><span class="sxs-lookup"><span data-stu-id="5dcc0-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dcc0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5dcc0-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5dcc0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5dcc0-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5dcc0-106">[in] La lunghezza del buffer che il `szName` punta al parametro.</span><span class="sxs-lookup"><span data-stu-id="5dcc0-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5dcc0-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="5dcc0-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="5dcc0-108">[out] Buffer che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="5dcc0-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5dcc0-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5dcc0-109">Return Value</span></span>  
 <span data-ttu-id="5dcc0-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5dcc0-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dcc0-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5dcc0-111">Requirements</span></span>  
 <span data-ttu-id="5dcc0-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5dcc0-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dcc0-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dcc0-113">See Also</span></span>  
 [<span data-ttu-id="5dcc0-114">ISymUnmanagedConstant (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5dcc0-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="5dcc0-115">GetSignature (metodo)</span><span class="sxs-lookup"><span data-stu-id="5dcc0-115">GetSignature Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getsignature-method.md)  
 [<span data-ttu-id="5dcc0-116">GetValue (metodo)</span><span class="sxs-lookup"><span data-stu-id="5dcc0-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
