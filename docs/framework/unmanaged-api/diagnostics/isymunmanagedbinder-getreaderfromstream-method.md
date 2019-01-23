---
title: Metodo ISymUnmanagedBinder::GetReaderFromStream
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder.GetReaderFromStream
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder::GetReaderFromStream
helpviewer_keywords:
- ISymUnmanagedBinder::GetReaderFromStream method [.NET Framework debugging]
- GetReaderFromStream method [.NET Framework debugging]
ms.assetid: aa38efd4-de7e-4482-a5d3-adc152093460
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: af4e9124140c2b311fb2c10800200f5d4d8dc679
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545764"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="e2171-102">Metodo ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="e2171-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="e2171-103">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il valore corretto [ISymUnmanagedReader](isymunmanagedreader-interface.md) struttura che leggerà il debug di simboli dall'archivio di simbolo specificato.</span><span class="sxs-lookup"><span data-stu-id="e2171-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2171-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2171-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2171-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e2171-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="e2171-106">[in] Un puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="e2171-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="e2171-107">[in] Puntatore al flusso contenente l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="e2171-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e2171-108">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e2171-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e2171-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="e2171-109">Return Value</span></span>  
 <span data-ttu-id="e2171-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="e2171-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2171-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e2171-111">Requirements</span></span>  
 <span data-ttu-id="e2171-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e2171-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2171-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2171-113">See also</span></span>
- [<span data-ttu-id="e2171-114">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="e2171-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
