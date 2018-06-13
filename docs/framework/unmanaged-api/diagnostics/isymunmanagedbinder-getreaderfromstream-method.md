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
ms.openlocfilehash: 4c5d3d1b868849d17b2068eecfcfeea0f1e598f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428517"
---
# <a name="isymunmanagedbindergetreaderfromstream-method"></a><span data-ttu-id="a5b9b-102">Metodo ISymUnmanagedBinder::GetReaderFromStream</span><span class="sxs-lookup"><span data-stu-id="a5b9b-102">ISymUnmanagedBinder::GetReaderFromStream Method</span></span>
<span data-ttu-id="a5b9b-103">Data un'interfaccia di metadati e un flusso che contiene l'archivio dei simboli, restituisce il [ISymUnmanagedReader](isymunmanagedreader-interface.md) simboli di struttura che verrà letto il debug dall'archivio di simboli specificato.</span><span class="sxs-lookup"><span data-stu-id="a5b9b-103">Given a metadata interface and a stream that contains the symbol store, returns the correct [ISymUnmanagedReader](isymunmanagedreader-interface.md) structure that will read the debugging symbols from the given symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a5b9b-104">Syntax</span></span>  
  
```  
HRESULT GetReaderFromStream(  
    [in]  IUnknown  *importer,  
    [in]  IStream   *pstream,  
    [out,retval] ISymUnmanagedReader **pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5b9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a5b9b-105">Parameters</span></span>  
 `importer`  
 <span data-ttu-id="a5b9b-106">[in] Un puntatore all'interfaccia di importazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="a5b9b-106">[in] A pointer to the metadata import interface.</span></span>  
  
 `pstream`  
 <span data-ttu-id="a5b9b-107">[in] Puntatore al flusso che contiene l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="a5b9b-107">[in] A pointer to the stream that contains the symbol store.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="a5b9b-108">[out] Un puntatore che viene impostato sull'oggetto restituito [ISymUnmanagedReader](isymunmanagedreader-interface.md) interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a5b9b-108">[out] A pointer that is set to the returned [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5b9b-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a5b9b-109">Return Value</span></span>  
 <span data-ttu-id="a5b9b-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a5b9b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b9b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a5b9b-111">Requirements</span></span>  
 <span data-ttu-id="a5b9b-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a5b9b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b9b-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a5b9b-113">See Also</span></span>  
 [<span data-ttu-id="a5b9b-114">Interfaccia ISymUnmanagedBinder</span><span class="sxs-lookup"><span data-stu-id="a5b9b-114">ISymUnmanagedBinder Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)
