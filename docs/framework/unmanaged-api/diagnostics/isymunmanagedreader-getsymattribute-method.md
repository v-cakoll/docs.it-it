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
ms.openlocfilehash: b7e2814e56765037b69c6ef7ca0ba610dd7d3c95
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614929"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="f243b-102">Metodo ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="f243b-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="f243b-103">Ottiene un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="f243b-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="f243b-104">Diversamente dagli attributi personalizzati dei metadati, questi attributi personalizzati vengono conservati nell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="f243b-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f243b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f243b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f243b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f243b-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="f243b-107">in Token di metadati per l'oggetto per il quale viene richiesto l'attributo.</span><span class="sxs-lookup"><span data-stu-id="f243b-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="f243b-108">in Puntatore alla variabile che indica l'attributo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="f243b-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="f243b-109">[in] Dimensione della matrice `buffer`.</span><span class="sxs-lookup"><span data-stu-id="f243b-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="f243b-110">out Puntatore alla variabile che riceve la lunghezza dei dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f243b-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="f243b-111">out Puntatore alla variabile che riceve i dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="f243b-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f243b-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f243b-112">Return Value</span></span>  
 <span data-ttu-id="f243b-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f243b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f243b-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f243b-114">Requirements</span></span>  
 <span data-ttu-id="f243b-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f243b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f243b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f243b-116">See also</span></span>

- [<span data-ttu-id="f243b-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="f243b-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
