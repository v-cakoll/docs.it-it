---
title: Metodo ISymUnmanagedDocument::HasEmbeddedSource
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.HasEmbeddedSource
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::HasEmbeddedSource
helpviewer_keywords:
- HasEmbeddedSource method [.NET Framework debugging]
- ISymUnmanagedDocument::HasEmbeddedSource method [.NET Framework debugging]
ms.assetid: 385fc4d3-365c-4645-b7b0-6c4c5344b79f
topic_type:
- apiref
ms.openlocfilehash: 533d8a5481fe9ba7e7e65775229156a9cc3cf4d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449117"
---
# <a name="isymunmanageddocumenthasembeddedsource-method"></a><span data-ttu-id="a355a-102">Metodo ISymUnmanagedDocument::HasEmbeddedSource</span><span class="sxs-lookup"><span data-stu-id="a355a-102">ISymUnmanagedDocument::HasEmbeddedSource Method</span></span>
<span data-ttu-id="a355a-103">Restituisce `true` se l'origine del documento è incorporata nei simboli di debug; in caso contrario, restituisce `false`.</span><span class="sxs-lookup"><span data-stu-id="a355a-103">Returns `true` if the document has source embedded in the debugging symbols; otherwise, returns `false`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a355a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a355a-104">Syntax</span></span>  
  
```cpp  
HRESULT HasEmbeddedSource(  
   [out, retval]  BOOL  *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a355a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a355a-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="a355a-106">out Puntatore a una variabile che indica se l'origine del documento è incorporata nei simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="a355a-106">[out] A pointer to a variable that indicates whether the document has source embedded in the debugging symbols.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a355a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a355a-107">Return Value</span></span>  
 <span data-ttu-id="a355a-108">S_OK se il metodo ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a355a-108">S_OK if the method succeeds.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a355a-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a355a-109">See also</span></span>

- [<span data-ttu-id="a355a-110">Interfaccia ISymUnmanagedDocument</span><span class="sxs-lookup"><span data-stu-id="a355a-110">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
