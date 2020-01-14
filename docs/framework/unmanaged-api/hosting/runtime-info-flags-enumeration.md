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
ms.openlocfilehash: 9d505b917c343c40c7fa2a7aecf3466578ae0a8d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936633"
---
# <a name="runtime_info_flags-enumeration"></a><span data-ttu-id="f2a02-102">Enumerazione RUNTIME_INFO_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f2a02-102">RUNTIME_INFO_FLAGS Enumeration</span></span>
<span data-ttu-id="f2a02-103">Contiene valori che indicano quali informazioni relative al Common Language Runtime (CLR) devono essere restituite.</span><span class="sxs-lookup"><span data-stu-id="f2a02-103">Contains values that indicate what information about the common language runtime (CLR) should be returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2a02-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f2a02-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="f2a02-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f2a02-105">Members</span></span>  
  
|<span data-ttu-id="f2a02-106">Member</span><span class="sxs-lookup"><span data-stu-id="f2a02-106">Member</span></span>|<span data-ttu-id="f2a02-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f2a02-107">Description</span></span>|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|<span data-ttu-id="f2a02-108">Indica che le informazioni della directory non devono essere incluse.</span><span class="sxs-lookup"><span data-stu-id="f2a02-108">Indicates that directory information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|<span data-ttu-id="f2a02-109">Indica che le informazioni sulla versione non devono essere incluse.</span><span class="sxs-lookup"><span data-stu-id="f2a02-109">Indicates that version information should not be included.</span></span>|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|<span data-ttu-id="f2a02-110">Indica che non è possibile visualizzare una finestra di dialogo di errore in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="f2a02-110">Indicates that an error dialog box should not be shown upon failure.</span></span>|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|<span data-ttu-id="f2a02-111">Indica che è necessario eseguire l'override degli effetti della chiamata della funzione [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) con il flag SEM_FAILCRITICALERRORS.</span><span class="sxs-lookup"><span data-stu-id="f2a02-111">Indicates that the effects of calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function with the SEM_FAILCRITICALERRORS flag should be overridden.</span></span> <span data-ttu-id="f2a02-112">Ovvero una finestra di dialogo di installazione dovrebbe essere visualizzata in caso di errore, anziché essere eliminato.</span><span class="sxs-lookup"><span data-stu-id="f2a02-112">That is, an installation dialog box should be shown upon failure, instead of being suppressed.</span></span>|  
|`RUNTIME_INFO_REQUEST_AMD64`|<span data-ttu-id="f2a02-113">Indica una richiesta di informazioni su una versione compatibile con AMD-64 del runtime.</span><span class="sxs-lookup"><span data-stu-id="f2a02-113">Indicates a request for information about an AMD-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_IA64`|<span data-ttu-id="f2a02-114">Indica una richiesta di informazioni su una versione compatibile con IA-64 del runtime.</span><span class="sxs-lookup"><span data-stu-id="f2a02-114">Indicates a request for information about an IA-64-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_REQUEST_X86`|<span data-ttu-id="f2a02-115">Indica una richiesta di informazioni su una versione compatibile x86 del runtime.</span><span class="sxs-lookup"><span data-stu-id="f2a02-115">Indicates a request for information about an x86-compatible version of the runtime.</span></span>|  
|`RUNTIME_INFO_UPGRADE_VERSION`|<span data-ttu-id="f2a02-116">Indica che devono essere incluse le informazioni relative all'aggiornamento della versione.</span><span class="sxs-lookup"><span data-stu-id="f2a02-116">Indicates that version upgrade information should be included.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f2a02-117">Note</span><span class="sxs-lookup"><span data-stu-id="f2a02-117">Remarks</span></span>  
 <span data-ttu-id="f2a02-118">I flag di architettura della piattaforma seguenti possono essere specificati solo uno alla volta e non possono essere combinati:</span><span class="sxs-lookup"><span data-stu-id="f2a02-118">The following platform architecture flags can be specified only one at a time and cannot be combined:</span></span>  
  
- <span data-ttu-id="f2a02-119">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="f2a02-119">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="f2a02-120">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="f2a02-120">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="f2a02-121">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="f2a02-121">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2a02-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f2a02-122">Requirements</span></span>  
 <span data-ttu-id="f2a02-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2a02-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2a02-124">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f2a02-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2a02-125">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f2a02-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2a02-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2a02-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2a02-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2a02-127">See also</span></span>

- [<span data-ttu-id="f2a02-128">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="f2a02-128">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
