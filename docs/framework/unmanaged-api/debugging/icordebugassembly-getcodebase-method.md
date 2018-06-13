---
title: Metodo ICorDebugAssembly::GetCodeBase
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetCodeBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetCodeBase
helpviewer_keywords:
- GetCodeBase method [.NET Framework debugging]
- ICorDebugAssembly::GetCodeBase method [.NET Framework debugging]
ms.assetid: 48adc154-9058-4fef-9c43-e9aad80e4dbf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6236d6b5349a9c2a528a85559c0cbc02c8da381
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401716"
---
# <a name="icordebugassemblygetcodebase-method"></a><span data-ttu-id="34f9a-102">Metodo ICorDebugAssembly::GetCodeBase</span><span class="sxs-lookup"><span data-stu-id="34f9a-102">ICorDebugAssembly::GetCodeBase Method</span></span>
<span data-ttu-id="34f9a-103">Questo metodo non è implementato nella versione corrente di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34f9a-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="34f9a-104">Syntax</span></span>  
  
```  
HRESULT GetCodeBase (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR szName[]  
);  
```
