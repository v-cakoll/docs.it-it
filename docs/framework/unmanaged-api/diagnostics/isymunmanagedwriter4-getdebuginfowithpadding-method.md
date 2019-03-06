---
title: Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cfa82ae8bbc87a884887f826d947c2d3f2c5341
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473526"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="38ca3-102">Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="38ca3-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="38ca3-103">Equivale [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere null di terminazione per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="38ca3-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="38ca3-104">Spaziatura interna viene assegnata solo se la lunghezza della stringa percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="38ca3-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="38ca3-105">Questo rende più semplice scrivere strumenti di tale file PE differenza.</span><span class="sxs-lookup"><span data-stu-id="38ca3-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ca3-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38ca3-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ca3-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="38ca3-107">Parameters</span></span>  
  
|<span data-ttu-id="38ca3-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="38ca3-108">Parameter</span></span>|<span data-ttu-id="38ca3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38ca3-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="38ca3-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="38ca3-110">Return Value</span></span>  
 <span data-ttu-id="38ca3-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="38ca3-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ca3-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38ca3-112">Requirements</span></span>  
 <span data-ttu-id="38ca3-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="38ca3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38ca3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38ca3-114">See also</span></span>
- [<span data-ttu-id="38ca3-115">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="38ca3-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
