---
title: Enumerazione COINITIEE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COINITIEE
api_location: mscoree.dll
api_type: COM
f1_keywords: COINITIEE
helpviewer_keywords: COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 03711186954aa24beff65e5d4d5b5e484c6dc276
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="306f7-102">Enumerazione COINITIEE</span><span class="sxs-lookup"><span data-stu-id="306f7-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="306f7-103">Specifica le costanti usate da [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="306f7-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="306f7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="306f7-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="306f7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="306f7-105">Members</span></span>  
  
|<span data-ttu-id="306f7-106">Membro</span><span class="sxs-lookup"><span data-stu-id="306f7-106">Member</span></span>|<span data-ttu-id="306f7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="306f7-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="306f7-108">Modalità di inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="306f7-108">Default initialization mode.</span></span> <span data-ttu-id="306f7-109">Inizializza il runtime e crea il valore predefinito <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="306f7-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="306f7-110">Inizializza per l'esecuzione di una DLL gestita.</span><span class="sxs-lookup"><span data-stu-id="306f7-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="306f7-111">Inizializza per l'esecuzione di un file EXE gestito.</span><span class="sxs-lookup"><span data-stu-id="306f7-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="306f7-112">Inizializza il runtime ma non crea il valore predefinito <xref:System.AppDomain>, che viene creato dopo l'immissione della routine principale del file EXE.</span><span class="sxs-lookup"><span data-stu-id="306f7-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="306f7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="306f7-113">Requirements</span></span>  
 <span data-ttu-id="306f7-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="306f7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="306f7-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="306f7-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="306f7-116">**Libreria:** inclusa come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="306f7-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="306f7-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="306f7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="306f7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="306f7-118">See Also</span></span>  
 [<span data-ttu-id="306f7-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="306f7-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
