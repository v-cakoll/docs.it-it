---
title: Metodo ISymUnmanagedWriter::CloseNamespace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.CloseNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::CloseNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::CloseNamespace method [.NET Framework debugging]
- CloseNamespace method [.NET Framework debugging]
ms.assetid: 7f74d9c5-1377-4958-b842-6306d611cbd5
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 364c2a851371ea147a61a49826efe702140c5b2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosenamespace-method"></a><span data-ttu-id="5f207-102">Metodo ISymUnmanagedWriter::CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="5f207-102">ISymUnmanagedWriter::CloseNamespace Method</span></span>
<span data-ttu-id="5f207-103">Chiude l'ultimo aperto dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="5f207-103">Closes the most recently opened namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f207-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5f207-104">Syntax</span></span>  
  
```  
HRESULT CloseNamespace();  
```  
  
## <a name="return-value"></a><span data-ttu-id="5f207-105">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5f207-105">Return Value</span></span>  
 <span data-ttu-id="5f207-106">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5f207-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f207-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f207-107">Requirements</span></span>  
 <span data-ttu-id="5f207-108">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5f207-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f207-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f207-109">See Also</span></span>  
 [<span data-ttu-id="5f207-110">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="5f207-110">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="5f207-111">Metodo OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="5f207-111">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)
