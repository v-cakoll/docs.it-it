---
title: Metodo ISymUnmanagedReader::GetSymbolStoreFileName
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1646e8fa5f04da56e4489dca9581e9dc56e01d0e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="937ef-102">Metodo ISymUnmanagedReader::GetSymbolStoreFileName</span><span class="sxs-lookup"><span data-stu-id="937ef-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="937ef-103">Fornisce il nome di file su disco dell'archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="937ef-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="937ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="937ef-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="937ef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="937ef-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="937ef-106">[in] Le dimensioni del `szName` buffer.</span><span class="sxs-lookup"><span data-stu-id="937ef-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="937ef-107">[out] Un puntatore a una variabile che riceve la lunghezza del nome restituito `szName`, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="937ef-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="937ef-108">[out] Puntatore a una variabile che riceve il nome del file dell'archivio di simboli.</span><span class="sxs-lookup"><span data-stu-id="937ef-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="937ef-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="937ef-109">Return Value</span></span>  
 <span data-ttu-id="937ef-110">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="937ef-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="937ef-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="937ef-111">Requirements</span></span>  
 <span data-ttu-id="937ef-112">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="937ef-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="937ef-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="937ef-113">See Also</span></span>  
 [<span data-ttu-id="937ef-114">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="937ef-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
