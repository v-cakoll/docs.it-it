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
ms.openlocfilehash: bd1a55d4100d74b769b2bc1b8fe33d2042f5e739
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428301"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="4729a-102">Metodo ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="4729a-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="4729a-103">Definisce un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="4729a-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="4729a-104">Questi attributi sono contenuti nell'archivio di simboli, diversamente dagli attributi di metadati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4729a-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4729a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4729a-105">Syntax</span></span>  
  
```  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4729a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4729a-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="4729a-107">[in] Il token di metadati per il quale viene definito l'attributo.</span><span class="sxs-lookup"><span data-stu-id="4729a-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="4729a-108">[in] Un puntatore a un `WCHAR` che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="4729a-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="4729a-109">[in] Oggetto `ULONG32` che indica le dimensioni del `data` matrice.</span><span class="sxs-lookup"><span data-stu-id="4729a-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="4729a-110">[in] Il valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="4729a-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4729a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4729a-111">Return Value</span></span>  
 <span data-ttu-id="4729a-112">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="4729a-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4729a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4729a-113">Requirements</span></span>  
 <span data-ttu-id="4729a-114">**Intestazione:** CorSym. idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="4729a-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4729a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4729a-115">See Also</span></span>  
 [<span data-ttu-id="4729a-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="4729a-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
