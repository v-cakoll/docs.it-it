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
ms.openlocfilehash: 23f5a2b6b0970f3cb64ee339e6a1a409354a60e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780957"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="12634-102">Enumerazione COINITIEE</span><span class="sxs-lookup"><span data-stu-id="12634-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="12634-103">Specifica le costanti usate da [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) durante l'inizializzazione di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="12634-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12634-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="12634-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="12634-105">Membri</span><span class="sxs-lookup"><span data-stu-id="12634-105">Members</span></span>  
  
|<span data-ttu-id="12634-106">Member</span><span class="sxs-lookup"><span data-stu-id="12634-106">Member</span></span>|<span data-ttu-id="12634-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="12634-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="12634-108">Modalità di inizializzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="12634-108">Default initialization mode.</span></span> <span data-ttu-id="12634-109">Inizializza il runtime e crea il valore predefinito <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="12634-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="12634-110">Inizializza per l'esecuzione di una DLL gestita.</span><span class="sxs-lookup"><span data-stu-id="12634-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="12634-111">Inizializza per l'esecuzione di un file EXE gestito.</span><span class="sxs-lookup"><span data-stu-id="12634-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="12634-112">Inizializza la fase di esecuzione ma non crea il valore predefinito <xref:System.AppDomain>, che viene creato dopo avere immesso la routine principale del file EXE.</span><span class="sxs-lookup"><span data-stu-id="12634-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="12634-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="12634-113">Requirements</span></span>  
 <span data-ttu-id="12634-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12634-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12634-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="12634-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12634-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="12634-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12634-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12634-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12634-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="12634-118">See also</span></span>

- [<span data-ttu-id="12634-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="12634-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
