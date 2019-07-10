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
ms.openlocfilehash: 50cd6d1e3666dd1f15c1e6a6b4f7dcb931b79d8d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777072"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="0baf4-102">Metodo ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="0baf4-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="0baf4-103">Fornisce il nome di file su disco dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="0baf4-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0baf4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0baf4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0baf4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="0baf4-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="0baf4-106">[in] Le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="0baf4-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0baf4-107">[out] Un puntatore alla variabile che riceve la lunghezza del nome restituito `szName`, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="0baf4-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="0baf4-108">[out] Puntatore alla variabile che riceve il nome del file dell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="0baf4-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0baf4-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0baf4-109">Return Value</span></span>  
 <span data-ttu-id="0baf4-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="0baf4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0baf4-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0baf4-111">Requirements</span></span>  
 <span data-ttu-id="0baf4-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0baf4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0baf4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0baf4-113">See also</span></span>

- [<span data-ttu-id="0baf4-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="0baf4-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
