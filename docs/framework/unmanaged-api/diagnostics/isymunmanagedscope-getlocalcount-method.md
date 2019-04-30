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
ms.openlocfilehash: 7b3c9c637bdaa0d0e18dbfd9655790ff5ebd46f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986189"
---
# <a name="isymunmanagedscopegetlocalcount-method"></a><span data-ttu-id="15f5f-102">Metodo ISymUnmanagedScope::GetLocalCount</span><span class="sxs-lookup"><span data-stu-id="15f5f-102">ISymUnmanagedScope::GetLocalCount Method</span></span>
<span data-ttu-id="15f5f-103">Ottiene un conteggio delle variabili locali definite all'interno di questo ambito.</span><span class="sxs-lookup"><span data-stu-id="15f5f-103">Gets a count of the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f5f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="15f5f-104">Syntax</span></span>  
  
```  
HRESULT GetLocalCount(  
    [out, retval] ULONG32 *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15f5f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="15f5f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="15f5f-106">[out] Un puntatore a un `ULONG32` che riceve il numero di variabili locali.</span><span class="sxs-lookup"><span data-stu-id="15f5f-106">[out] A pointer to a `ULONG32` that receives the count of local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15f5f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="15f5f-107">Return Value</span></span>  
 <span data-ttu-id="15f5f-108">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="15f5f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f5f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="15f5f-109">Requirements</span></span>  
 <span data-ttu-id="15f5f-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="15f5f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f5f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="15f5f-111">See also</span></span>

- [<span data-ttu-id="15f5f-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="15f5f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
