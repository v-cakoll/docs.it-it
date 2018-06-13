---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariableCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariableCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariableCount method [.NET Framework debugging]
- GetLocalVariableCount method [.NET Framework debugging]
ms.assetid: 9777d8bb-4abc-4be8-aa7c-34f853eceb9c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7d557e2111a26c0865c20d8eb952c4d42b5604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436059"
---
# <a name="isymunmanagedencupdategetlocalvariablecount-method"></a><span data-ttu-id="1c07f-102">Metodo ISymUnmanagedENCUpdate::GetLocalVariableCount</span><span class="sxs-lookup"><span data-stu-id="1c07f-102">ISymUnmanagedENCUpdate::GetLocalVariableCount Method</span></span>
<span data-ttu-id="1c07f-103">Ottiene il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1c07f-103">Gets the number of local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c07f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1c07f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariableCount(  
    [in]  mdMethodDef  mdMethodToken,  
    [out] ULONG        *pcLocals);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c07f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1c07f-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="1c07f-106">[in] Il token di metadati dei metodi.</span><span class="sxs-lookup"><span data-stu-id="1c07f-106">[in] The metadata token of methods.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="1c07f-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="1c07f-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the number of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1c07f-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1c07f-108">Return Value</span></span>  
 <span data-ttu-id="1c07f-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1c07f-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c07f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1c07f-110">Requirements</span></span>  
 <span data-ttu-id="1c07f-111">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1c07f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c07f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c07f-112">See Also</span></span>  
 [<span data-ttu-id="1c07f-113">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="1c07f-113">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
