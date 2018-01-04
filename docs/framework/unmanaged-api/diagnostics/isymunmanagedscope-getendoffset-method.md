---
title: Metodo ISymUnmanagedScope::GetEndOffset
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope.GetEndOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64990dc2785a3804e683e281c823f459ec48e8a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="5045f-102">Metodo ISymUnmanagedScope::GetEndOffset</span><span class="sxs-lookup"><span data-stu-id="5045f-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="5045f-103">Ottiene l'offset finale per questo ambito.</span><span class="sxs-lookup"><span data-stu-id="5045f-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5045f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5045f-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5045f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5045f-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="5045f-106">[out] Un puntatore a un `ULONG32` che riceve l'offset finale.</span><span class="sxs-lookup"><span data-stu-id="5045f-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5045f-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5045f-107">Return Value</span></span>  
 <span data-ttu-id="5045f-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5045f-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5045f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5045f-109">Requirements</span></span>  
 <span data-ttu-id="5045f-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5045f-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5045f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5045f-111">See Also</span></span>  
 [<span data-ttu-id="5045f-112">Interfaccia ISymUnmanagedScope</span><span class="sxs-lookup"><span data-stu-id="5045f-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="5045f-113">Metodo GetStartOffset</span><span class="sxs-lookup"><span data-stu-id="5045f-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
