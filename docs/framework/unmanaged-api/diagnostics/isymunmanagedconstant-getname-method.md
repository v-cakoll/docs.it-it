---
title: Metodo ISymUnmanagedConstant::GetName
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetName
helpviewer_keywords:
- ISymUnmanagedConstant::GetName method [.NET Framework debugging]
- GetName method, ISymUnmanagedConstant interface [.NET Framework debugging]
ms.assetid: cbaca4e1-4473-459b-ba34-f1f59ce7c0ba
topic_type:
- apiref
ms.openlocfilehash: 2dd70693528904459a34689dbad944c65c971254
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441643"
---
# <a name="isymunmanagedconstantgetname-method"></a><span data-ttu-id="2fcb2-102">Metodo ISymUnmanagedConstant::GetName</span><span class="sxs-lookup"><span data-stu-id="2fcb2-102">ISymUnmanagedConstant::GetName Method</span></span>
<span data-ttu-id="2fcb2-103">Ottiene il nome della costante.</span><span class="sxs-lookup"><span data-stu-id="2fcb2-103">Gets the name of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fcb2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2fcb2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
        length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fcb2-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2fcb2-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2fcb2-106">in Lunghezza del buffer a cui punta il `szName` parametro.</span><span class="sxs-lookup"><span data-stu-id="2fcb2-106">[in] The length of the buffer that the `szName` parameter points to.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2fcb2-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere il nome, inclusa la terminazione null.</span><span class="sxs-lookup"><span data-stu-id="2fcb2-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the name, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="2fcb2-108">out Il buffer in cui è archiviato il nome.</span><span class="sxs-lookup"><span data-stu-id="2fcb2-108">[out] The buffer that stores the name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fcb2-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2fcb2-109">Return Value</span></span>  
 <span data-ttu-id="2fcb2-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="2fcb2-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fcb2-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2fcb2-111">Requirements</span></span>  
 <span data-ttu-id="2fcb2-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="2fcb2-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fcb2-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2fcb2-113">See also</span></span>

- [<span data-ttu-id="2fcb2-114">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="2fcb2-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="2fcb2-115">Metodo GetSignature</span><span class="sxs-lookup"><span data-stu-id="2fcb2-115">GetSignature Method</span></span>](isymunmanagedconstant-getsignature-method.md)
- [<span data-ttu-id="2fcb2-116">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="2fcb2-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
