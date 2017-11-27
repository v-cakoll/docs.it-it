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
ms.openlocfilehash: d9f2f0aad37fcd63e2345cd32a00b44412ed8c7a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="53b15-102">Metodo ISymUnmanagedWriter4::GetDebugInfoWithPadding</span><span class="sxs-lookup"><span data-stu-id="53b15-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="53b15-103">Funziona nello stesso modo [metodo GetDebugInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) ad eccezione del fatto che la stringa di percorso verrà anteposti tanti zeri che seguono il carattere di terminazione null per rendere i dati di stringa di una dimensione fissa di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="53b15-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="53b15-104">Spaziatura interna viene fornita solo se la lunghezza della stringa di percorso stesso è minore di `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="53b15-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="53b15-105">Questo rende più semplice scrivere strumenti tale file PE di differenza.</span><span class="sxs-lookup"><span data-stu-id="53b15-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b15-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="53b15-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53b15-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="53b15-107">Parameters</span></span>  
  
|<span data-ttu-id="53b15-108">Parametro</span><span class="sxs-lookup"><span data-stu-id="53b15-108">Parameter</span></span>|<span data-ttu-id="53b15-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="53b15-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="53b15-110">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="53b15-110">Return Value</span></span>  
 <span data-ttu-id="53b15-111">Restituisce `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="53b15-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53b15-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="53b15-112">Requirements</span></span>  
 <span data-ttu-id="53b15-113">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="53b15-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b15-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="53b15-114">See Also</span></span>  
 [<span data-ttu-id="53b15-115">Interfaccia ISymUnmanagedWriter4</span><span class="sxs-lookup"><span data-stu-id="53b15-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
