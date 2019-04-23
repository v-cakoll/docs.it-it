---
title: Metodo ISymUnmanagedReader::GetSymbolStoreFileName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 147b33a3f49f9163daea776779ca26f62561a84e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170378"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="5027e-102">Metodo ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="5027e-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="5027e-103">Fornisce il nome di file su disco dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="5027e-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5027e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5027e-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5027e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5027e-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="5027e-106">[in] Le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="5027e-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="5027e-107">[out] Un puntatore alla variabile che riceve la lunghezza del nome restituito `szName`, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="5027e-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="5027e-108">[out] Puntatore alla variabile che riceve il nome del file dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="5027e-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5027e-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5027e-109">Return Value</span></span>  
 <span data-ttu-id="5027e-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="5027e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5027e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5027e-111">Requirements</span></span>  
 <span data-ttu-id="5027e-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5027e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5027e-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5027e-113">See also</span></span>

- [<span data-ttu-id="5027e-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="5027e-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
