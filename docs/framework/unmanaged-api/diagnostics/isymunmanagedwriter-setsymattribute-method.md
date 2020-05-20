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
ms.openlocfilehash: 39b0c065a324f2b3939467901739f995bc9abbad
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614760"
---
# <a name="isymunmanagedwritersetsymattribute-method"></a><span data-ttu-id="3322e-102">Metodo ISymUnmanagedWriter::SetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="3322e-102">ISymUnmanagedWriter::SetSymAttribute Method</span></span>
<span data-ttu-id="3322e-103">Definisce un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="3322e-103">Defines a custom attribute based upon its name.</span></span> <span data-ttu-id="3322e-104">Questi attributi sono conservati nell'archivio simboli, a differenza degli attributi personalizzati dei metadati.</span><span class="sxs-lookup"><span data-stu-id="3322e-104">These attributes are held in the symbol store, unlike metadata custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3322e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3322e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetSymAttribute(  
    [in] mdToken parent,  
    [in] const WCHAR *name,  
    [in] ULONG32 cData,  
    [in, size_is(cData)] unsigned char data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3322e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="3322e-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="3322e-107">in Token di metadati per il quale viene definito l'attributo.</span><span class="sxs-lookup"><span data-stu-id="3322e-107">[in] The metadata token for which the attribute is being defined.</span></span>  
  
 `name`  
 <span data-ttu-id="3322e-108">in Puntatore a un oggetto `WCHAR` che contiene il nome dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="3322e-108">[in] A pointer to a `WCHAR` that contains the attribute name.</span></span>  
  
 `cData`  
 <span data-ttu-id="3322e-109">in Oggetto `ULONG32` che indica la dimensione della `data` matrice.</span><span class="sxs-lookup"><span data-stu-id="3322e-109">[in] A `ULONG32` that indicates the size of the `data` array.</span></span>  
  
 `data`  
 <span data-ttu-id="3322e-110">in Valore dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="3322e-110">[in] The attribute value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3322e-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3322e-111">Return Value</span></span>  
 <span data-ttu-id="3322e-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="3322e-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3322e-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3322e-113">Requirements</span></span>  
 <span data-ttu-id="3322e-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="3322e-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3322e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3322e-115">See also</span></span>

- [<span data-ttu-id="3322e-116">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="3322e-116">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
