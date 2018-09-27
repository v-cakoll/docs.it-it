---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397358"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="75a2a-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="75a2a-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="75a2a-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="75a2a-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75a2a-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="75a2a-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="75a2a-105">Methods</span></span>  
 <span data-ttu-id="75a2a-106">La classe AsymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="75a2a-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="75a2a-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="75a2a-107">Properties</span></span>  
 <span data-ttu-id="75a2a-108">La classe AsymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="75a2a-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="75a2a-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="75a2a-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="75a2a-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="75a2a-110">Data type: string</span></span>  
  
 <span data-ttu-id="75a2a-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="75a2a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75a2a-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="75a2a-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="75a2a-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="75a2a-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="75a2a-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="75a2a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="75a2a-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="75a2a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75a2a-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="75a2a-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75a2a-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="75a2a-117">Requirements</span></span>  
  
|<span data-ttu-id="75a2a-118">MOF</span><span class="sxs-lookup"><span data-stu-id="75a2a-118">MOF</span></span>|<span data-ttu-id="75a2a-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="75a2a-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="75a2a-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="75a2a-120">Namespace</span></span>|<span data-ttu-id="75a2a-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="75a2a-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75a2a-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75a2a-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
