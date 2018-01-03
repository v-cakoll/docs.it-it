---
title: Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f85486370d567ceb1506c41f6aa7c4f3a1929941
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="90759-102">Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="90759-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="90759-103">Funziona nello stesso modo [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere di terminazione null per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="90759-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="90759-104">Spaziatura interna viene fornita solo se la lunghezza della stringa di percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="90759-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="90759-105">Questo rende più semplice scrivere strumenti tale file PE di differenza.</span><span class="sxs-lookup"><span data-stu-id="90759-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90759-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="90759-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90759-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="90759-107">Parameters</span></span>  
  
|<span data-ttu-id="90759-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="90759-108">Parameter</span></span>|<span data-ttu-id="90759-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="90759-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="90759-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="90759-110">Return Value</span></span>  
 <span data-ttu-id="90759-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="90759-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90759-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="90759-112">Requirements</span></span>  
 <span data-ttu-id="90759-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="90759-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90759-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="90759-114">See Also</span></span>  
 [<span data-ttu-id="90759-115">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="90759-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
