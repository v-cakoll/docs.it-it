---
title: Metodo ISymUnmanagedScope::GetLocalCount
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocalCount
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocalCount
helpviewer_keywords:
- GetLocalCount method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocalCount method [.NET Framework debugging]
ms.assetid: 3ede8fb5-f655-4088-8e19-9c53812588a8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 809b9033c784954374065a901f34f7542f41e7ab
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549941"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="0b741-102">Metodo ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="0b741-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="0b741-103">Ottiene un conteggio delle variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="0b741-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b741-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b741-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b741-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0b741-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="0b741-106">[out] Un puntatore a un `ULONG32` che riceve il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="0b741-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b741-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0b741-107">Return Value</span></span>  
 <span data-ttu-id="0b741-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0b741-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b741-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b741-109">Requirements</span></span>  
 <span data-ttu-id="0b741-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0b741-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b741-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b741-111">See also</span></span>
- [<span data-ttu-id="0b741-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="0b741-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
