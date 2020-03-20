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
ms.openlocfilehash: 816e2f2dc7d4d00f74f67720ee45d7b3483e57fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177724"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="644f3-102">Metodo IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="644f3-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="644f3-103">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="644f3-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="644f3-104">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="644f3-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="644f3-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="644f3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="644f3-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="644f3-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="644f3-107">[in] Puntatore a un GUID che specifica l'opzione da recuperare.</span><span class="sxs-lookup"><span data-stu-id="644f3-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="644f3-108">Vedere la sezione Osservazioni per un elenco dei GUID supportati.</span><span class="sxs-lookup"><span data-stu-id="644f3-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="644f3-109">[fuori] Valore dell'opzione restituita.</span><span class="sxs-lookup"><span data-stu-id="644f3-109">[out] The value of the returned option.</span></span> <span data-ttu-id="644f3-110">Il tipo di questo valore sarà una variante del tipo di opzione specificata.</span><span class="sxs-lookup"><span data-stu-id="644f3-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="644f3-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="644f3-111">Remarks</span></span>  
 <span data-ttu-id="644f3-112">Nell'elenco seguente vengono illustrati i GUID supportati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="644f3-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="644f3-113">Per le descrizioni, vedere il metodo [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="644f3-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="644f3-114">Se `optionId` non è presente nell'elenco, `E_INVALIDARG`questo metodo restituisce HRESULT , che indica un parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="644f3-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="644f3-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="644f3-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="644f3-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="644f3-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="644f3-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="644f3-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="644f3-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="644f3-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="644f3-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="644f3-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="644f3-120">MetaDataGenerateTCEAdapter</span><span class="sxs-lookup"><span data-stu-id="644f3-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="644f3-121">MetaDataLinkerOpzioni</span><span class="sxs-lookup"><span data-stu-id="644f3-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="644f3-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="644f3-122">Requirements</span></span>  
 <span data-ttu-id="644f3-123">**Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="644f3-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="644f3-124">**Intestazione:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="644f3-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="644f3-125">**Biblioteca:** Utilizzato come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="644f3-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="644f3-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="644f3-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="644f3-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="644f3-127">See also</span></span>

- [<span data-ttu-id="644f3-128">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="644f3-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="644f3-129">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="644f3-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
