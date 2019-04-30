---
title: Metodo ISymUnmanagedDocumentWriter::SetSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64982308c6eb7e9df4b94b4e123857c65939f044
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939750"
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="fba9d-102">Metodo ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="fba9d-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="fba9d-103">Imposta l'origine per un documento che viene scritto incorporata.</span><span class="sxs-lookup"><span data-stu-id="fba9d-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fba9d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fba9d-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fba9d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fba9d-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="fba9d-106">[in] Oggetto `ULONG32` che contiene la dimensione del `source` buffer.</span><span class="sxs-lookup"><span data-stu-id="fba9d-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="fba9d-107">[in] Buffer che archivia l'origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="fba9d-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fba9d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fba9d-108">Return Value</span></span>  
 <span data-ttu-id="fba9d-109">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="fba9d-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fba9d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fba9d-110">Requirements</span></span>  
 <span data-ttu-id="fba9d-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fba9d-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fba9d-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fba9d-112">See also</span></span>

- [<span data-ttu-id="fba9d-113">Interfaccia ISymUnmanagedDocumentWriter</span><span class="sxs-lookup"><span data-stu-id="fba9d-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
