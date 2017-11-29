---
title: Metodo ISymUnmanagedWriter::OpenNamespace
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.OpenNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::OpenNamespace
helpviewer_keywords:
- ISymUnmanagedWriter::OpenNamespace method [.NET Framework debugging]
- OpenNamespace method [.NET Framework debugging]
ms.assetid: 426f4e4f-e60d-4ad1-b546-a10e3c55c283
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e3dffd9605bd238446156d7a32e8e668ddd80916
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriteropennamespace-method"></a><span data-ttu-id="17d99-102">Metodo ISymUnmanagedWriter::OpenNamespace</span><span class="sxs-lookup"><span data-stu-id="17d99-102">ISymUnmanagedWriter::OpenNamespace Method</span></span>
<span data-ttu-id="17d99-103">Apre un nuovo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="17d99-103">Opens a new namespace.</span></span> <span data-ttu-id="17d99-104">Chiamare questo metodo prima di definire i metodi o le variabili che occupano uno spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="17d99-104">Call this method before defining methods or variables that occupy a namespace.</span></span> <span data-ttu-id="17d99-105">Spazi dei nomi possono essere nidificati.</span><span class="sxs-lookup"><span data-stu-id="17d99-105">Namespaces can be nested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d99-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="17d99-106">Syntax</span></span>  
  
```  
HRESULT OpenNamespace(  
    [in] const WCHAR *name);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17d99-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="17d99-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="17d99-108">[in] Puntatore al nome del nuovo spazio dei nomi specificato.</span><span class="sxs-lookup"><span data-stu-id="17d99-108">[in] A pointer to the name of the new namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17d99-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="17d99-109">Return Value</span></span>  
 <span data-ttu-id="17d99-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="17d99-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d99-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="17d99-111">Requirements</span></span>  
 <span data-ttu-id="17d99-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="17d99-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17d99-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17d99-113">See Also</span></span>  
 [<span data-ttu-id="17d99-114">ISymUnmanagedWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="17d99-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="17d99-115">CloseNamespace (metodo)</span><span class="sxs-lookup"><span data-stu-id="17d99-115">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)
