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
ms.openlocfilehash: 8a4d205586921b377147eeab80754e1a0d9e52b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74427846"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="1b076-102">Metodo ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="1b076-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="1b076-103">Definisce un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="1b076-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="1b076-104">Questi attributi sono conservati nell'archivio simboli, a differenza degli attributi personalizzati dei metadati.</span><span class="sxs-lookup"><span data-stu-id="1b076-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b076-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b076-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b076-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b076-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="1b076-107">in Token di metadati per il quale viene definito l'attributo.</span><span class="sxs-lookup"><span data-stu-id="1b076-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="1b076-108">in Puntatore a un `WCHAR` che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="1b076-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="1b076-109">in `ULONG32` che indica le dimensioni della matrice di `data`.</span><span class="sxs-lookup"><span data-stu-id="1b076-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="1b076-110">in Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="1b076-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1b076-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="1b076-111">Return Value</span></span>  
 <span data-ttu-id="1b076-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="1b076-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b076-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b076-113">Requirements</span></span>  
 <span data-ttu-id="1b076-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="1b076-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b076-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1b076-115">See also</span></span>

- [<span data-ttu-id="1b076-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="1b076-116">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
