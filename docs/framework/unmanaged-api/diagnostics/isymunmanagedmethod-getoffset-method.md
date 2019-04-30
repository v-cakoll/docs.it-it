---
title: Metodo ISymUnmanagedMethod::GetOffset
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetOffset
helpviewer_keywords:
- GetOffset method, ISymUnmanagedMethod interface [.NET Framework debugging]
- ISymUnmanagedMethod::GetOffset method [.NET Framework debugging]
ms.assetid: 8bf3cb62-89bf-4159-ad53-de606aba89e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a42dc624d4de9cddebad287f6d90590f96b30272
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939659"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="12f92-102">Metodo ISymUnmanagedMethod::GetOffset</span><span class="sxs-lookup"><span data-stu-id="12f92-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="12f92-103">Restituisce l'offset all'interno di questo metodo che corrisponde a una determinata posizione all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="12f92-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12f92-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12f92-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12f92-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="12f92-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="12f92-106">[in] Puntatore al documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="12f92-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="12f92-107">[in] Riga del documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="12f92-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="12f92-108">[in] La colonna di documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="12f92-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="12f92-109">[out] Un puntatore a un `ULONG32` che riceve gli offset.</span><span class="sxs-lookup"><span data-stu-id="12f92-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="12f92-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="12f92-110">Return Value</span></span>  
 <span data-ttu-id="12f92-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="12f92-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12f92-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12f92-112">Requirements</span></span>  
 <span data-ttu-id="12f92-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="12f92-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f92-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12f92-114">See also</span></span>

- [<span data-ttu-id="12f92-115">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="12f92-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
