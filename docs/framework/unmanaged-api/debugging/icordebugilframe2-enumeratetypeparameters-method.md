---
title: Metodo ICorDebugILFrame2::EnumerateTypeParameters
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7454b551edc546fecbd9d091f7c821e0a07b16df
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497821"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="843bd-102">Metodo ICorDebugILFrame2::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="843bd-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="843bd-103">Ottiene un oggetto ICorDebugTypeEnum che contiene il <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="843bd-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="843bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="843bd-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="843bd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="843bd-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="843bd-106">Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugTypeEnum che consente l'enumerazione dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="843bd-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="843bd-107">L'elenco di parametri di tipo include i parametri di tipo classe (se presente) seguite dai parametri di tipo di metodo (se presente).</span><span class="sxs-lookup"><span data-stu-id="843bd-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="843bd-108">Note</span><span class="sxs-lookup"><span data-stu-id="843bd-108">Remarks</span></span>  
 <span data-ttu-id="843bd-109">Usare la [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) metodo per determinare il numero di parametri di tipo classe e metodo digitare i parametri contenuti in questo elenco.</span><span class="sxs-lookup"><span data-stu-id="843bd-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="843bd-110">I parametri di tipo non sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="843bd-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="843bd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="843bd-111">Requirements</span></span>  
 <span data-ttu-id="843bd-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="843bd-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="843bd-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="843bd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="843bd-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="843bd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="843bd-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="843bd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
