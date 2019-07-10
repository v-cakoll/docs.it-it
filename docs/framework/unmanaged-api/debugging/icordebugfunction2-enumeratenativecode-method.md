---
title: Metodo ICorDebugFunction2::EnumerateNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61dcf014a65f524d2b2e7b92bcc7f007d1a47125
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754506"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="9c494-102">Metodo ICorDebugFunction2::EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="9c494-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="9c494-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum contenente le istruzioni di codice nativo nella funzione di cui viene fatto riferimento dall'oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="9c494-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9c494-104">`EnumerateNativeCode` non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9c494-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c494-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9c494-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9c494-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9c494-106">Requirements</span></span>  
 <span data-ttu-id="9c494-107">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c494-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
