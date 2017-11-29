---
title: Metodo ISymUnmanagedMethod::GetNamespace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetNamespace
helpviewer_keywords:
- ISymUnmanagedMethod::GetNamespace method [.NET Framework debugging]
- GetNamespace method [.NET Framework debugging]
ms.assetid: 7fbbac42-b966-406d-9ae9-67bf3aea74ce
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5aff1bcd98e67f381340ed81a187db591c0986be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetnamespace-method"></a><span data-ttu-id="8683b-102">Metodo ISymUnmanagedMethod::GetNamespace</span><span class="sxs-lookup"><span data-stu-id="8683b-102">ISymUnmanagedMethod::GetNamespace Method</span></span>
<span data-ttu-id="8683b-103">Ottiene lo spazio dei nomi all'interno del quale è definito questo metodo.</span><span class="sxs-lookup"><span data-stu-id="8683b-103">Gets the namespace within which this method is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8683b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8683b-104">Syntax</span></span>  
  
```  
HRESULT GetNamespace(  
   [out] ISymUnmanagedNamespace  **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8683b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8683b-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="8683b-106">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="8683b-106">[out] A pointer that is set to the returned [ISymUnmanagedNamespace](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8683b-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8683b-107">Return Value</span></span>  
 <span data-ttu-id="8683b-108">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8683b-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8683b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8683b-109">Requirements</span></span>  
 <span data-ttu-id="8683b-110">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8683b-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8683b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8683b-111">See Also</span></span>  
 [<span data-ttu-id="8683b-112">ISymUnmanagedMethod (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8683b-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
