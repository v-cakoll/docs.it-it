---
title: Metodo ISymUnmanagedVariable::GetName
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedVariable.GetName
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a86a93db6058a8fda42e837388f7fa4cf5c765c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="d5817-102">Metodo ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="d5817-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="d5817-103">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="d5817-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5817-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d5817-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d5817-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d5817-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="d5817-106">[in] La lunghezza del buffer che il `pcchName` punta al parametro.</span><span class="sxs-lookup"><span data-stu-id="d5817-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="d5817-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="d5817-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="d5817-108">[out] Buffer che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="d5817-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5817-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d5817-109">Return Value</span></span>  
 <span data-ttu-id="d5817-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="d5817-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5817-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d5817-111">Requirements</span></span>  
 <span data-ttu-id="d5817-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d5817-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5817-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5817-113">See Also</span></span>  
 [<span data-ttu-id="d5817-114">ISymUnmanagedVariable (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="d5817-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
