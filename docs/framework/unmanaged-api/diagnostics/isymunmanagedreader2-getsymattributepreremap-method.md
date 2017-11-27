---
title: Metodo ISymUnmanagedReader2::GetSymAttributePreRemap
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader2.GetSymAttributePreRemap
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader2::GetSymAttributePreRemap
helpviewer_keywords:
- GetSymAttributePreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetSymAttributePreRemap method [.NET Framework debugging]
ms.assetid: 7580d546-a709-40c5-ad02-aa70d774fd0b
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 75608d89b6fd34570166718de824150b0621c84e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreader2getsymattributepreremap-method"></a><span data-ttu-id="25e53-102">Metodo ISymUnmanagedReader2::GetSymAttributePreRemap</span><span class="sxs-lookup"><span data-stu-id="25e53-102">ISymUnmanagedReader2::GetSymAttributePreRemap Method</span></span>
<span data-ttu-id="25e53-103">Ottiene un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="25e53-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="25e53-104">A differenza dei metadati attributi personalizzati, questi attributi sono contenuti nell'archivio simboli.</span><span class="sxs-lookup"><span data-stu-id="25e53-104">Unlike metadata custom attributes, these attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25e53-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25e53-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttributePreRemap(  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is(cBuffer),  
        length_is(*pcBuffer)] BYTE buffer[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="25e53-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="25e53-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="25e53-107">[in] Il token di metadati dell'elemento padre.</span><span class="sxs-lookup"><span data-stu-id="25e53-107">[in] The metadata token of the parent.</span></span>  
  
 `name`  
 <span data-ttu-id="25e53-108">[in] Un puntatore a un `WCHAR` che contiene il nome.</span><span class="sxs-lookup"><span data-stu-id="25e53-108">[in] A pointer to a `WCHAR` that contains the name.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="25e53-109">[in] Oggetto `ULONG32` che indica le dimensioni del `buffer` matrice.</span><span class="sxs-lookup"><span data-stu-id="25e53-109">[in] A `ULONG32` that indicates the size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="25e53-110">[out] Un puntatore a un `ULONG32` che riceve le dimensioni del buffer necessaria per contenere i byte di attributo.</span><span class="sxs-lookup"><span data-stu-id="25e53-110">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the attribute bytes.</span></span>  
  
 `buffer`  
 <span data-ttu-id="25e53-111">[out] Puntatore al buffer che riceve i byte di attributo.</span><span class="sxs-lookup"><span data-stu-id="25e53-111">[out] A pointer to the buffer that receives the attribute bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="25e53-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="25e53-112">Return Value</span></span>  
 <span data-ttu-id="25e53-113">S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="25e53-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25e53-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25e53-114">Requirements</span></span>  
 <span data-ttu-id="25e53-115">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="25e53-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25e53-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25e53-116">See Also</span></span>  
 [<span data-ttu-id="25e53-117">ISymUnmanagedReader2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="25e53-117">ISymUnmanagedReader2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)
