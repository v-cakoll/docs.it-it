---
title: Enumerazione COINITIEE
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4a84fdfdba96c58671302c723b8a56848b70eb60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984126"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="543b8-102">Enumerazione COINITIEE</span><span class="sxs-lookup"><span data-stu-id="543b8-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="543b8-103">Specifica le costanti usate da [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="543b8-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="543b8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="543b8-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="543b8-105">Membri</span><span class="sxs-lookup"><span data-stu-id="543b8-105">Members</span></span>  
  
|<span data-ttu-id="543b8-106">Member</span><span class="sxs-lookup"><span data-stu-id="543b8-106">Member</span></span>|<span data-ttu-id="543b8-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="543b8-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="543b8-108">Modalità di inizializzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="543b8-108">Default initialization mode.</span></span> <span data-ttu-id="543b8-109">Inizializza il runtime e crea il valore predefinito <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="543b8-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="543b8-110">Inizializza per l'esecuzione di una DLL gestita.</span><span class="sxs-lookup"><span data-stu-id="543b8-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="543b8-111">Inizializza per l'esecuzione di un file EXE gestito.</span><span class="sxs-lookup"><span data-stu-id="543b8-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="543b8-112">Inizializza la fase di esecuzione ma non crea il valore predefinito <xref:System.AppDomain>, che viene creato dopo avere immesso la routine principale del file EXE.</span><span class="sxs-lookup"><span data-stu-id="543b8-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="543b8-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="543b8-113">Requirements</span></span>  
 <span data-ttu-id="543b8-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="543b8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="543b8-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="543b8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="543b8-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="543b8-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="543b8-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="543b8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543b8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="543b8-118">See also</span></span>

- [<span data-ttu-id="543b8-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="543b8-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
