---
title: Metodo ISymUnmanagedWriter::OpenNamespace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.OpenNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77d50f6bac87d5a110b53a69044f96f547c51904
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="f3940-102">Metodo ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="f3940-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="f3940-103">Apre un nuovo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f3940-103">Opens a new namespace.</span></span> <span data-ttu-id="f3940-104">Chiamare questo metodo prima di definire i metodi o le variabili che occupano uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f3940-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="f3940-105">Spazi dei nomi possono essere nidificati.</span><span class="sxs-lookup"><span data-stu-id="f3940-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3940-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f3940-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f3940-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="f3940-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f3940-108">[in] Puntatore al nome del nuovo spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="f3940-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3940-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f3940-109">Return Value</span></span>  
 <span data-ttu-id="f3940-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f3940-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3940-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f3940-111">Requirements</span></span>  
 <span data-ttu-id="f3940-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f3940-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3940-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3940-113">See Also</span></span>  
 [<span data-ttu-id="f3940-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f3940-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="f3940-115">Metodo CloseNamespace</span><span class="sxs-lookup"><span data-stu-id="f3940-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
