---
title: Metodo ResolveTypeLib
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
ms.openlocfilehash: f0f6fe321f4d38129b6d70ce94a7ea8de8fff6c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935664"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="76f62-102">Metodo ResolveTypeLib</span><span class="sxs-lookup"><span data-stu-id="76f62-102">ResolveTypeLib Method</span></span>
<span data-ttu-id="76f62-103">Risolve il nome semplice di una libreria dei tipi restituendo il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="76f62-103">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76f62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="76f62-104">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76f62-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="76f62-105">Parameters</span></span>  
 `bstrSimpleName`  
 <span data-ttu-id="76f62-106">in [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il nome semplice della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="76f62-106">[in] A [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="76f62-107">in GUID assegnato alla libreria dei tipi nel registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="76f62-107">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="76f62-108">in ID di localizzazione della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="76f62-108">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="76f62-109">in Numero di versione principale della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="76f62-109">[in] The major version number of the type library.</span></span> <span data-ttu-id="76f62-110">Per la versione *x. y*, ad esempio, il numero di versione principale è *x*.</span><span class="sxs-lookup"><span data-stu-id="76f62-110">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="76f62-111">in Numero della versione secondaria della libreria dei tipi.</span><span class="sxs-lookup"><span data-stu-id="76f62-111">[in] The minor version number of the type library.</span></span> <span data-ttu-id="76f62-112">Per la versione *x. y*, ad esempio, il numero di versione secondario è *y*.</span><span class="sxs-lookup"><span data-stu-id="76f62-112">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="76f62-113">in Flag [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) che identifica l'ambiente operativo.</span><span class="sxs-lookup"><span data-stu-id="76f62-113">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="76f62-114">I valori comuni sono SYS_WIN32 e SYS_WIN64.</span><span class="sxs-lookup"><span data-stu-id="76f62-114">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="76f62-115">out Puntatore a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominata nel parametro `bstrSimpleName`.</span><span class="sxs-lookup"><span data-stu-id="76f62-115">[out] A pointer to a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76f62-116">Note</span><span class="sxs-lookup"><span data-stu-id="76f62-116">Remarks</span></span>  
 <span data-ttu-id="76f62-117">Il metodo `ResolveTypeLib` viene chiamato dalla [funzione LoadTypeLibWithResolver](loadtypelibwithresolver-function.md) durante l'elaborazione di [Tlbexp. exe (utilità di esportazione della libreria dei tipi)](../../tools/tlbexp-exe-type-library-exporter.md) .</span><span class="sxs-lookup"><span data-stu-id="76f62-117">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="76f62-118">Le implementazioni personalizzate di questa interfaccia devono restituire un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) che contiene il percorso completo della libreria dei tipi denominata nel parametro `bstrSimpleName`.</span><span class="sxs-lookup"><span data-stu-id="76f62-118">Custom implementations of this interface must return a [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76f62-119">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="76f62-119">Requirements</span></span>  
 <span data-ttu-id="76f62-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76f62-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76f62-121">**Intestazione:** TlbRef. idl, TlbRef. h</span><span class="sxs-lookup"><span data-stu-id="76f62-121">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="76f62-122">**Libreria:** TlbRef. lib</span><span class="sxs-lookup"><span data-stu-id="76f62-122">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="76f62-123">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76f62-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f62-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76f62-124">See also</span></span>

- [<span data-ttu-id="76f62-125">Funzioni di supporto Tlbexp</span><span class="sxs-lookup"><span data-stu-id="76f62-125">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="76f62-126">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="76f62-126">LoadTypeLibEx</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
