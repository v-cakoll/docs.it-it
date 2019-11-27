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
ms.openlocfilehash: 9e441d4ff39632d9381e445ee99249d04539ad87
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427876"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="9a40f-102">Metodo ISymUnmanagedWriter::RemapToken</span><span class="sxs-lookup"><span data-stu-id="9a40f-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="9a40f-103">Notifica al writer di simboli che è stato eseguito il mapping di un token di metadati durante la creazione dei metadati.</span><span class="sxs-lookup"><span data-stu-id="9a40f-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="9a40f-104">Se il writer di simboli ha archiviato il token precedente nell'archivio dei simboli, deve aggiornare il token archiviato con il nuovo valore oppure salvare la mappa affinché il lettore di simboli corrispondente venga rimappato durante la fase di lettura.</span><span class="sxs-lookup"><span data-stu-id="9a40f-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a40f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9a40f-105">Syntax</span></span>  
  
```cpp  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a40f-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="9a40f-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="9a40f-107">in Token di metadati di cui è stato eseguito il mapping.</span><span class="sxs-lookup"><span data-stu-id="9a40f-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="9a40f-108">in Nuovo token di metadati a cui `oldToken` stato rimappato.</span><span class="sxs-lookup"><span data-stu-id="9a40f-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a40f-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="9a40f-109">Return Value</span></span>  
 <span data-ttu-id="9a40f-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="9a40f-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a40f-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9a40f-111">Requirements</span></span>  
 <span data-ttu-id="9a40f-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="9a40f-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a40f-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a40f-113">See also</span></span>

- [<span data-ttu-id="9a40f-114">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="9a40f-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
