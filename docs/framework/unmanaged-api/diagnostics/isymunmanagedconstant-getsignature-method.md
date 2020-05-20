---
title: Metodo ISymUnmanagedConstant::GetSignature
ms.date: 03/30/2017
api_name:
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
ms.openlocfilehash: 332d60418c744a9391c7c0afc20248c2239b090c
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441620"
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="8ca0a-102">Metodo ISymUnmanagedConstant::GetSignature</span><span class="sxs-lookup"><span data-stu-id="8ca0a-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="8ca0a-103">Ottiene la firma della costante.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ca0a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ca0a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ca0a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ca0a-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="8ca0a-106">in Lunghezza del buffer a cui punta il `pcSig` parametro.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="8ca0a-107">out Puntatore a un oggetto `ULONG32` che riceve la dimensione, in caratteri, del buffer necessario per contenere la firma.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="8ca0a-108">out Buffer in cui è archiviata la firma.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ca0a-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ca0a-109">Return Value</span></span>  
 <span data-ttu-id="8ca0a-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="8ca0a-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ca0a-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ca0a-111">Requirements</span></span>  
 <span data-ttu-id="8ca0a-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="8ca0a-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ca0a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ca0a-113">See also</span></span>

- [<span data-ttu-id="8ca0a-114">Interfaccia ISymUnmanagedConstant</span><span class="sxs-lookup"><span data-stu-id="8ca0a-114">ISymUnmanagedConstant Interface</span></span>](isymunmanagedconstant-interface.md)
- [<span data-ttu-id="8ca0a-115">Metodo GetName</span><span class="sxs-lookup"><span data-stu-id="8ca0a-115">GetName Method</span></span>](isymunmanagedconstant-getname-method.md)
- [<span data-ttu-id="8ca0a-116">Metodo GetValue</span><span class="sxs-lookup"><span data-stu-id="8ca0a-116">GetValue Method</span></span>](isymunmanagedconstant-getvalue-method.md)
