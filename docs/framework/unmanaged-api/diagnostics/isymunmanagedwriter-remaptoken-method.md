---
title: Metodo ISymUnmanagedWriter::RemapToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86d6c78a49c55bdc9093241952bee00ee331696e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="ec198-102">Metodo ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="ec198-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="ec198-103">Notifica il writer di simboli che è stato rimappato un token di metadati come i metadati è stato creato.</span><span class="sxs-lookup"><span data-stu-id="ec198-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="ec198-104">Se il writer di simboli è archiviato il token precedente nell'archivio di simboli, deve aggiornare che il token con il nuovo valore oppure salvare la mappa per il lettore di simboli corrispondenti modificare il mapping durante la fase di lettura.</span><span class="sxs-lookup"><span data-stu-id="ec198-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec198-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ec198-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec198-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ec198-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="ec198-107">[in] Il token di metadati che è stato rimappato.</span><span class="sxs-lookup"><span data-stu-id="ec198-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="ec198-108">[in] Il nuovo token di metadati a cui `oldToken` rimappato.</span><span class="sxs-lookup"><span data-stu-id="ec198-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ec198-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ec198-109">Return Value</span></span>  
 <span data-ttu-id="ec198-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="ec198-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec198-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ec198-111">Requirements</span></span>  
 <span data-ttu-id="ec198-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ec198-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec198-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ec198-113">See Also</span></span>  
 [<span data-ttu-id="ec198-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="ec198-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
