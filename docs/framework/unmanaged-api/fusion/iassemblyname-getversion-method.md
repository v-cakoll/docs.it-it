---
title: Metodo IAssemblyName::GetVersion
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetVersion
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetVersion
helpviewer_keywords:
- IAssemblyName::GetVersion method [.NET Framework fusion]
- GetVersion method, IAssemblyName interface [.NET Framework fusion]
ms.assetid: 42230928-2c33-41fd-9519-d96efef6c7af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 58919936bdc62d52437f429146f04c66d49294b2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796574"
---
# <a name="iassemblynamegetversion-method"></a><span data-ttu-id="fd347-102">Metodo IAssemblyName::GetVersion</span><span class="sxs-lookup"><span data-stu-id="fd347-102">IAssemblyName::GetVersion Method</span></span>
<span data-ttu-id="fd347-103">Ottiene le informazioni sulla versione per l'assembly a cui fa riferimento questo oggetto [IAssemblyName](iassemblyname-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="fd347-103">Gets the version information for the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd347-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd347-104">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion (  
    [out] LPDWORD pdwVersionHi,  
    [out] LPDWORD pdwVersionLow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd347-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd347-105">Parameters</span></span>  
 `pdwVersionHi`  
 <span data-ttu-id="fd347-106">out Bit 32 alti della versione.</span><span class="sxs-lookup"><span data-stu-id="fd347-106">[out] The high 32 bits of the version.</span></span>  
  
 `pdwVersionLow`  
 <span data-ttu-id="fd347-107">out Bit 32 bassi della versione.</span><span class="sxs-lookup"><span data-stu-id="fd347-107">[out] The low 32 bits of the version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd347-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd347-108">Requirements</span></span>  
 <span data-ttu-id="fd347-109">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd347-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd347-110">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="fd347-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fd347-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd347-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd347-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd347-112">See also</span></span>

- [<span data-ttu-id="fd347-113">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="fd347-113">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
