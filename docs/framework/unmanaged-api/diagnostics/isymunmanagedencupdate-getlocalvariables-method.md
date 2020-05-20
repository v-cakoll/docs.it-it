---
title: Metodo ISymUnmanagedENCUpdate::GetLocalVariables
ms.date: 03/30/2017
api_name:
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
ms.openlocfilehash: 5e5bf097a4b1e366fff807595b22c4696a91cf43
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614552"
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="86d4e-102">Metodo ISymUnmanagedENCUpdate::GetLocalVariables</span><span class="sxs-lookup"><span data-stu-id="86d4e-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="86d4e-103">Ottiene le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="86d4e-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d4e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="86d4e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86d4e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="86d4e-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="86d4e-106">in Token di metadati del metodo.</span><span class="sxs-lookup"><span data-stu-id="86d4e-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="86d4e-107">in Oggetto `ULONG` che indica la dimensione del `rgLocals` parametro.</span><span class="sxs-lookup"><span data-stu-id="86d4e-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="86d4e-108">out Matrice restituita delle istanze di [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="86d4e-108">[out] The returned array of [ISymUnmanagedVariable](isymunmanagedvariable-interface.md) instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="86d4e-109">out Puntatore a un oggetto `ULONG` che riceve le dimensioni del `rgLocals` buffer necessarie per contenere le variabili locali.</span><span class="sxs-lookup"><span data-stu-id="86d4e-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86d4e-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="86d4e-110">Return Value</span></span>  
 <span data-ttu-id="86d4e-111">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="86d4e-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86d4e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="86d4e-112">Requirements</span></span>  
 <span data-ttu-id="86d4e-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="86d4e-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d4e-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="86d4e-114">See also</span></span>

- [<span data-ttu-id="86d4e-115">Interfaccia ISymUnmanagedENCUpdate</span><span class="sxs-lookup"><span data-stu-id="86d4e-115">ISymUnmanagedENCUpdate Interface</span></span>](isymunmanagedencupdate-interface.md)
