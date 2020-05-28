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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005908"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="a9278-102">Enumerazione COINITIEE</span><span class="sxs-lookup"><span data-stu-id="a9278-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="a9278-103">Specifica le costanti usate dal [CoInitializeEE](../hosting/coinitializeee-function.md) durante l'inizializzazione del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a9278-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9278-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9278-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="a9278-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a9278-105">Members</span></span>  
  
|<span data-ttu-id="a9278-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a9278-106">Member</span></span>|<span data-ttu-id="a9278-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a9278-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="a9278-108">Modalità di inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="a9278-108">Default initialization mode.</span></span> <span data-ttu-id="a9278-109">Il runtime viene inizializzato e viene creato il valore predefinito <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="a9278-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="a9278-110">Inizializza per eseguire una DLL gestita.</span><span class="sxs-lookup"><span data-stu-id="a9278-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="a9278-111">Inizializza per eseguire un file EXE gestito.</span><span class="sxs-lookup"><span data-stu-id="a9278-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="a9278-112">In questo modo viene inizializzato il runtime, ma non viene creato il valore predefinito <xref:System.AppDomain> , che viene creato dopo l'immissione della routine principale del file exe.</span><span class="sxs-lookup"><span data-stu-id="a9278-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9278-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9278-113">Requirements</span></span>  
 <span data-ttu-id="a9278-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9278-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9278-115">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a9278-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9278-116">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a9278-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9278-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9278-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9278-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9278-118">See also</span></span>

- [<span data-ttu-id="a9278-119">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="a9278-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
