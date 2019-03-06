---
title: Metodo ISymUnmanagedWriter::RemapToken
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec4a486b9dfb72c05a9e614fca22626dd84a83f7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468460"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="5e8e5-102">Metodo ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="5e8e5-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="5e8e5-103">Notifica il writer di simboli che ha è stato modificato il mapping di un token di metadati come il costo veniva calcolato i metadati.</span><span class="sxs-lookup"><span data-stu-id="5e8e5-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="5e8e5-104">Se il writer di simboli è archiviato il token precedente nell'archivio dei simboli, è necessario aggiornare che il token archiviato con il nuovo valore oppure salvare la mappa per il lettore di simboli corrispondenti modificare il mapping durante la fase di lettura.</span><span class="sxs-lookup"><span data-stu-id="5e8e5-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e8e5-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e8e5-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e8e5-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e8e5-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="5e8e5-107">[in] Il token di metadati che è stato rimappato.</span><span class="sxs-lookup"><span data-stu-id="5e8e5-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="5e8e5-108">[in] Il nuovo token di metadati a cui `oldToken` è stata rimappata.</span><span class="sxs-lookup"><span data-stu-id="5e8e5-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e8e5-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5e8e5-109">Return Value</span></span>  
 <span data-ttu-id="5e8e5-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5e8e5-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e8e5-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e8e5-111">Requirements</span></span>  
 <span data-ttu-id="5e8e5-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5e8e5-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e8e5-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e8e5-113">See also</span></span>
- [<span data-ttu-id="5e8e5-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="5e8e5-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
