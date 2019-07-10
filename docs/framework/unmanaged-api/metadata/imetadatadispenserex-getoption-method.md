---
title: Metodo IMetaDataDispenserEx::GetOption
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8717a1eafebf24366c35848dbe285943c107ed51
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777729"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="c3b3d-102">Metodo IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="c3b3d-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="c3b3d-103">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="c3b3d-104">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b3d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c3b3d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b3d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c3b3d-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="c3b3d-107">[in] Un puntatore a un GUID che specifica l'opzione da recuperare.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="c3b3d-108">Vedere la sezione Osservazioni per un elenco di GUID supportati.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c3b3d-109">[out] Il valore dell'opzione restituita.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-109">[out] The value of the returned option.</span></span> <span data-ttu-id="c3b3d-110">Il tipo di questo valore sarà una variante di tipo dell'opzione specificata.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b3d-111">Note</span><span class="sxs-lookup"><span data-stu-id="c3b3d-111">Remarks</span></span>  
 <span data-ttu-id="c3b3d-112">L'elenco seguente mostra i GUID che sono supportati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="c3b3d-113">Per descrizioni, vedere la [IMetaDataDispenserEx](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="c3b3d-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="c3b3d-114">Se `optionId` è non in elenco, questo metodo restituisce HRESULT `E_INVALIDARG`, che indica un parametro errato.</span><span class="sxs-lookup"><span data-stu-id="c3b3d-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="c3b3d-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="c3b3d-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="c3b3d-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="c3b3d-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="c3b3d-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="c3b3d-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="c3b3d-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="c3b3d-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="c3b3d-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="c3b3d-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="c3b3d-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="c3b3d-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="c3b3d-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="c3b3d-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3b3d-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c3b3d-122">Requirements</span></span>  
 <span data-ttu-id="c3b3d-123">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3b3d-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3b3d-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c3b3d-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3b3d-125">**Libreria:** Usato come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="c3b3d-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3b3d-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3b3d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3b3d-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c3b3d-127">See also</span></span>

- [<span data-ttu-id="c3b3d-128">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="c3b3d-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="c3b3d-129">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="c3b3d-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
