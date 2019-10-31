---
title: Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 274bf79175bda9e880b1ef3cf8f125a017ad0734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121666"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="cb525-102">Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="cb525-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="cb525-103">Funziona allo stesso modo del [Metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) , con la differenza che la stringa di percorso viene riempita con zeri che seguono il carattere null di terminazione per fare in modo che i dati della stringa siano di dimensioni fisse `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="cb525-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="cb525-104">La spaziatura interna viene specificata solo se la lunghezza della stringa di percorso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="cb525-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="cb525-105">In questo modo è più semplice scrivere strumenti che differenziano i file PE.</span><span class="sxs-lookup"><span data-stu-id="cb525-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb525-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cb525-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb525-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="cb525-107">Parameters</span></span>  
  
|<span data-ttu-id="cb525-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="cb525-108">Parameter</span></span>|<span data-ttu-id="cb525-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cb525-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="cb525-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="cb525-110">Return Value</span></span>  
 <span data-ttu-id="cb525-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="cb525-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb525-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cb525-112">Requirements</span></span>  
 <span data-ttu-id="cb525-113">**Intestazione:** CorSym. idl, CorSym. h</span><span class="sxs-lookup"><span data-stu-id="cb525-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb525-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cb525-114">See also</span></span>

- [<span data-ttu-id="cb525-115">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="cb525-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
