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
ms.openlocfilehash: 9020fed83b1c57cae3cc492872a279afb0195983
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205166"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="719dd-102">Metodo ICorDebugILFrame2::EnumerateTypeParameters</span><span class="sxs-lookup"><span data-stu-id="719dd-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="719dd-103">Ottiene un oggetto ICorDebugTypeEnum che contiene i <xref:System.Type> parametri in questo frame.</span><span class="sxs-lookup"><span data-stu-id="719dd-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="719dd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="719dd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="719dd-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="719dd-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="719dd-106">Puntatore all'indirizzo di un oggetto interfaccia ICorDebugTypeEnum che consente l'enumerazione dei parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="719dd-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="719dd-107">L'elenco dei parametri di tipo include i parametri di tipo di classe, se presenti, seguiti dai parametri di tipo del metodo, se presenti.</span><span class="sxs-lookup"><span data-stu-id="719dd-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="719dd-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="719dd-108">Remarks</span></span>  
 <span data-ttu-id="719dd-109">Usare il metodo [IMetaDataImport2:: EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) per determinare il numero di parametri di tipo di classe e i parametri di tipo di metodo contenuti nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="719dd-109">Use the [IMetaDataImport2::EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="719dd-110">I parametri di tipo non sono sempre disponibili.</span><span class="sxs-lookup"><span data-stu-id="719dd-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="719dd-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="719dd-111">Requirements</span></span>  
 <span data-ttu-id="719dd-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="719dd-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="719dd-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="719dd-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="719dd-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="719dd-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="719dd-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="719dd-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
