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
ms.openlocfilehash: 2ccc038b4420040779dae70f15e3a8827ba94180
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444112"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="d9993-102">Enumerazione COINITIEE</span><span class="sxs-lookup"><span data-stu-id="d9993-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="d9993-103">Specifica le costanti usate dal [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) durante l'inizializzazione del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d9993-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9993-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d9993-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="d9993-105">Members</span><span class="sxs-lookup"><span data-stu-id="d9993-105">Members</span></span>  
  
|<span data-ttu-id="d9993-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d9993-106">Member</span></span>|<span data-ttu-id="d9993-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d9993-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="d9993-108">Modalità di inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9993-108">Default initialization mode.</span></span> <span data-ttu-id="d9993-109">Il runtime viene inizializzato e viene creata la <xref:System.AppDomain>predefinita.</span><span class="sxs-lookup"><span data-stu-id="d9993-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="d9993-110">Inizializza per eseguire una DLL gestita.</span><span class="sxs-lookup"><span data-stu-id="d9993-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="d9993-111">Inizializza per eseguire un file EXE gestito.</span><span class="sxs-lookup"><span data-stu-id="d9993-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="d9993-112">In questo modo viene inizializzato il runtime, ma non viene creato il <xref:System.AppDomain>predefinito, che viene creato dopo l'immissione della routine principale del file EXE.</span><span class="sxs-lookup"><span data-stu-id="d9993-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9993-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d9993-113">Requirements</span></span>  
 <span data-ttu-id="d9993-114">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9993-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9993-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d9993-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9993-116">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d9993-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9993-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9993-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9993-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d9993-118">See also</span></span>

- [<span data-ttu-id="d9993-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="d9993-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
