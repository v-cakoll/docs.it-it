---
title: Metodo ISymUnmanagedReader::GetDocuments
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0bcb0efab3b61f55bd5fdd3405799c7ac78ee521
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424651"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="a8366-102">Metodo ISymUnmanagedReader::GetDocuments</span><span class="sxs-lookup"><span data-stu-id="a8366-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="a8366-103">Restituisce una matrice di tutti i documenti definiti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="a8366-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8366-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a8366-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8366-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a8366-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="a8366-106">[in] Dimensione della matrice `pDocs`.</span><span class="sxs-lookup"><span data-stu-id="a8366-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="a8366-107">[out] Puntatore a una variabile che riceve la lunghezza della matrice.</span><span class="sxs-lookup"><span data-stu-id="a8366-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="a8366-108">[out] Puntatore a una variabile che riceve la matrice del documento.</span><span class="sxs-lookup"><span data-stu-id="a8366-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8366-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a8366-109">Return Value</span></span>  
 <span data-ttu-id="a8366-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a8366-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8366-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a8366-111">Requirements</span></span>  
 <span data-ttu-id="a8366-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a8366-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8366-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a8366-113">See Also</span></span>  
 [<span data-ttu-id="a8366-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="a8366-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
