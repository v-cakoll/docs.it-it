---
title: Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.UpdateSymbolStore2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2
helpviewer_keywords:
- ISymUnmanagedENCUpdate::UpdateSymbolStore2 method [.NET Framework debugging]
- UpdateSymbolStore2 method [.NET Framework debugging]
ms.assetid: 35588317-6184-485c-ab41-4b15fc1765d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82f2f335299cfd3041dcecc7d176cb77ce54ae96
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172133"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="55900-102">Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="55900-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="55900-103">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) del database, purché le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="55900-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="55900-104">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe della funzione.</span><span class="sxs-lookup"><span data-stu-id="55900-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55900-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55900-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55900-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="55900-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="55900-107">[in] Un puntatore a un [IStream](/windows/desktop/api/objidl/nn-objidl-istream) che contiene le informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="55900-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="55900-108">[in] Un puntatore a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) struttura che contiene le righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="55900-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="55900-109">[in] Oggetto `ULONG` che rappresenta il numero di righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="55900-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55900-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="55900-110">Return Value</span></span>  
 <span data-ttu-id="55900-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="55900-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55900-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55900-112">Requirements</span></span>  
 <span data-ttu-id="55900-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55900-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55900-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="55900-114">See also</span></span>

- [<span data-ttu-id="55900-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="55900-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
