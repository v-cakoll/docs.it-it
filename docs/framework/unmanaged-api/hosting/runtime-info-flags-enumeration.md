---
title: Enumerazione RUNTIME_INFO_FLAGS
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9483cf8671b7d3ad5430081d93925af30b3d8368
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765154"
---
# <a name="runtimeinfoflags-enumeration"></a><span data-ttu-id="bda72-102">Enumerazione RUNTIME_INFO_FLAGS</span><span class="sxs-lookup"><span data-stu-id="bda72-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="bda72-103">Contiene valori che indicano le informazioni su common language runtime (CLR) devono essere restituite.</span><span class="sxs-lookup"><span data-stu-id="bda72-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bda72-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bda72-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bda72-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bda72-105">Members</span></span>  
  
|<span data-ttu-id="bda72-106">Member</span><span class="sxs-lookup"><span data-stu-id="bda72-106">Member</span></span>|<span data-ttu-id="bda72-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bda72-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="bda72-108">Indica che non devono essere incluse informazioni di directory.</span><span class="sxs-lookup"><span data-stu-id="bda72-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="bda72-109">Indica che non devono essere incluse informazioni sulla versione.</span><span class="sxs-lookup"><span data-stu-id="bda72-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="bda72-110">Indica che non deve essere visualizzata una finestra di dialogo di errore in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="bda72-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="bda72-111">Indica che gli effetti della chiamata al metodo il [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) funzione con il flag SEM_FAILCRITICALERRORS deve essere sottoposto a override.</span><span class="sxs-lookup"><span data-stu-id="bda72-111">Indicates that the effects of calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="bda72-112">Vale a dire, una finestra di dialogo di installazione deve essere visualizzato in caso di errore, anziché da eliminare.</span><span class="sxs-lookup"><span data-stu-id="bda72-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="bda72-113">Indica una richiesta per informazioni su una versione compatibile con 64 processori AMD del runtime.</span><span class="sxs-lookup"><span data-stu-id="bda72-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="bda72-114">Indica una richiesta per informazioni su una versione compatibile con IA-64 di runtime.</span><span class="sxs-lookup"><span data-stu-id="bda72-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="bda72-115">Indica una richiesta per informazioni su una versione x86 compatibile di runtime.</span><span class="sxs-lookup"><span data-stu-id="bda72-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="bda72-116">Indica che devono essere incluse informazioni sull'aggiornamento di versione.</span><span class="sxs-lookup"><span data-stu-id="bda72-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bda72-117">Note</span><span class="sxs-lookup"><span data-stu-id="bda72-117">Remarks</span></span>  
 <span data-ttu-id="bda72-118">I flag di architettura di piattaforma seguenti possono essere specificato solo uno alla volta e non possono essere combinati:</span><span class="sxs-lookup"><span data-stu-id="bda72-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="bda72-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="bda72-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="bda72-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="bda72-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="bda72-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="bda72-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bda72-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bda72-122">Requirements</span></span>  
 <span data-ttu-id="bda72-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bda72-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bda72-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bda72-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bda72-125">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bda72-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bda72-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bda72-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bda72-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bda72-127">See also</span></span>

- [<span data-ttu-id="bda72-128">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="bda72-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
