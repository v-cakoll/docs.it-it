---
title: Funzione CreateApplicationContext
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25364330dafdf858c4b41e9a05731c37e97fbb57
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795441"
---
# <a name="createapplicationcontext-function"></a><span data-ttu-id="d237d-102">Funzione CreateApplicationContext</span><span class="sxs-lookup"><span data-stu-id="d237d-102">CreateApplicationContext Function</span></span>
<span data-ttu-id="d237d-103">Questa funzione supporta l'infrastruttura .NET Framework e non può essere usata direttamente dal codice.</span><span class="sxs-lookup"><span data-stu-id="d237d-103">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d237d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d237d-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="d237d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d237d-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="d237d-106">in Puntatore a un nome descrittivo.</span><span class="sxs-lookup"><span data-stu-id="d237d-106">[in] A pointer to a friendly name.</span></span>  
  
 `ppCtx`  
 <span data-ttu-id="d237d-107">out Puntatore a un contesto dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d237d-107">[out] A pointer to an application context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d237d-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d237d-108">Requirements</span></span>  
 <span data-ttu-id="d237d-109">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d237d-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d237d-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="d237d-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d237d-111">**Libreria** Incluso come risorsa in Fusion. dll</span><span class="sxs-lookup"><span data-stu-id="d237d-111">**Library:** Included as a resource in Fusion.dll</span></span>  
  
 <span data-ttu-id="d237d-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d237d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d237d-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d237d-113">See also</span></span>

- [<span data-ttu-id="d237d-114">Interfaccia IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="d237d-114">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="d237d-115">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="d237d-115">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="d237d-116">Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="d237d-116">Global Assembly Cache</span></span>](../../app-domains/gac.md)
