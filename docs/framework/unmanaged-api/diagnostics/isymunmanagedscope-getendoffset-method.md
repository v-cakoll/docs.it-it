---
title: Metodo ISymUnmanagedScope::GetEndOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d13006bc5c09ed065ae1671ee75cf8dce066669d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426303"
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="80a6b-102">Metodo ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="80a6b-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="80a6b-103">Ottiene l'offset finale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="80a6b-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80a6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80a6b-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="80a6b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80a6b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="80a6b-106">[out] Un puntatore a un `ULONG32` che riceve l'offset finale.</span><span class="sxs-lookup"><span data-stu-id="80a6b-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="80a6b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="80a6b-107">Return Value</span></span>  
 <span data-ttu-id="80a6b-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="80a6b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80a6b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="80a6b-109">Requirements</span></span>  
 <span data-ttu-id="80a6b-110">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="80a6b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a6b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80a6b-111">See Also</span></span>  
 [<span data-ttu-id="80a6b-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="80a6b-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="80a6b-113">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="80a6b-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
