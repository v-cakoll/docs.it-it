---
title: Metodo ISymUnmanagedReader::GetSymAttribute
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 26458e2512f331ff7a8c41868c99d092cfd30977
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737232"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="855de-102">Metodo ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="855de-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="855de-103">Ottiene un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="855de-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="855de-104">A differenza dei metadati di attributi personalizzati, questi attributi personalizzati vengono mantenuti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="855de-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="855de-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="855de-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="855de-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="855de-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="855de-107">[in] Il token di metadati per l'oggetto per cui è richiesto l'attributo.</span><span class="sxs-lookup"><span data-stu-id="855de-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="855de-108">[in] Puntatore alla variabile che indica l'attributo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="855de-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="855de-109">[in] Dimensione della matrice `buffer`.</span><span class="sxs-lookup"><span data-stu-id="855de-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="855de-110">[out] Puntatore alla variabile che riceve la lunghezza dei dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="855de-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="855de-111">[out] Puntatore alla variabile che riceve i dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="855de-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="855de-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="855de-112">Return Value</span></span>  
 <span data-ttu-id="855de-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="855de-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="855de-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="855de-114">Requirements</span></span>  
 <span data-ttu-id="855de-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="855de-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855de-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="855de-116">See also</span></span>

- [<span data-ttu-id="855de-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="855de-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
