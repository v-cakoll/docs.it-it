---
title: Enumerazione COUNINITIEE
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176123"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="cdc8f-102">Enumerazione COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="cdc8f-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="cdc8f-103">Specifica le costanti utilizzate da [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) durante l'inizializzazione di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cdc8f-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdc8f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cdc8f-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="cdc8f-105">Members</span><span class="sxs-lookup"><span data-stu-id="cdc8f-105">Members</span></span>  
  
|<span data-ttu-id="cdc8f-106">Membro</span><span class="sxs-lookup"><span data-stu-id="cdc8f-106">Member</span></span>|<span data-ttu-id="cdc8f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cdc8f-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="cdc8f-108">Indica la modalità di annullamento dell'inizializzazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="cdc8f-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="cdc8f-109">Indica la modalità di annullamento dell'inizializzazione per lo scaricamento di un assembly.</span><span class="sxs-lookup"><span data-stu-id="cdc8f-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cdc8f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cdc8f-110">Requirements</span></span>  
 <span data-ttu-id="cdc8f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdc8f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdc8f-112">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cdc8f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cdc8f-113">**Biblioteca:** Incluso come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cdc8f-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cdc8f-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdc8f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdc8f-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdc8f-115">See also</span></span>

- [<span data-ttu-id="cdc8f-116">Enumerazioni dei metadati</span><span class="sxs-lookup"><span data-stu-id="cdc8f-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
