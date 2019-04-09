---
title: Metodo ISymUnmanagedReader2::GetMethodsInDocument
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodsInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument
helpviewer_keywords:
- ISymUnmanagedReader2::GetMethodsInDocument method [.NET Framework debugging]
- GetMethodsInDocument method [.NET Framework debugging]
ms.assetid: c7ae84d6-81e8-4cb7-a1f9-d48b6cde5d79
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28b240159c36b03b2c476f56f7e6ad7b33f20649
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142346"
---
# <a name="isymunmanagedreader2getmethodsindocument-method"></a><span data-ttu-id="af33a-102">Metodo ISymUnmanagedReader2::GetMethodsInDocument</span><span class="sxs-lookup"><span data-stu-id="af33a-102">ISymUnmanagedReader2::GetMethodsInDocument Method</span></span>
<span data-ttu-id="af33a-103">Ottiene i metodi che contiene informazioni sulla riga del documento specificato.</span><span class="sxs-lookup"><span data-stu-id="af33a-103">Gets every method that has line information in the provided document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af33a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af33a-104">Syntax</span></span>  
  
```  
HRESULT GetMethodsInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is(cMethod),  
        length_is(*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af33a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af33a-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="af33a-106">[in] Puntatore al documento.</span><span class="sxs-lookup"><span data-stu-id="af33a-106">[in] A pointer to the document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="af33a-107">[in] Oggetto `ULONG32` che indica le dimensioni del `pRetVal` matrice.</span><span class="sxs-lookup"><span data-stu-id="af33a-107">[in] A `ULONG32` that indicates the size of the  `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="af33a-108">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessarie per contenere i metodi.</span><span class="sxs-lookup"><span data-stu-id="af33a-108">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the methods.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="af33a-109">[out] Puntatore al buffer che riceve i metodi.</span><span class="sxs-lookup"><span data-stu-id="af33a-109">[out] A pointer to the buffer that receives the methods.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af33a-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af33a-110">Return Value</span></span>  
 <span data-ttu-id="af33a-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="af33a-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af33a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af33a-112">Requirements</span></span>  
 <span data-ttu-id="af33a-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="af33a-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af33a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af33a-114">See also</span></span>

- [<span data-ttu-id="af33a-115">Interfaccia ISymUnmanagedReader2</span><span class="sxs-lookup"><span data-stu-id="af33a-115">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
