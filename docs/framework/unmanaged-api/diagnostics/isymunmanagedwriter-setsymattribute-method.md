---
title: Metodo ISymUnmanagedWriter::SetSymAttribute
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetSymAttribute
helpviewer_keywords:
- SetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedWriter::SetSymAttribute method [.NET Framework debugging]
ms.assetid: 64d9b80e-b883-4539-89c7-03573185a1eb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ee3e96a25a224fb5b025e22fa43169a64f6c0d2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501669"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="a7230-102">Metodo ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="a7230-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="a7230-103">Definisce un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="a7230-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="a7230-104">Questi attributi sono contenuti nell'archivio simboli, a differenza degli attributi personalizzati di metadati.</span><span class="sxs-lookup"><span data-stu-id="a7230-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7230-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a7230-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7230-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="a7230-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="a7230-107">[in] Il token di metadati per il quale viene definito l'attributo.</span><span class="sxs-lookup"><span data-stu-id="a7230-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="a7230-108">[in] Un puntatore a un `WCHAR` che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a7230-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="a7230-109">[in] Oggetto `ULONG32` che indica le dimensioni del `data` matrice.</span><span class="sxs-lookup"><span data-stu-id="a7230-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="a7230-110">[in] Il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="a7230-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7230-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="a7230-111">Return Value</span></span>  
 <span data-ttu-id="a7230-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o qualche altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="a7230-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7230-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a7230-113">Requirements</span></span>  
 <span data-ttu-id="a7230-114">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a7230-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7230-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7230-115">See also</span></span>
- [<span data-ttu-id="a7230-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="a7230-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
