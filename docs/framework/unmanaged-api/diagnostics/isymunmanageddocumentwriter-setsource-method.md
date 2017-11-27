---
title: Metodo ISymUnmanagedDocumentWriter::SetSource
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetSource
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetSource
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetSource method [.NET Framework debugging]
- SetSource method [.NET Framework debugging]
ms.assetid: ea5b9d9f-ff06-4bd3-8de5-6435343aba59
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 74b917ff4c2853eb31625af2ab1d2c64ced613e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentwritersetsource-method"></a><span data-ttu-id="07a48-102">Metodo ISymUnmanagedDocumentWriter::SetSource</span><span class="sxs-lookup"><span data-stu-id="07a48-102">ISymUnmanagedDocumentWriter::SetSource Method</span></span>
<span data-ttu-id="07a48-103">Imposta l'origine per un documento che viene scritto incorporata.</span><span class="sxs-lookup"><span data-stu-id="07a48-103">Sets embedded source for a document that is being written.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07a48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07a48-104">Syntax</span></span>  
  
```  
HRESULT SetSource(  
    [in]  ULONG32  sourceSize,  
    [in, size_is(sourceSize)] BYTE  source[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07a48-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="07a48-105">Parameters</span></span>  
 `sourceSize`  
 <span data-ttu-id="07a48-106">[in] Oggetto `ULONG32` che contiene la dimensione del `source` buffer.</span><span class="sxs-lookup"><span data-stu-id="07a48-106">[in] A `ULONG32` that contains the size of the `source` buffer.</span></span>  
  
 `source`  
 <span data-ttu-id="07a48-107">[in] Buffer che archivia origine incorporata.</span><span class="sxs-lookup"><span data-stu-id="07a48-107">[in] The buffer that stores the embedded source.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07a48-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="07a48-108">Return Value</span></span>  
 <span data-ttu-id="07a48-109">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="07a48-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07a48-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07a48-110">Requirements</span></span>  
 <span data-ttu-id="07a48-111">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="07a48-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a48-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07a48-112">See Also</span></span>  
 [<span data-ttu-id="07a48-113">ISymUnmanagedDocumentWriter (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="07a48-113">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)
