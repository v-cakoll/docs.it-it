---
title: Metodo ISymUnmanagedVariable::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9abbfa14777c5a5f5a77fa91db0fbafee095ba9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429237"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="997c5-102">Metodo ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="997c5-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="997c5-103">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="997c5-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="997c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="997c5-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="997c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="997c5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="997c5-106">[in] La lunghezza del buffer che il `pcchName` punta al parametro.</span><span class="sxs-lookup"><span data-stu-id="997c5-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="997c5-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="997c5-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="997c5-108">[out] Buffer che archivia il nome.</span><span class="sxs-lookup"><span data-stu-id="997c5-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="997c5-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="997c5-109">Return Value</span></span>  
 <span data-ttu-id="997c5-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="997c5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="997c5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="997c5-111">Requirements</span></span>  
 <span data-ttu-id="997c5-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="997c5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="997c5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="997c5-113">See Also</span></span>  
 [<span data-ttu-id="997c5-114">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="997c5-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
