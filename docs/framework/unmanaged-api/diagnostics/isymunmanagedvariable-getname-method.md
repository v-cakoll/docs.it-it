---
title: Metodo ISymUnmanagedVariable::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetName
helpviewer_keywords:
- GetName method, ISymUnmanagedVariable interface [.NET Framework debugging]
- ISymUnmanagedVariable::GetName method [.NET Framework debugging]
ms.assetid: eedf1ef0-9d4a-4847-a201-4e99572dfe5e
topic_type:
- apiref
ms.openlocfilehash: 77dec4332aa65f6125685db607169b3398bcab98
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446059"
---
# <a name="isymunmanagedvariablegetname-method"></a><span data-ttu-id="cc6ee-102">Metodo ISymUnmanagedVariable::GetName</span><span class="sxs-lookup"><span data-stu-id="cc6ee-102">ISymUnmanagedVariable::GetName Method</span></span>
<span data-ttu-id="cc6ee-103">Ottiene il nome della variabile.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-103">Gets the name of this variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc6ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc6ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc6ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc6ee-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="cc6ee-106">in Lunghezza del buffer a cui punta il parametro `pcchName`.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-106">[in] The length of the buffer that the `pcchName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="cc6ee-107">out Puntatore a un `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="cc6ee-108">out Il buffer in cui è archiviato il nome.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc6ee-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cc6ee-109">Return Value</span></span>  
 <span data-ttu-id="cc6ee-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="cc6ee-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc6ee-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc6ee-111">Requirements</span></span>  
 <span data-ttu-id="cc6ee-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cc6ee-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc6ee-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc6ee-113">See also</span></span>

- [<span data-ttu-id="cc6ee-114">Interfaccia ISymUnmanagedVariable</span><span class="sxs-lookup"><span data-stu-id="cc6ee-114">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)
