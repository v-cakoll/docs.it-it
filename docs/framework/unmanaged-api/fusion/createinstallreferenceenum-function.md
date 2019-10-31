---
title: Funzione CreateInstallReferenceEnum
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
ms.openlocfilehash: f089769f854bad5d3e572e0307734e06e72ca89c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108562"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="b09d1-102">Funzione CreateInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b09d1-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="b09d1-103">Ottiene un puntatore a un'istanza di [IInstallReferenceEnum](iinstallreferenceenum-interface.md) che rappresenta un elenco di riferimenti di un'applicazione all'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="b09d1-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b09d1-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b09d1-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b09d1-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b09d1-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="b09d1-106">out Puntatore `IInstallReferenceEnum` restituito.</span><span class="sxs-lookup"><span data-stu-id="b09d1-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="b09d1-107">in [IAssemblyName](iassemblyname-interface.md) che identifica l'assembly per il quale enumerare i riferimenti.</span><span class="sxs-lookup"><span data-stu-id="b09d1-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b09d1-108">in Flag che influenzano il comportamento dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="b09d1-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b09d1-109">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="b09d1-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b09d1-110">`pvReserved` deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="b09d1-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b09d1-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b09d1-111">Requirements</span></span>  
 <span data-ttu-id="b09d1-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b09d1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b09d1-113">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b09d1-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b09d1-114">**Libreria:** Fusion. dll e mscorwks. dll.</span><span class="sxs-lookup"><span data-stu-id="b09d1-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="b09d1-115">Usare Fusion. dll invece di mscorwks. dll per assicurarsi di avere come destinazione la versione corretta del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b09d1-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="b09d1-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b09d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b09d1-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b09d1-117">See also</span></span>

- [<span data-ttu-id="b09d1-118">Interfaccia IInstallReferenceEnum</span><span class="sxs-lookup"><span data-stu-id="b09d1-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="b09d1-119">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="b09d1-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="b09d1-120">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="b09d1-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
