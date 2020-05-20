---
title: Funzione GetCORVersion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 23d68e8e4bbd87779e3b49f0c40f5a5ab9f5124f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617217"
---
# <a name="getcorversion-function"></a><span data-ttu-id="615fa-102">Funzione GetCORVersion</span><span class="sxs-lookup"><span data-stu-id="615fa-102">GetCORVersion Function</span></span>
<span data-ttu-id="615fa-103">Restituisce il numero di versione del Common Language Runtime (CLR) in esecuzione nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="615fa-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="615fa-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="615fa-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="615fa-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="615fa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="615fa-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="615fa-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="615fa-107">Puntatore a un buffer in cui CLR restituisce una stringa che specifica la versione del Runtime attualmente caricata nel processo.</span><span class="sxs-lookup"><span data-stu-id="615fa-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="615fa-108">La stringa restituita assume lo stesso formato delle stringhe passate a [CorBindToRuntimeEx](corbindtoruntimeex-function.md), ad esempio, "v 1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="615fa-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="615fa-109">Se il runtime non è ancora stato caricato nel processo, la funzione restituisce le informazioni di directory appropriate per la versione più recente del runtime installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="615fa-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="615fa-110">Numero di caratteri `WCHAR` che possono essere conservati in `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="615fa-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="615fa-111">Puntatore al numero di caratteri effettivamente restituiti in `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="615fa-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="615fa-112">Se `pbuffer` è un puntatore null, il runtime restituisce E_POINTER.</span><span class="sxs-lookup"><span data-stu-id="615fa-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="615fa-113">Se il numero di caratteri è maggiore della lunghezza di `pbuffer` , il runtime restituisce ERROR_INSUFFICIENT_BUFFER.</span><span class="sxs-lookup"><span data-stu-id="615fa-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="615fa-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="615fa-114">Requirements</span></span>  
 <span data-ttu-id="615fa-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="615fa-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="615fa-116">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="615fa-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="615fa-117">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="615fa-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="615fa-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="615fa-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615fa-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="615fa-119">See also</span></span>

- [<span data-ttu-id="615fa-120">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="615fa-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
