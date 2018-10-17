---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
author: BrucePerlerMS
ms.openlocfilehash: e633ae19cd17930fb140a93ffd0910c7ed8efea4
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374432"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="48e62-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="48e62-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="48e62-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="48e62-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e62-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48e62-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="48e62-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="48e62-105">Methods</span></span>  
 <span data-ttu-id="48e62-106">La classe SymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="48e62-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="48e62-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="48e62-107">Properties</span></span>  
 <span data-ttu-id="48e62-108">La classe SymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="48e62-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="48e62-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="48e62-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="48e62-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="48e62-110">Data type: string</span></span>  
  
 <span data-ttu-id="48e62-111">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="48e62-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48e62-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="48e62-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="48e62-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="48e62-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="48e62-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="48e62-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="48e62-115">Tipo di accesso: sola lettura</span><span class="sxs-lookup"><span data-stu-id="48e62-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48e62-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="48e62-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48e62-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48e62-117">Requirements</span></span>  
  
|<span data-ttu-id="48e62-118">MOF</span><span class="sxs-lookup"><span data-stu-id="48e62-118">MOF</span></span>|<span data-ttu-id="48e62-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="48e62-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="48e62-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="48e62-120">Namespace</span></span>|<span data-ttu-id="48e62-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="48e62-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48e62-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48e62-122">See Also</span></span>  
 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
