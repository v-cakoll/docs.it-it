---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 076313548828f1fbce9c68b48c0fa7db9cca095f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185118"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="30eeb-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="30eeb-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="30eeb-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="30eeb-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30eeb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30eeb-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="30eeb-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="30eeb-105">Methods</span></span>  
 <span data-ttu-id="30eeb-106">La classe AsymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="30eeb-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="30eeb-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="30eeb-107">Properties</span></span>  
 <span data-ttu-id="30eeb-108">La classe AsymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="30eeb-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="30eeb-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="30eeb-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="30eeb-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="30eeb-110">Data type: string</span></span>  
  
 <span data-ttu-id="30eeb-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="30eeb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30eeb-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="30eeb-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="30eeb-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="30eeb-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="30eeb-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="30eeb-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="30eeb-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="30eeb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="30eeb-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="30eeb-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30eeb-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="30eeb-117">Requirements</span></span>  
  
|<span data-ttu-id="30eeb-118">MOF</span><span class="sxs-lookup"><span data-stu-id="30eeb-118">MOF</span></span>|<span data-ttu-id="30eeb-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="30eeb-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="30eeb-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="30eeb-120">Namespace</span></span>|<span data-ttu-id="30eeb-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="30eeb-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30eeb-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30eeb-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
