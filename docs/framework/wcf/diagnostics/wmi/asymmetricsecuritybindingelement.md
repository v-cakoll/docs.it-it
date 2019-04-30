---
title: AsymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: 7bd3b6be-8f77-4927-93ae-6fa371893cca
ms.openlocfilehash: 0f86fc1b410753b5ec100f0a7d43de9badd1401b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964203"
---
# <a name="asymmetricsecuritybindingelement"></a><span data-ttu-id="48e17-102">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="48e17-102">AsymmetricSecurityBindingElement</span></span>
<span data-ttu-id="48e17-103">AsymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="48e17-103">AsymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e17-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="48e17-104">Syntax</span></span>  
  
```csharp
class AsymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="48e17-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="48e17-105">Methods</span></span>  
 <span data-ttu-id="48e17-106">La classe AsymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="48e17-106">The AsymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="48e17-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="48e17-107">Properties</span></span>  
 <span data-ttu-id="48e17-108">La classe AsymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="48e17-108">The AsymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="48e17-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="48e17-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="48e17-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="48e17-110">Data type: string</span></span>  
  
 <span data-ttu-id="48e17-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="48e17-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48e17-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="48e17-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="48e17-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="48e17-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="48e17-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="48e17-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="48e17-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="48e17-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="48e17-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="48e17-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48e17-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="48e17-117">Requirements</span></span>  
  
|<span data-ttu-id="48e17-118">MOF</span><span class="sxs-lookup"><span data-stu-id="48e17-118">MOF</span></span>|<span data-ttu-id="48e17-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="48e17-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="48e17-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="48e17-120">Namespace</span></span>|<span data-ttu-id="48e17-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="48e17-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="48e17-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48e17-122">See also</span></span>

- <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>
