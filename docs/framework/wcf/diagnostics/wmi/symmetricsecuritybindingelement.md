---
title: SymmetricSecurityBindingElement
ms.date: 03/30/2017
ms.assetid: b2e182b6-c041-4d80-a926-6058068d9f79
ms.openlocfilehash: 7b979a6872da15c4130e580a3f7327802f42db18
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54701391"
---
# <a name="symmetricsecuritybindingelement"></a><span data-ttu-id="4e362-102">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4e362-102">SymmetricSecurityBindingElement</span></span>
<span data-ttu-id="4e362-103">SymmetricSecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="4e362-103">SymmetricSecurityBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e362-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4e362-104">Syntax</span></span>  
  
```csharp
class SymmetricSecurityBindingElement : SecurityBindingElement  
{  
  string MessageProtectionOrder;  
  boolean RequireSignatureConfirmation;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4e362-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="4e362-105">Methods</span></span>  
 <span data-ttu-id="4e362-106">La classe SymmetricSecurityBindingElement non definisce metodi.</span><span class="sxs-lookup"><span data-stu-id="4e362-106">The SymmetricSecurityBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4e362-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="4e362-107">Properties</span></span>  
 <span data-ttu-id="4e362-108">La classe SymmetricSecurityBindingElement dispone delle proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="4e362-108">The SymmetricSecurityBindingElement class has the following properties:</span></span>  
  
### <a name="messageprotectionorder"></a><span data-ttu-id="4e362-109">MessageProtectionOrder</span><span class="sxs-lookup"><span data-stu-id="4e362-109">MessageProtectionOrder</span></span>  
 <span data-ttu-id="4e362-110">Tipo di dati: stringa</span><span class="sxs-lookup"><span data-stu-id="4e362-110">Data type: string</span></span>  
  
 <span data-ttu-id="4e362-111">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4e362-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e362-112">Ordine di crittografia e firma dei messaggi per questa associazione.</span><span class="sxs-lookup"><span data-stu-id="4e362-112">The order of message encryption and signing for this binding.</span></span>  
  
### <a name="requiresignatureconfirmation"></a><span data-ttu-id="4e362-113">RequireSignatureConfirmation</span><span class="sxs-lookup"><span data-stu-id="4e362-113">RequireSignatureConfirmation</span></span>  
 <span data-ttu-id="4e362-114">Tipo di dati: booleano</span><span class="sxs-lookup"><span data-stu-id="4e362-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4e362-115">Tipo di accesso: Sola lettura</span><span class="sxs-lookup"><span data-stu-id="4e362-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4e362-116">Indica se l'associazione richiede la conferma della firma.</span><span class="sxs-lookup"><span data-stu-id="4e362-116">Whether the binding requires signature confirmation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e362-117">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4e362-117">Requirements</span></span>  
  
|<span data-ttu-id="4e362-118">MOF</span><span class="sxs-lookup"><span data-stu-id="4e362-118">MOF</span></span>|<span data-ttu-id="4e362-119">Dichiarato in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="4e362-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4e362-120">Spazio dei nomi</span><span class="sxs-lookup"><span data-stu-id="4e362-120">Namespace</span></span>|<span data-ttu-id="4e362-121">Definito in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4e362-121">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e362-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4e362-122">See also</span></span>
- <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>
