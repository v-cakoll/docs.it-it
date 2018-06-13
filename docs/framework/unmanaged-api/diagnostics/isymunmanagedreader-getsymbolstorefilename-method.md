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
ms.openlocfilehash: b36f4007f286938169cc5d583908493916b9e6f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425340"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="4bfb7-102">Metodo ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="4bfb7-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="4bfb7-103">Fornisce il nome di file su disco dell'archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="4bfb7-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfb7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4bfb7-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4bfb7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4bfb7-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="4bfb7-106">[in] Le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="4bfb7-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="4bfb7-107">[out] Un puntatore a una variabile che riceve la lunghezza del nome restituito `szName`, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="4bfb7-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="4bfb7-108">[out] Puntatore a una variabile che riceve il nome del file dell'archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="4bfb7-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bfb7-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4bfb7-109">Return Value</span></span>  
 <span data-ttu-id="4bfb7-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4bfb7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bfb7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4bfb7-111">Requirements</span></span>  
 <span data-ttu-id="4bfb7-112">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4bfb7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfb7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bfb7-113">See Also</span></span>  
 [<span data-ttu-id="4bfb7-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="4bfb7-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
