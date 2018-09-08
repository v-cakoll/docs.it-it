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
ms.openlocfilehash: 78d9e27299c9d7ed7d6cb9b09dd659ba081c5fde
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213027"
---
# <a name="isymunmanagedencupdateupdatesymbolstore2-method"></a><span data-ttu-id="c3a21-102">Metodo ISymUnmanagedENCUpdate::UpdateSymbolStore2</span><span class="sxs-lookup"><span data-stu-id="c3a21-102">ISymUnmanagedENCUpdate::UpdateSymbolStore2 Method</span></span>
<span data-ttu-id="c3a21-103">Consente a un compilatore di omettere le funzioni che non sono state modificate dal flusso di programma (PDB) del database, purché le informazioni sulla riga soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="c3a21-103">Allows a compiler to omit functions that have not been modified from the program database (PDB) stream, provided the line information meets the requirements.</span></span> <span data-ttu-id="c3a21-104">Le informazioni sulla riga corretto può essere determinati con le informazioni sulla riga PDB precedente e un delta per tutte le righe della funzione.</span><span class="sxs-lookup"><span data-stu-id="c3a21-104">The correct line information can be determined with the old PDB line information and one delta for all lines in the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a21-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3a21-105">Syntax</span></span>  
  
```  
HRESULT UpdateSymbolStore2(  
    [in]  IStream      *pIStream,  
    [in]  SYMLINEDELTA* pDeltaLines,  
    [in]  ULONG         cDeltaLines);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c3a21-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3a21-106">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="c3a21-107">[in] Un puntatore a un [IStream](/windows/desktop/api/objidl/nn-objidl-istream) che contiene le informazioni sulla riga.</span><span class="sxs-lookup"><span data-stu-id="c3a21-107">[in] A pointer to an [IStream](/windows/desktop/api/objidl/nn-objidl-istream) that contains the line information.</span></span>  
  
 `pDeltaLines`  
 <span data-ttu-id="c3a21-108">[in] Un puntatore a un [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) struttura che contiene le righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="c3a21-108">[in] A pointer to a [SYMLINEDELTA](../../../../docs/framework/unmanaged-api/diagnostics/symlinedelta-structure.md) structure that contains the lines that have changed.</span></span>  
  
 `cDeltaLines`  
 <span data-ttu-id="c3a21-109">[in] Oggetto `ULONG` che rappresenta il numero di righe che sono stati modificati.</span><span class="sxs-lookup"><span data-stu-id="c3a21-109">[in] A `ULONG` that represents the number of lines that have changed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3a21-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c3a21-110">Return Value</span></span>  
 <span data-ttu-id="c3a21-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="c3a21-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3a21-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3a21-112">Requirements</span></span>  
 <span data-ttu-id="c3a21-113">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c3a21-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3a21-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3a21-114">See Also</span></span>  
 [<span data-ttu-id="c3a21-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="c3a21-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
