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
ms.openlocfilehash: 7f04b5c100f1fd9c44e671b883fe469b16d33fa6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440146"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="42a0e-102">Metodo ISymUnmanagedReader::GetSymAttribute</span><span class="sxs-lookup"><span data-stu-id="42a0e-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="42a0e-103">Ottiene un attributo personalizzato in base al nome.</span><span class="sxs-lookup"><span data-stu-id="42a0e-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="42a0e-104">Diversamente dagli attributi personalizzati dei metadati, questi attributi personalizzati vengono conservati nell'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="42a0e-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42a0e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="42a0e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="42a0e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="42a0e-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="42a0e-107">in Token di metadati per l'oggetto per il quale viene richiesto l'attributo.</span><span class="sxs-lookup"><span data-stu-id="42a0e-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="42a0e-108">in Puntatore alla variabile che indica l'attributo da recuperare.</span><span class="sxs-lookup"><span data-stu-id="42a0e-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="42a0e-109">[in] Dimensione della matrice `buffer`.</span><span class="sxs-lookup"><span data-stu-id="42a0e-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="42a0e-110">out Puntatore alla variabile che riceve la lunghezza dei dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="42a0e-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="42a0e-111">out Puntatore alla variabile che riceve i dati dell'attributo.</span><span class="sxs-lookup"><span data-stu-id="42a0e-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="42a0e-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="42a0e-112">Return Value</span></span>  
 <span data-ttu-id="42a0e-113">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="42a0e-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42a0e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="42a0e-114">Requirements</span></span>  
 <span data-ttu-id="42a0e-115">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="42a0e-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42a0e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="42a0e-116">See also</span></span>

- [<span data-ttu-id="42a0e-117">Interfaccia ISymUnmanagedReader</span><span class="sxs-lookup"><span data-stu-id="42a0e-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
