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
ms.openlocfilehash: a4d15d9ae63e63f98ab73e250df558dfa16002a7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411788"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="b55da-102">Metodo ICorDebugFunction2::EnumerateNativeCode</span><span class="sxs-lookup"><span data-stu-id="b55da-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="b55da-103">Ottiene un puntatore a interfaccia a un oggetto ICorDebugCodeEnum che contiene le istruzioni di codice nativo nella funzione a cui fa riferimento questo oggetto ICorDebugFunction2.</span><span class="sxs-lookup"><span data-stu-id="b55da-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b55da-104">`EnumerateNativeCode` non è implementata nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b55da-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b55da-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b55da-105">Syntax</span></span>  
  
```  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="b55da-106">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b55da-106">Requirements</span></span>  
 <span data-ttu-id="b55da-107">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b55da-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
