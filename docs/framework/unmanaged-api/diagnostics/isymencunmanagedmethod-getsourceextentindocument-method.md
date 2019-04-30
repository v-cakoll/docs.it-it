---
title: Metodo ISymENCUnmanagedMethod::GetSourceExtentInDocument
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 442584cffe4b4ae44702892587e261d41abf4e8a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940244"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="c6f08-102">Metodo ISymENCUnmanagedMethod::GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="c6f08-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="c6f08-103">Ottiene il valore più piccolo start riga e la riga finale per il metodo in un documento specifico.</span><span class="sxs-lookup"><span data-stu-id="c6f08-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6f08-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6f08-104">Syntax</span></span>  
  
```  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6f08-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6f08-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="c6f08-106">[in] Puntatore al documento.</span><span class="sxs-lookup"><span data-stu-id="c6f08-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="c6f08-107">[out] Un puntatore a un `ULONG32` che riceve la riga iniziale.</span><span class="sxs-lookup"><span data-stu-id="c6f08-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="c6f08-108">[out] Un puntatore a un `ULONG32` che riceve la riga finale.</span><span class="sxs-lookup"><span data-stu-id="c6f08-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6f08-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c6f08-109">Return Value</span></span>  
 <span data-ttu-id="c6f08-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c6f08-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6f08-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6f08-111">Requirements</span></span>  
 <span data-ttu-id="c6f08-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c6f08-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6f08-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6f08-113">See also</span></span>

- [<span data-ttu-id="c6f08-114">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="c6f08-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
