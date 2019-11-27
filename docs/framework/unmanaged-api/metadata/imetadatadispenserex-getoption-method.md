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
ms.openlocfilehash: ab74b02df959fe6e6457273e67ba3b82ae6a015c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435998"
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="cc4f0-102">Metodo IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="cc4f0-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="cc4f0-103">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="cc4f0-104">L'opzione consente di controllare il modo in cui vengono gestite le chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc4f0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cc4f0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc4f0-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="cc4f0-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="cc4f0-107">in Puntatore a un GUID che specifica l'opzione da recuperare.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="cc4f0-108">Vedere la sezione Osservazioni per un elenco di GUID supportati.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="cc4f0-109">out Valore dell'opzione restituita.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-109">[out] The value of the returned option.</span></span> <span data-ttu-id="cc4f0-110">Il tipo di questo valore sarà una variante del tipo dell'opzione specificata.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc4f0-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="cc4f0-111">Remarks</span></span>  
 <span data-ttu-id="cc4f0-112">Nell'elenco seguente sono illustrati i GUID supportati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="cc4f0-113">Per le descrizioni, vedere il metodo [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cc4f0-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="cc4f0-114">Se `optionId` non è presente nell'elenco, questo metodo restituisce HRESULT `E_INVALIDARG`, che indica un parametro errato.</span><span class="sxs-lookup"><span data-stu-id="cc4f0-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
- <span data-ttu-id="cc4f0-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="cc4f0-115">MetaDataCheckDuplicatesFor</span></span>  
  
- <span data-ttu-id="cc4f0-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="cc4f0-116">MetaDataRefToDefCheck</span></span>  
  
- <span data-ttu-id="cc4f0-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="cc4f0-117">MetaDataNotificationForTokenMovement</span></span>  
  
- <span data-ttu-id="cc4f0-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="cc4f0-118">MetaDataSetENC</span></span>  
  
- <span data-ttu-id="cc4f0-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="cc4f0-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
- <span data-ttu-id="cc4f0-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="cc4f0-120">MetaDataGenerateTCEAdapters</span></span>  
  
- <span data-ttu-id="cc4f0-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="cc4f0-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc4f0-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cc4f0-122">Requirements</span></span>  
 <span data-ttu-id="cc4f0-123">**Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc4f0-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc4f0-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cc4f0-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc4f0-125">**Libreria:** Usato come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc4f0-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc4f0-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc4f0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc4f0-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cc4f0-127">See also</span></span>

- [<span data-ttu-id="cc4f0-128">Interfaccia IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="cc4f0-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="cc4f0-129">Interfaccia IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="cc4f0-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
