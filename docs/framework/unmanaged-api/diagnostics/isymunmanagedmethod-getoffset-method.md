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
ms.openlocfilehash: 6d88e9279f70c36fd8a9c626972e33305cded5fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33424391"
---
# <a name="isymunmanagedmethodgetoffset-method"></a><span data-ttu-id="3910a-102">Metodo ISymUnmanagedMethod::GetOffset</span><span class="sxs-lookup"><span data-stu-id="3910a-102">ISymUnmanagedMethod::GetOffset Method</span></span>
<span data-ttu-id="3910a-103">Restituisce l'offset all'interno del metodo che corrisponde a una posizione specifica all'interno di un documento.</span><span class="sxs-lookup"><span data-stu-id="3910a-103">Returns the offset within this method that corresponds to a given position within a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3910a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3910a-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32                 line,  
    [in]  ULONG32                 column,  
    [out, retval] ULONG32*        pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3910a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3910a-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="3910a-106">[in] Puntatore al documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="3910a-106">[in] A pointer to the document for which the offset is requested.</span></span>  
  
 `line`  
 <span data-ttu-id="3910a-107">[in] Riga del documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="3910a-107">[in] The document line for which the offset is requested.</span></span>  
  
 `column`  
 <span data-ttu-id="3910a-108">[in] La colonna di documento per cui è richiesto l'offset.</span><span class="sxs-lookup"><span data-stu-id="3910a-108">[in] The document column for which the offset is requested.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="3910a-109">[out] Un puntatore a un `ULONG32` che riceve gli offset.</span><span class="sxs-lookup"><span data-stu-id="3910a-109">[out] A pointer to a `ULONG32` that receives the offsets.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3910a-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3910a-110">Return Value</span></span>  
 <span data-ttu-id="3910a-111">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3910a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3910a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3910a-112">Requirements</span></span>  
 <span data-ttu-id="3910a-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3910a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3910a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3910a-114">See Also</span></span>  
 [<span data-ttu-id="3910a-115">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="3910a-115">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
