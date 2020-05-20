---
title: Metodo ISymUnmanagedMethod::GetSourceStartEnd
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetSourceStartEnd
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetSourceStartEnd
helpviewer_keywords:
- GetSourceStartEnd method [.NET Framework debugging]
- ISymUnmanagedMethod::GetSourceStartEnd method [.NET Framework debugging]
ms.assetid: 2a420900-01f1-4461-8777-3a34a6dc1426
topic_type:
- apiref
ms.openlocfilehash: 25e797fdf563a01ab727f16e7173eec2552eeb27
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614422"
---
# <a name="isymunmanagedmethodgetsourcestartend-method"></a><span data-ttu-id="f912a-102">Metodo ISymUnmanagedMethod::GetSourceStartEnd</span><span class="sxs-lookup"><span data-stu-id="f912a-102">ISymUnmanagedMethod::GetSourceStartEnd Method</span></span>
<span data-ttu-id="f912a-103">Ottiene le posizioni del documento iniziale e finale per l'origine di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="f912a-103">Gets the start and end document positions for the source of this method.</span></span> <span data-ttu-id="f912a-104">La prima posizione della matrice è l'inizio e la seconda posizione della matrice è la fine.</span><span class="sxs-lookup"><span data-stu-id="f912a-104">The first array position is the start, and the second array position is the end.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f912a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f912a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceStartEnd(  
    [in]  ISymUnmanagedDocument  *docs[2],  
    [in]  ULONG32                lines[2],  
    [in]  ULONG32                columns[2],  
    [out] BOOL                   *pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f912a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f912a-106">Parameters</span></span>  
 `docs`  
 <span data-ttu-id="f912a-107">in Documenti di origine iniziale e finale.</span><span class="sxs-lookup"><span data-stu-id="f912a-107">[in] The starting and ending source documents.</span></span>  
  
 `lines`  
 <span data-ttu-id="f912a-108">in Righe iniziali e finali dei documenti di origine corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f912a-108">[in] The starting and ending lines in the corresponding source documents.</span></span>  
  
 `columns`  
 <span data-ttu-id="f912a-109">in Colonne iniziali e finali dei documenti di origine corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="f912a-109">[in] The starting and ending columns in the corresponding source documents.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="f912a-110">[out] `true` Se le posizioni sono state definite; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="f912a-110">[out] `true` if positions were defined; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f912a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f912a-111">Return Value</span></span>  
 <span data-ttu-id="f912a-112">S_OK se il metodo ha esito positivo; in caso contrario, E_FAIL o un altro codice di errore.</span><span class="sxs-lookup"><span data-stu-id="f912a-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f912a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f912a-113">Requirements</span></span>  
 <span data-ttu-id="f912a-114">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="f912a-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f912a-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f912a-115">See also</span></span>

- [<span data-ttu-id="f912a-116">Interfaccia ISymUnmanagedMethod</span><span class="sxs-lookup"><span data-stu-id="f912a-116">ISymUnmanagedMethod Interface</span></span>](isymunmanagedmethod-interface.md)
