---
title: Metodo ISymENCUnmanagedMethod::GetSourceExtentInDocument
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetSourceExtentInDocument
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetSourceExtentInDocument
helpviewer_keywords:
- GetSourceExtentInDocument method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetSourceExtentInDocument method [.NET Framework debugging]
ms.assetid: 9c5566ab-4ec7-4b61-9753-839bb90ae78c
topic_type:
- apiref
ms.openlocfilehash: 3ac8bb3a20ce82b734a572832a9cbb75fa2568c4
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441903"
---
# <a name="isymencunmanagedmethodgetsourceextentindocument-method"></a><span data-ttu-id="af1dc-102">Metodo ISymENCUnmanagedMethod::GetSourceExtentInDocument</span><span class="sxs-lookup"><span data-stu-id="af1dc-102">ISymENCUnmanagedMethod::GetSourceExtentInDocument Method</span></span>
<span data-ttu-id="af1dc-103">Ottiene la riga iniziale più piccola e la riga finale più grande per il metodo in un documento specifico.</span><span class="sxs-lookup"><span data-stu-id="af1dc-103">Gets the smallest start line and largest end line for the method in a specific document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1dc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="af1dc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceExtentInDocument(  
    [in]  ISymUnmanagedDocument *document,  
    [out] ULONG32* pstartLine,  
    [out] ULONG32* pendLine);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af1dc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="af1dc-105">Parameters</span></span>  
 `document`  
 <span data-ttu-id="af1dc-106">in Puntatore al documento.</span><span class="sxs-lookup"><span data-stu-id="af1dc-106">[in] A pointer to the document.</span></span>  
  
 `pstartLine`  
 <span data-ttu-id="af1dc-107">out Puntatore a un oggetto `ULONG32` che riceve la riga iniziale.</span><span class="sxs-lookup"><span data-stu-id="af1dc-107">[out] A pointer to a `ULONG32` that receives the start line.</span></span>  
  
 `pendLine`  
 <span data-ttu-id="af1dc-108">out Puntatore a un oggetto `ULONG32` che riceve la riga finale.</span><span class="sxs-lookup"><span data-stu-id="af1dc-108">[out] A pointer to a `ULONG32` that receives the end line.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af1dc-109">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="af1dc-109">Return Value</span></span>  
 <span data-ttu-id="af1dc-110">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="af1dc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af1dc-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="af1dc-111">Requirements</span></span>  
 <span data-ttu-id="af1dc-112">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="af1dc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1dc-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="af1dc-113">See also</span></span>

- [<span data-ttu-id="af1dc-114">Interfaccia ISymENCUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="af1dc-114">ISymENCUnmanagedMethod Interface</span></span>](isymencunmanagedmethod-interface.md)
