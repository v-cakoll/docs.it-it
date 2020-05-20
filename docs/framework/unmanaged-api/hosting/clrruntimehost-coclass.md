---
title: Coclasse CLRRuntimeHost
ms.date: 03/30/2017
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616801"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="593bd-102">Coclasse CLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="593bd-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="593bd-103">Fornisce interfacce per la gestione dell'esecuzione del codice da parte del runtime.</span><span class="sxs-lookup"><span data-stu-id="593bd-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="593bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="593bd-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="593bd-105">Interfacce</span><span class="sxs-lookup"><span data-stu-id="593bd-105">Interfaces</span></span>  
  
|<span data-ttu-id="593bd-106">Interfaccia</span><span class="sxs-lookup"><span data-stu-id="593bd-106">Interface</span></span>|<span data-ttu-id="593bd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="593bd-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="593bd-108">Interfaccia ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="593bd-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="593bd-109">Fornisce metodi per controllare l'esecuzione delle applicazioni da parte del runtime.</span><span class="sxs-lookup"><span data-stu-id="593bd-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="593bd-110">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="593bd-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="593bd-111">Fornisce metodi per la convalida delle immagini eseguibili portabili e per la segnalazione dettagliata degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="593bd-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="593bd-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="593bd-112">Requirements</span></span>  
 <span data-ttu-id="593bd-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="593bd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="593bd-114">**Intestazione:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="593bd-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="593bd-115">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="593bd-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="593bd-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="593bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="593bd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="593bd-117">See also</span></span>

- [<span data-ttu-id="593bd-118">Coclassi di hosting</span><span class="sxs-lookup"><span data-stu-id="593bd-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
