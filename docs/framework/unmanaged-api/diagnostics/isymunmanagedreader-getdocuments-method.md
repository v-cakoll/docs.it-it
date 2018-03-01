---
title: Metodo ISymUnmanagedReader::GetDocuments
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
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 423267f30459c409cc1bba6e0dee53b31a2783cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="c8f88-102">Metodo ISymUnmanagedReader::GetDocuments</span><span class="sxs-lookup"><span data-stu-id="c8f88-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="c8f88-103">Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="c8f88-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8f88-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8f88-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8f88-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="c8f88-106">[in] Dimensione della matrice `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="c8f88-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="c8f88-107">[out] Puntatore a una variabile che riceve la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="c8f88-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="c8f88-108">[out] Puntatore a una variabile che riceve la matrice del documento.</span><span class="sxs-lookup"><span data-stu-id="c8f88-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8f88-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8f88-109">Return Value</span></span>  
 <span data-ttu-id="c8f88-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c8f88-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8f88-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8f88-111">Requirements</span></span>  
 <span data-ttu-id="c8f88-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c8f88-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f88-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8f88-113">See Also</span></span>  
 [<span data-ttu-id="c8f88-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="c8f88-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
