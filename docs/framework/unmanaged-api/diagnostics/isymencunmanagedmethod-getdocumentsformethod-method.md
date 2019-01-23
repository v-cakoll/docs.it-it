---
title: Metodo ISymENCUnmanagedMethod::GetDocumentsForMethod
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetDocumentsForMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetDocumentsForMethod
helpviewer_keywords:
- GetDocumentsForMethod method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetDocumentsForMethod method [.NET Framework debugging]
ms.assetid: bd6ccde5-d578-48d8-abed-b474fbd48d13
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd294037774721839b0c4f1f09bdc2a6e3b87841
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562674"
---
# <a name="isymencunmanagedmethodgetdocumentsformethod-method"></a><span data-ttu-id="203ac-102">Metodo ISymENCUnmanagedMethod::GetDocumentsForMethod</span><span class="sxs-lookup"><span data-stu-id="203ac-102">ISymENCUnmanagedMethod::GetDocumentsForMethod Method</span></span>
<span data-ttu-id="203ac-103">Ottiene i documenti che questo metodo è incluse righe.</span><span class="sxs-lookup"><span data-stu-id="203ac-103">Gets the documents that this method has lines in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="203ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="203ac-104">Syntax</span></span>  
  
```  
HRESULT GetDocumentsForMethod(  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,   
    [in, size_is(cDocs)] ISymUnmanagedDocument* documents[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="203ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="203ac-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="203ac-106">[in] La lunghezza del buffer a cui punta `pcDocs`.</span><span class="sxs-lookup"><span data-stu-id="203ac-106">[in] The length of the buffer pointed to by `pcDocs`.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="203ac-107">[out] Un puntatore a un `ULONG32` che riceve le dimensioni, in caratteri, del buffer necessaria per contenere i documenti.</span><span class="sxs-lookup"><span data-stu-id="203ac-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the documents.</span></span>  
  
 `documents`  
 <span data-ttu-id="203ac-108">[in] Buffer che contiene i documenti.</span><span class="sxs-lookup"><span data-stu-id="203ac-108">[in] The buffer that contains the documents.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="203ac-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="203ac-109">Return Value</span></span>  
 <span data-ttu-id="203ac-110">S_OK se il metodo ha esito positivo; in caso contrario, un codice di errore.</span><span class="sxs-lookup"><span data-stu-id="203ac-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="203ac-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="203ac-111">Requirements</span></span>  
 <span data-ttu-id="203ac-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="203ac-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="203ac-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="203ac-113">See also</span></span>
- [<span data-ttu-id="203ac-114">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="203ac-114">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)
