---
title: Enumerazione RUNTIME_INFO_FLAGS
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d050972857ba652ae0b40727260f681c383208b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="d99a7-102">Enumerazione RUNTIME_INFO_FLAGS</span><span class="sxs-lookup"><span data-stu-id="d99a7-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="d99a7-103">Contiene valori che indicano le informazioni su common language runtime (CLR) devono essere restituite.</span><span class="sxs-lookup"><span data-stu-id="d99a7-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d99a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d99a7-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="d99a7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d99a7-105">Members</span></span>  
  
|<span data-ttu-id="d99a7-106">Membro</span><span class="sxs-lookup"><span data-stu-id="d99a7-106">Member</span></span>|<span data-ttu-id="d99a7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d99a7-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="d99a7-108">Indica che non devono essere incluse informazioni di directory.</span><span class="sxs-lookup"><span data-stu-id="d99a7-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="d99a7-109">Indica che non devono essere incluse informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="d99a7-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="d99a7-110">Indica che non deve essere visualizzata una finestra di dialogo di errore in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="d99a7-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="d99a7-111">Indica che gli effetti della chiamata di [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) funzione con il flag SEM_FAILCRITICALERRORS deve essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="d99a7-111">Indicates that the effects of calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="d99a7-112">Vale a dire la finestra di dialogo installazione deve essere visualizzata in caso di errore, anziché da eliminare.</span><span class="sxs-lookup"><span data-stu-id="d99a7-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="d99a7-113">Indica una richiesta di informazioni su una versione AMD-64 compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="d99a7-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="d99a7-114">Indica una richiesta di informazioni su una versione IA-64 compatibile del runtime.</span><span class="sxs-lookup"><span data-stu-id="d99a7-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="d99a7-115">Indica una richiesta di informazioni su una versione x86 compatibile di runtime.</span><span class="sxs-lookup"><span data-stu-id="d99a7-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="d99a7-116">Indica che devono essere incluse informazioni di aggiornamento di versione.</span><span class="sxs-lookup"><span data-stu-id="d99a7-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d99a7-117">Note</span><span class="sxs-lookup"><span data-stu-id="d99a7-117">Remarks</span></span>  
 <span data-ttu-id="d99a7-118">I flag dell'architettura di piattaforma seguenti possono essere specificati solo uno alla volta e non possono essere combinati:</span><span class="sxs-lookup"><span data-stu-id="d99a7-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
-   <span data-ttu-id="d99a7-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="d99a7-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="d99a7-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="d99a7-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="d99a7-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="d99a7-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d99a7-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d99a7-122">Requirements</span></span>  
 <span data-ttu-id="d99a7-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d99a7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d99a7-124">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d99a7-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d99a7-125">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d99a7-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d99a7-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d99a7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d99a7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d99a7-127">See Also</span></span>  
 [<span data-ttu-id="d99a7-128">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d99a7-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
