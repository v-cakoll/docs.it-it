---
title: Funzione _CorExeMain
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756416"
---
# <a name="corexemain-function"></a><span data-ttu-id="7a204-102">Funzione _CorExeMain</span><span class="sxs-lookup"><span data-stu-id="7a204-102">_CorExeMain Function</span></span>
<span data-ttu-id="7a204-103">Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly eseguibile e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7a204-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a204-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a204-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7a204-105">Note</span><span class="sxs-lookup"><span data-stu-id="7a204-105">Remarks</span></span>  
 <span data-ttu-id="7a204-106">Questa funzione viene chiamata dal caricatore nei processi creati dagli assembly eseguibile gestito.</span><span class="sxs-lookup"><span data-stu-id="7a204-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="7a204-107">Per gli assembly DLL, il caricatore chiama il [CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="7a204-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="7a204-108">Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file di immagine.</span><span class="sxs-lookup"><span data-stu-id="7a204-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="7a204-109">In Windows 98, Windows ME, Windows NT e Windows 2000, la `_CorExeMain` funzione viene chiamata indirettamente tramite una correzione nel caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7a204-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="7a204-110">In tutte le altre versioni di Windows, bensì direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7a204-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="7a204-111">Per altre informazioni, vedere la sezione osservazioni nel [CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="7a204-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a204-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7a204-112">Requirements</span></span>  
 <span data-ttu-id="7a204-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a204-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a204-114">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7a204-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a204-115">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="7a204-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a204-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a204-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a204-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7a204-117">See also</span></span>

- [<span data-ttu-id="7a204-118">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="7a204-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
