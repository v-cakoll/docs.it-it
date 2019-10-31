---
title: Interfaccia IInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
ms.openlocfilehash: d3f7c24b4bd373924c44dbc0490c890e7f1322bd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131728"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="664a7-102">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="664a7-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="664a7-103">Rappresenta un enumeratore per gli assembly di riferimento installati nell'Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="664a7-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="664a7-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="664a7-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="664a7-105">Methods</span></span>  
  
|<span data-ttu-id="664a7-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="664a7-106">Method</span></span>|<span data-ttu-id="664a7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="664a7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="664a7-108">Metodo GetNextInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="664a7-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="664a7-109">Ottiene un puntatore al `IInstallReferenceItem` successivo contenuto nell'`IInstallReferenceEnum`.</span><span class="sxs-lookup"><span data-stu-id="664a7-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="664a7-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="664a7-110">Requirements</span></span>  
 <span data-ttu-id="664a7-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="664a7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="664a7-112">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="664a7-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="664a7-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="664a7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="664a7-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="664a7-114">See also</span></span>

- [<span data-ttu-id="664a7-115">Interfacce Fusion</span><span class="sxs-lookup"><span data-stu-id="664a7-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="664a7-116">Interfaccia IInstallReferenceItem</span><span class="sxs-lookup"><span data-stu-id="664a7-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
