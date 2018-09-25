---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
author: BrucePerlerMS
ms.openlocfilehash: 63af1c9a607cb9f81e2c0abf795ee2b3432cbf9c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075057"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="3e137-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3e137-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="3e137-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="3e137-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e137-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e137-104">Syntax</span></span>  
  
```  
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3e137-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="3e137-105">Methods</span></span>  
 <span data-ttu-id="3e137-106">La classe AsymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="3e137-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3e137-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="3e137-107">Properties</span></span>  
 <span data-ttu-id="3e137-108">La classe AsymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e137-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="3e137-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="3e137-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="3e137-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="3e137-110">Data type: string</span></span>  
  
 <span data-ttu-id="3e137-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e137-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e137-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="3e137-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="3e137-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="3e137-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="3e137-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="3e137-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3e137-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="3e137-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3e137-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="3e137-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e137-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e137-117">Requirements</span></span>  
  
|<span data-ttu-id="3e137-118">MOF</span><span class="sxs-lookup"><span data-stu-id="3e137-118">MOF</span></span>|<span data-ttu-id="3e137-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3e137-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3e137-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="3e137-120">Namespace</span></span>|<span data-ttu-id="3e137-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3e137-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3e137-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e137-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
