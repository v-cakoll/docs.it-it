---
title: AsymmetricSecurityBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 82e5365a440d103727f354e682d0ebecb5f46a46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="dd3d2-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dd3d2-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="dd3d2-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="dd3d2-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd3d2-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dd3d2-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dd3d2-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="dd3d2-105">Methods</span></span>  
 <span data-ttu-id="dd3d2-106">La classe AsymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="dd3d2-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dd3d2-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="dd3d2-107">Properties</span></span>  
 <span data-ttu-id="dd3d2-108">La classe AsymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="dd3d2-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="dd3d2-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="dd3d2-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="dd3d2-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="dd3d2-110">Data type: string</span></span>  
  
 <span data-ttu-id="dd3d2-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd3d2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd3d2-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="dd3d2-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="dd3d2-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="dd3d2-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="dd3d2-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="dd3d2-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="dd3d2-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="dd3d2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dd3d2-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="dd3d2-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd3d2-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dd3d2-117">Requirements</span></span>  
  
|<span data-ttu-id="dd3d2-118">MOF</span><span class="sxs-lookup"><span data-stu-id="dd3d2-118">MOF</span></span>|<span data-ttu-id="dd3d2-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dd3d2-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dd3d2-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="dd3d2-120">Namespace</span></span>|<span data-ttu-id="dd3d2-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dd3d2-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dd3d2-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dd3d2-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
