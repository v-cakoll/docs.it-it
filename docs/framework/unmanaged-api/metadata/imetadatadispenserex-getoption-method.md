---
title: Metodo IMetaDataDispenserEx::GetOption
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx.GetOption
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fa9db222c81c2d6536b782c3e047e24c773bd018
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserexgetoption-method"></a><span data-ttu-id="5c230-102">Metodo IMetaDataDispenserEx::GetOption</span><span class="sxs-lookup"><span data-stu-id="5c230-102">IMetaDataDispenserEx::GetOption Method</span></span>
<span data-ttu-id="5c230-103">Ottiene il valore dell'opzione specificata per l'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="5c230-103">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="5c230-104">L'opzione controlla la modalità di gestione delle chiamate all'ambito dei metadati corrente.</span><span class="sxs-lookup"><span data-stu-id="5c230-104">The option controls how calls to the current metadata scope are handled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c230-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5c230-105">Syntax</span></span>  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c230-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5c230-106">Parameters</span></span>  
 `optionId`  
 <span data-ttu-id="5c230-107">[in] Puntatore a un GUID che specifica l'opzione da recuperare.</span><span class="sxs-lookup"><span data-stu-id="5c230-107">[in] A pointer to a GUID that specifies the option to be retrieved.</span></span> <span data-ttu-id="5c230-108">Vedere la sezione Osservazioni per un elenco di GUID supportati.</span><span class="sxs-lookup"><span data-stu-id="5c230-108">See the Remarks section for a list of supported GUIDs.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5c230-109">[out] Il valore dell'opzione restituita.</span><span class="sxs-lookup"><span data-stu-id="5c230-109">[out] The value of the returned option.</span></span> <span data-ttu-id="5c230-110">Il tipo di questo valore sarà una variante del tipo dell'opzione specificata.</span><span class="sxs-lookup"><span data-stu-id="5c230-110">The type of this value will be a variant of the specified option's type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c230-111">Note</span><span class="sxs-lookup"><span data-stu-id="5c230-111">Remarks</span></span>  
 <span data-ttu-id="5c230-112">Nell'elenco seguente vengono illustrati i GUID che sono supportati per questo metodo.</span><span class="sxs-lookup"><span data-stu-id="5c230-112">The following list shows the GUIDs that are supported for this method.</span></span> <span data-ttu-id="5c230-113">Per le descrizioni, vedere il [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="5c230-113">For descriptions, see the [IMetaDataDispenserEx::SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) method.</span></span> <span data-ttu-id="5c230-114">Se `optionId` è non in elenco, questo metodo restituisce HRESULT `E_INVALIDARG`, che indica un parametro non corretto.</span><span class="sxs-lookup"><span data-stu-id="5c230-114">If `optionId` is not in this list, this method returns HRESULT `E_INVALIDARG`, indicating an incorrect parameter.</span></span>  
  
-   <span data-ttu-id="5c230-115">MetaDataCheckDuplicatesFor</span><span class="sxs-lookup"><span data-stu-id="5c230-115">MetaDataCheckDuplicatesFor</span></span>  
  
-   <span data-ttu-id="5c230-116">MetaDataRefToDefCheck</span><span class="sxs-lookup"><span data-stu-id="5c230-116">MetaDataRefToDefCheck</span></span>  
  
-   <span data-ttu-id="5c230-117">MetaDataNotificationForTokenMovement</span><span class="sxs-lookup"><span data-stu-id="5c230-117">MetaDataNotificationForTokenMovement</span></span>  
  
-   <span data-ttu-id="5c230-118">MetaDataSetENC</span><span class="sxs-lookup"><span data-stu-id="5c230-118">MetaDataSetENC</span></span>  
  
-   <span data-ttu-id="5c230-119">MetaDataErrorIfEmitOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="5c230-119">MetaDataErrorIfEmitOutOfOrder</span></span>  
  
-   <span data-ttu-id="5c230-120">MetaDataGenerateTCEAdapters</span><span class="sxs-lookup"><span data-stu-id="5c230-120">MetaDataGenerateTCEAdapters</span></span>  
  
-   <span data-ttu-id="5c230-121">MetaDataLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="5c230-121">MetaDataLinkerOptions</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c230-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5c230-122">Requirements</span></span>  
 <span data-ttu-id="5c230-123">**Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c230-123">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c230-124">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5c230-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c230-125">**Libreria:** usata come risorsa in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5c230-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c230-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c230-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c230-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5c230-127">See Also</span></span>  
 [<span data-ttu-id="5c230-128">IMetaDataDispenserEx (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5c230-128">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [<span data-ttu-id="5c230-129">IMetaDataDispenser (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="5c230-129">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
