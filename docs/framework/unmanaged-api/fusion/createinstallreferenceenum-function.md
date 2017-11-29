---
title: Funzione CreateInstallReferenceEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateInstallReference
helpviewer_keywords: CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07c7ec72a66b37798e6e2af523bb024e9dd63d9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="a4950-102">Funzione CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="a4950-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="a4950-103">Ottiene un puntatore a un [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) istanza che rappresenta un elenco di riferimenti di un'applicazione per l'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="a4950-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4950-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a4950-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4950-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a4950-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="a4950-106">[out] L'oggetto restituito `IInstallReferenceEnum` puntatore.</span><span class="sxs-lookup"><span data-stu-id="a4950-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="a4950-107">[in] Il [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) che identifica l'assembly per cui si desidera enumerare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="a4950-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a4950-108">[in] Flag che influenzano il comportamento dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="a4950-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a4950-109">[in] Riservato per l'estensibilità futura.</span><span class="sxs-lookup"><span data-stu-id="a4950-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a4950-110">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="a4950-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4950-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a4950-111">Requirements</span></span>  
 <span data-ttu-id="a4950-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4950-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4950-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="a4950-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a4950-114">**Libreria:** Fusion e Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="a4950-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="a4950-115">Utilizzare il file Fusion.dll anziché Mscorwks.dll per garantire che la versione corretta di .NET Framework di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a4950-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="a4950-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4950-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4950-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a4950-117">See Also</span></span>  
 [<span data-ttu-id="a4950-118">IInstallReferenceEnum (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a4950-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)  
 [<span data-ttu-id="a4950-119">IAssemblyName (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="a4950-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="a4950-120">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="a4950-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
