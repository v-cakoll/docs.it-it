---
title: Enumerazione COINITIEE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="b1e1c-102">Enumerazione COINITIEE</span><span class="sxs-lookup"><span data-stu-id="b1e1c-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="b1e1c-103">Specifica le costanti usate da [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1e1c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b1e1c-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="b1e1c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b1e1c-105">Members</span></span>  
  
|<span data-ttu-id="b1e1c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b1e1c-106">Member</span></span>|<span data-ttu-id="b1e1c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b1e1c-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="b1e1c-108">Modalità di inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-108">Default initialization mode.</span></span> <span data-ttu-id="b1e1c-109">Inizializza il runtime e crea il valore predefinito <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="b1e1c-110">Inizializza per l'esecuzione di una DLL gestita.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="b1e1c-111">Inizializza per l'esecuzione di un file EXE gestito.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="b1e1c-112">Inizializza il runtime ma non crea il valore predefinito <xref:System.AppDomain>, che viene creato dopo l'immissione della routine principale del file EXE.</span><span class="sxs-lookup"><span data-stu-id="b1e1c-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1e1c-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b1e1c-113">Requirements</span></span>  
 <span data-ttu-id="b1e1c-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1e1c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1e1c-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b1e1c-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1e1c-116">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b1e1c-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b1e1c-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1e1c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e1c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b1e1c-118">See Also</span></span>  
 [<span data-ttu-id="b1e1c-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="b1e1c-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
