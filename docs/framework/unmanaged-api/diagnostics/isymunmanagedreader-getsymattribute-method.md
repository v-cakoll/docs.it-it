---
title: Metodo ISymUnmanagedReader::GetSymAttribute
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
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9795d5c7937f3c66c799665ba0e07e70c2be0b66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="2b008-102">Metodo ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="2b008-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="2b008-103">Ottiene un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="2b008-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="2b008-104">Diversamente dagli attributi personalizzati di metadati, gli attributi personalizzati sono contenuti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="2b008-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b008-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2b008-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b008-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="2b008-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="2b008-107">[in] Il token di metadati per l'oggetto per cui è richiesto l'attributo.</span><span class="sxs-lookup"><span data-stu-id="2b008-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="2b008-108">[in] Puntatore alla variabile che indica l'attributo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="2b008-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="2b008-109">[in] Dimensione della matrice `buffer`.</span><span class="sxs-lookup"><span data-stu-id="2b008-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="2b008-110">[out] Puntatore a una variabile che riceve la lunghezza dei dati degli attributi.</span><span class="sxs-lookup"><span data-stu-id="2b008-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="2b008-111">[out] Puntatore a una variabile che riceve i dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="2b008-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b008-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2b008-112">Return Value</span></span>  
 <span data-ttu-id="2b008-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore...</span><span class="sxs-lookup"><span data-stu-id="2b008-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code..</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b008-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2b008-114">Requirements</span></span>  
 <span data-ttu-id="2b008-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="2b008-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b008-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b008-116">See Also</span></span>  
 [<span data-ttu-id="2b008-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="2b008-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
